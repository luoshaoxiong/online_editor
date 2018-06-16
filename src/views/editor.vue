<template>
  <div class="editor clearfix" v-show="show.editor">
    <nav>
      <ul>
        <li v-for="(item, index) in icon" :class="{'active': currentIndex===index}" @click="choosePanel(index)">
          <i class="icon iconfont" :class="[`icon-${item}`]"></i>
        </li>
      </ul>
    </nav>
    <main class="editor-panel">
      <user-message :form="message" v-show="currentIndex===0"></user-message>
      <skill :skills="skills" v-show="currentIndex===1"></skill>
      <work-experience :experiences="experiences" v-show="currentIndex===2"></work-experience>
      <education :educations="educations" v-show="currentIndex===3"></education>
      <price :prices="prices" v-show="currentIndex===4"></price>
    </main>
  </div>
</template>

<script>
  import userMessage from './user_message';
  import skill from './skill';
  import workExperience from './work_experience';
  import price from './price';
  import education from './education';

  export default {
    name: "editor",
    components: {userMessage, skill, workExperience, price, education},
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
        icon: [
          'shenfenzheng',
          'xiangmu',
          'gongzuojingyan',
          'drxx18',
          'price'
        ],
        currentIndex: 0
      }
    },
    methods: {
      choosePanel(index) {
        this.currentIndex = index;
      }
    }
  }
</script>

<style scoped>
  .editor {
    float: left;
    width: 40%;
    height: calc(100% - 80px);
    background-color: #fff;
  }
  nav {
    float: left;
    height: 100%;
    width: 80px;
  }
  nav>ul {
    width: 80px;
    background-color: #111;
    color: #fff;
    height: 100%;
  }
  nav>ul>li {
    height: 60px;
    padding: 20px 0;
    text-align: center;
  }
  nav>ul>li:hover,
  nav>ul>li.active {
    background-color: #409EFF;
  }
  nav>ul>li>i {
    font-size: 20px;
  }
  .editor-panel {
    float: left;
    width: calc(100% - 80px);
    height: 100%;
    overflow: auto;
    padding: 10px 30px;
  }
</style>
