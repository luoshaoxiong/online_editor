<template>
  <div id="app" class="clearfix">
    <top-bar></top-bar>
    <editor :message="message" :skills="skills" :experiences="experiences" :educations="educations" :prices="prices"></editor>
    <preview :message="message" :skills="skills" :experiences="experiences" :educations="educations" :prices="prices"></preview>
  </div>
</template>

<script>
import topBar from './views/top_bar';
import editor from './views/editor';
import preview from './views/preview';
import reset from './assets/reset.css';
import common from './assets/common.css';
import iconfont from './assets/font/iconfont/iconfont.css';

export default {
  name: 'App',
  components: {
    topBar,
    editor,
    preview
  },
  data() {
    return {
      message: {
        name: '',
        sex: '',
        prefer: '',
        education: '',
        city: '',
        workingYears: '',
        phone: '',
        email: ''
      },
      skills: [
        {description: ''}
      ],
      prices: [
        {description: ''}
      ],
      educations: [
        {description: ''}
      ],
      experiences: [
        {
          company: '',
          works: ''
        }
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
}
</style>
