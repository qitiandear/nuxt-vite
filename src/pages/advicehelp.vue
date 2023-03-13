<template>
  <div class="adviceandHelp pageContainer">
    <div class="banner_box">
      <el-image
        :src="banner"
        style="width: 100%"
        fit="cover"
        class="banner_img"
      />
    </div>
    <secondMenu
      :littleMenu="littleMenu"
      @clickSecondMenu="clickSecondMenu"
    ></secondMenu>
    <!-- 表单内容开始 -->
    <div class="form_box">
      <!-- 建议开始 -->
      <el-form
        :model="adviceForm"
        :rules="adviceRules"
        ref="adviceFormRef"
        label-width="180px"
        class="demo-ruleForm"
        v-show="activeMenu == '建议'"
      >
        <el-form-item label="建议标题：" prop="title">
          <el-input
            v-model="adviceForm.title"
            placeholder="请输入30字以内的内容"
            maxlength="30"
            show-word-limit
          ></el-input>
        </el-form-item>
        <div style="display: flex">
          <el-form-item label="留言人:" prop="name" style="width: 50%">
            <el-input v-model="adviceForm.name" placeholder="请输入留言人">
            </el-input>
          </el-form-item>
          <el-form-item label="联系方式:" prop="tel" style="width: 50%">
            <el-input v-model="adviceForm.tel" placeholder="请输入联系方式">
            </el-input>
          </el-form-item>
        </div>
        <el-form-item label="详细内容：" prop="cont">
          <el-input
            v-model="adviceForm.cont"
            placeholder="请您填写咨询或者建议的详细内容，以便我们尽快处理，建议200字以内"
            maxlength="200"
            show-word-limit
            type="textarea"
          ></el-input>
        </el-form-item>
        <el-form-item label="问题页链接：" prop="link">
          <el-input
            label="问题页链接"
            v-model="adviceForm.link"
            placeholder="Http://"
          >
          </el-input>
        </el-form-item>
        <el-form-item label="相关图片上传：" prop="link">
          <el-upload
            class="upload-demo"
            action="https://jsonplaceholder.typicode.com/posts/"
            :on-change="imgHandleChange"
            :file-list="fileList"
          >
            <el-button size="small" type="primary">点击上传</el-button>
            <template #tip>
              <div class="el-upload__tip">
                只能上传jpg/png文件，且不超过500kb
              </div>
            </template>
          </el-upload>
        </el-form-item>
        <el-form-item class="foot-btn">
          <el-button type="primary" @click="submitForm(adviceFormRef)"
            >确认提交</el-button
          >
          <el-button type="info" @click="resetForm(adviceFormRef)"
            >重新填写</el-button
          >
        </el-form-item>
      </el-form>
      <!-- 建议结束 -->

      <!-- 投诉开始 -->
      <el-form
        :model="complaintForm"
        :rules="complaintRules"
        ref="complaintFormRef"
        label-width="180px"
        class="demo-ruleForm"
        v-show="activeMenu == '投诉'"
      >
        <el-form-item label="姓名:" prop="name">
          <el-input v-model="complaintForm.name" placeholder="请输入留言人">
          </el-input>
        </el-form-item>
        <el-form-item label="联系方式:" prop="tel">
          <el-input v-model="complaintForm.tel" placeholder="请输入联系方式">
          </el-input>
        </el-form-item>
        <el-form-item label="投诉原因:" prop="reason">
          <el-input
            v-model="complaintForm.reason"
            placeholder="请您填写投诉原因的详细内容，以便我们尽快处理，建议500字以内"
            maxlength="500"
            show-word-limit
            type="textarea"
          ></el-input>
        </el-form-item>
        <el-form-item label="您的诉求:" prop="cont">
          <el-input
            v-model="complaintForm.cont"
            placeholder="请您填写您的诉求内容，以便我们尽快处理，建议500字以内"
            maxlength="500"
            show-word-limit
            type="textarea"
          ></el-input>
        </el-form-item>
        <el-form-item class="foot-btn">
          <el-button type="primary" @click="submitForm(complaintFormRef)"
            >确认提交</el-button
          >
          <el-button type="info" @click="resetForm(complaintFormRef)"
            >重新填写</el-button
          >
        </el-form-item>
      </el-form>
      <!-- 投诉结束 -->

      <!-- 咨询开始 -->
      <div class="question" v-show="activeMenu == '咨询'">
        <el-tabs v-model="activeName">
          <el-tab-pane
            :label="item.type"
            :name="'' + index"
            v-for="(item, index) in quesList"
            :key="index"
          >
            <el-collapse v-model="active2" accordion>
              <el-collapse-item
                :title="'Q：' + row.title"
                :name="'' + y"
                v-for="(row, y) in item.cont"
                :key="y"
              >
                <div class="answer_row">
                  <div>A：</div>
                  <div>
                    <div v-for="(ans, akey) in row.answer" :key="akey">
                      {{ akey + 1 }}、{{ ans }}
                    </div>
                  </div>
                </div>
                <span class="more"> 查看更多详细内容>> </span>
              </el-collapse-item>
            </el-collapse>
          </el-tab-pane>
        </el-tabs>
      </div>
      <!-- 咨询结束 -->

      <!-- 提交完成页面 -->
      <div class="question overimg" v-show="activeMenu == 'finished'">
        <img src="@/assets/images/help/letter.png" alt="" />
        <p>您已成功提交此次的{{ letterName }}</p>
        <div>
          我们将在收到您建议的第一时间进行处理，处理结果将对您进行有效反馈。
        </div>
      </div>
      <!-- 提交完成页面 -->
    </div>
    <!-- 表单内容结束 -->
  </div>
</template>

<script setup lang="ts">
import banner from '@/assets/images/help/banner.png'
import type { FormInstance, FormRules } from 'element-plus'
const adviceFormRef = ref<FormInstance>()
const complaintFormRef = ref<FormInstance>()

interface news {
  title: string
  id: number
}
const littleMenu = reactive([
  {
    title: '建议',
    id: 1,
  },
  {
    title: '咨询',
    id: 2,
  },
  {
    title: '投诉',
    id: 3,
  },
])
const adviceForm = reactive({
  title: '',
  cont: '',
  link: '',
  name: '',
  tel: '',
})
const adviceRules = reactive<FormRules>({
  title: [{ required: true, message: '请输入建议标题', trigger: 'blur' }],
})
const complaintForm = reactive({
  reason: '',
  cont: '',
  name: '',
  tel: '',
})
const complaintRules = reactive<FormRules>({
  reason: [{ required: true, message: '请输入投诉原因', trigger: 'blur' }],
})
const fileList = reactive([])
const activeMenu = ref('建议')
const activeName = ref('0')
const letterName = ref('建议')
const active2 = ref('0')
const quesList = reactive([
  {
    type: '常见问题',
    cont: [
      {
        title: '生产厂家如何与杏林丹心进行合作？',
        answer: [
          '您可以拨打杏林丹心7*24小时客服电话0351- 8786003与我们进行联系。 ',
          '您可扫描杏林丹心官网任一页面底部公众号二维码，关注杏林丹心公众号与我们进行联系。',
        ],
      },
      {
        title: '如何如何注册成为杏林丹心用户？',
        answer: ['如何如何注册成为杏林丹心用户 '],
      },
      {
        title: '手机注册用户忘记密码怎么办？',
        answer: ['手机注册用户忘记密码怎么办'],
      },
      {
        title: '邮箱注册用户忘记密码怎么办？',
        answer: ['邮箱注册用户忘记密码怎么办 '],
      },
      {
        title: '如何修改密码？',
        answer: ['修改密码 '],
      },
      {
        title: '网站纠错',
        answer: ['网站纠错 '],
      },
    ],
  },
  {
    type: '产品问题',
    cont: [
      {
        title: '林丹心后台如何获取账号？',
        answer: [
          '如果您提交了免费体验申请，在收到请求的24小时内将会有专业客服人员通过您留下的联系方式与您联系，将体验版系统账号告知于您。如果您购买了 正式版系统，您的专属客服人员将会在您定制的系统完成后，第一时间将账号通过邮箱、电话等方式告知与您。',
        ],
      },
      {
        title: '管理系统后台“单位管理”如何进行操作？',
        answer: ['管理系统后台“单位管理”如何进行操作？'],
      },
      {
        title: '如何进行产品、器械的管理工作？',
        answer: ['如何进行产品、器械的管理工作'],
      },
      {
        title: '如何创建采购计划？',
        answer: ['如何创建采购计划'],
      },
      {
        title: '如何对库存进行管理？',
        answer: ['如何对库存进行管理'],
      },
      {
        title: '管理系统后台登录异常问题',
        answer: ['管理系统后台登录异常问题'],
      },
    ],
  },
  {
    type: '网站事宜',
    cont: [
      {
        title: '建议帮助- 留言建议反馈功能的使用说明',
        answer: [
          '建议标题：为了便于我们更精准的为您提供解答服务，请简要描述您的建议。  ',
          '详细内容：此处请对您要反馈的问题进行详细描述，字数限制为10-500字。',
          '问题页链接：如您反馈页面上的问题，请在此处添加对应的网址链接。',
          '相关图片上传：此处最多可添加5张图片，每张图片大小不超过2M。上传图片的格式仅限jpg、jepg、png、gif、bmp。',
        ],
      },
      {
        title: '投诉举报流程说明',
        answer: [
          '投诉举报流程说明',
          '您可扫描杏林丹心官网任一页面底部公众号二维码，关注杏林丹心公众号与我们进行联系。',
        ],
      },
      {
        title: '网站纠错',
        answer: ['网站纠错'],
      },
      {
        title: '如何查看新闻中心各类新闻？',
        answer: ['如何查看新闻中心各类新闻？'],
      },
      {
        title: '如何详细了解杏林丹心公司信息？',
        answer: ['如何详细了解杏林丹心公司信息？'],
      },
      {
        title: '行业动态怎样进行了解',
        answer: ['行业动态怎样进行了解'],
      },
    ],
  },
  {
    type: '用户问题',
    cont: [
      {
        title: '如何注册成为杏林丹心用户',
        answer: [
          '在杏林丹心首页导航栏右上方，点击“用户”图标，在下滑框中点击“立即注册”。 ',
          '在杏林担心用户注册页中可通过手机或邮箱两种方式进行注册，中国大陆地区用户选择手机注册更为便利。填写完信息后点击“提交”即可。',
        ],
      },
      {
        title: '手机注册用户忘记密码怎么办',
        answer: ['手机注册用户忘记密码怎么办'],
      },
      {
        title: '如何进行第三方登录',
        answer: ['如何进行第三方登录'],
      },
      {
        title: '如何修改密码',
        answer: ['如何修改密码'],
      },
      {
        title: '如何修改昵称',
        answer: ['如何修改昵称'],
      },
      {
        title: '如何修改头像',
        answer: ['如何修改头像'],
      },
    ],
  },
  {
    type: '合作问题',
    cont: [
      {
        title: '建议帮助- 留言建议反馈功能的使用说明',
        answer: [
          '建议标题：为了便于我们更精准的为您提供解答服务，请简要描述您的建议 ',
          '详细内容：此处请对您要反馈的问题进行详细描述，字数限制为10-500字。',
        ],
      },
      {
        title: '供应商如何与杏林丹心进行合作？',
        answer: ['供应商如何与杏林丹心进行合作？'],
      },
      {
        title: '医院如何与杏林丹心进行合作？',
        answer: ['医院如何与杏林丹心进行合作？ '],
      },
      {
        title: '合作流程详解',
        answer: ['合作流程详解'],
      },
      {
        title: '合作方式有几种？',
        answer: ['合作方式有几种？'],
      },
      {
        title: '与杏林丹心进行合作会有怎样的收益？',
        answer: ['与杏林丹心进行合作会有怎样的收益？'],
      },
    ],
  },
])
const clickSecondMenu = (value: news) => {
  console.log(value)
  activeMenu.value = value.title
  letterName.value = value.title
}
const submitForm = async (formEl: FormInstance | undefined) => {
  if (!formEl) return
  await formEl.validate((valid, fields) => {
    if (valid) {
      console.log('submit!')
      activeMenu.value = 'finished'
    } else {
      console.log('error submit!', fields)
    }
  })
}
const resetForm = (formEl: FormInstance | undefined) => {
  if (!formEl) return
  formEl.resetFields()
}
const imgHandleChange = () => {
  fileList.slice(-5)
}
</script>
<style lang="scss" scoped>
.adviceandHelp {
  .form_box {
    width: 70%;
    margin: 40px auto;

    ::v-deep(.el-form-item__label) {
      height: 24px;
      font-size: 24px;
      font-weight: 400;
      color: #333333;
    }

    ::v-deep(.el-input__inner) {
      height: 40px;
      line-height: 40px;
    }

    .foot-btn {
      .el-button {
        width: 240px;
        height: 60px;
        border-radius: 10px;
        margin: 20px 40px;
        font-size: 24px;
        font-weight: 400;
      }

      .el-button--primary {
        background: #005bff;
      }
    }

    .upload-demo {
      border-radius: 4px;
      border: 1px solid #dcdfe6;
      display: flex;
      flex-direction: row-reverse;
      justify-content: space-between;
      flex: 1;

      .el-upload__tip {
        flex-grow: 1;
        color: #606266;
      }
    }
  }

  .question {
    ::v-deep(.el-tab-pane) {
      width: 90%;
      margin: auto;
    }

    ::v-deep(.el-tabs__active-bar) {
      width: 120px !important;
    }

    ::v-deep(.el-tabs__item) {
      font-size: 24px;
      font-family: FZLanTingHei-DB-GBK;
      font-weight: 400;
      color: #333333;
      line-height: 60px;
      height: 60px;
      width: 120px !important;
      text-align: center;
    }

    ::v-deep(.el-collapse-item__header) {
      font-size: 20px;
      font-family: FZLanTingHeiS-EL-GB;
      font-weight: 400;
      color: #333333;
      height: 72px;
      line-height: 72px;
    }

    .answer_row {
      display: flex;
      font-size: 16px;
      font-family: FZLanTingHeiS-EL-GB;
      font-weight: 400;
      color: #666666;
      line-height: 27px;
    }

    .more {
      float: right;
      height: 30px;
      line-height: 30px;
      font-size: 16px;
      color: #005bff;
      cursor: pointer;
    }
  }

  .overimg {
    height: 600px;
    text-align: center;
    font-size: 18px;

    image {
      width: auto;
      height: 430px;
    }

    p {
      font-size: 28px;
      font-weight: 500;
      color: #333333;
      margin: 20px 0;
    }
  }
}
</style>
