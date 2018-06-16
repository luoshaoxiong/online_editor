<template>
  <div class="preview" v-show="false">
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
      <span slot="tag">教育经历</span>
      <div slot="content" class="clearfix">
        <ol style="margin-left: 35px">
          <li v-for="item in skills">{{item.description}}</li>
        </ol>
      </div>
    </preview-section>
    <preview-section>
      <span slot="tag">获奖情况</span>
      <div slot="content" class="clearfix">
        <ol style="margin-left: 35px">
          <li v-for="item in skills">{{item.description}}</li>
        </ol>
      </div>
    </preview-section>
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
</style>
