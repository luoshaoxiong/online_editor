<template>
  <div :class="[show.preview ? 'previewing' : 'preview']">
    <header>
      <h1>个人简历</h1>
      <span class="split">|</span>
      <span>Personal Resume</span>
    </header>
    <preview-section>
      <span slot="tag">基本信息</span>
      <div slot="content" class="clearfix">
        <div class="message_item" v-for="(item, index) in message">
          <span class="message-tag">{{messageTag[index]}}</span>：{{item}}
        </div>
      </div>
    </preview-section>
    <preview-section>
      <span slot="tag">技能描述</span>
      <div slot="content" class="clearfix">
        <ol style="margin-left: 35px">
          <li v-for="item in skills">{{item.description}}</li>
        </ol>
      </div>
    </preview-section>
    <preview-section>
      <span slot="tag">工作经历</span>
      <div slot="content" class="clearfix">
        <ul class="experiences">
          <li v-for="item in experiences">
            {{item.description}}
            <p>公司名称：{{item.company}}</p>
            <p>工作内容：{{item.works}}</p>
          </li>
        </ul>
      </div>
    </preview-section>
    <preview-section>
      <span slot="tag">教育经历</span>
      <div slot="content" class="clearfix">
        <ol style="margin-left: 35px">
          <li v-for="item in educations">{{item.description}}</li>
        </ol>
      </div>
    </preview-section>
    <preview-section>
      <span slot="tag">获奖情况</span>
      <div slot="content" class="clearfix">
        <ol style="margin-left: 35px">
          <li v-for="item in prices">{{item.description}}</li>
        </ol>
      </div>
    </preview-section>
    <el-button class="exit-preview" type="primary" v-show="show.preview" @click="exitPreview">退出预览</el-button>
  </div>
</template>

<script>
  import previewSection from './preview_section';

  export default {
    name: "preview",
    components: {previewSection},
    props: {
      message: {
        type: Object
      },
      skills: {
        type: Array
      },
      prices: {
        type: Array
      },
      educations: {
        type: Array
      },
      experiences:{
        type: Array
      },
      show: {
        type: Object
      }
    },
    data() {
      return {
        messageTag: {
          name: '姓名',
          sex: '性别',
          education: '学历',
          city: '城市',
          prefer: '求职意向',
          workingYears: '工作年限',
          phone: '联系电话',
          email:'邮箱'
        }
      }
    },
    methods: {
      exitPreview() {
        this.show.topBar = true;
        this.show.editor = true;
        this.show.preview = false;
      }
    }
  }
</script>

<style scoped>
  .preview {
    float: left;
    width: 60%;
    height: calc(100% - 80px);
    border-left: 1px solid #aaa;
    margin-top: -2px;
    padding-bottom: 30px;
    overflow: auto;
    background-color: #fff;
  }
  .previewing {
    width: 60%;
    border: 1px solid #aaa;
    margin: 20px 20%;
    background-color: #fff;
    padding-bottom: 30px;
  }
  header {
    padding: 30px 50px;
  }
  header>h1 {
    display: inline-block;
    color: #0186b3;
  }
  header>.split {
    margin: 0 5px;
    font-size: 2.5em;
    color: #0186b3;
  }
  .message_item {
    float: left;
    width: calc(50% - 40px);
    margin: 5px 20px;
  }
  .message-tag {
    text-align: justify;
  }
  .experiences {
    margin-top: 15px;
    margin-bottom: 5px;
    margin-left: 24px;
    list-style: none;
  }
  .experiences p {
    line-height: 2em;
  }
  .experiences li {
    position: relative;
    padding-bottom: 10px;
    padding-left: 11px;
    border-left: 2px solid #0186b3;
  }
  .experiences li::before {
    content: '';
    position: absolute;
    top: -10px;
    left: -6px;
    width: 10px;
    height: 10px;
    display: inline-block;
    border-radius: 50%;
    background-color: #0186b3;
  }
  .experiences li::after {
    content: '';
    position: absolute;
    bottom: 0px;
    left: -6px;
    width: 10px;
    height: 10px;
    display: inline-block;
    border-radius: 50%;
    background-color: #0186b3;
  }
  ol>li {
    line-height: 2em;
  }
  .exit-preview {
    position: fixed;
    right: 5%;
    top: 30px;
  }
</style>
