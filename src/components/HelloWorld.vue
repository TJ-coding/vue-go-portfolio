<template>
  <div id="ProjectPage" class="menu">
    <div class="card" v-for="project in projects" :key="project.id">
      <div class="thumb-nail" style="position: relative; display: inline-block">
        <img src="https://tj-coding.info/resource/career-thumbnail.gif">
        <span class="title">{{project.title}}</span>
      </div>
      <div class="content">
        <span class="subtitle">{{project.subTitle}}</span>
        <br>
        <br>
        <div class="float-wrap" style="text-align: center">
          <div class="right">
            <div class="description">{{project.description}}</div>
          </div>
          <div class="left technology">
            {{project.programmingLanguage}}
            <ul v-for="(technology,index) in project.technologies" :key="index">
              <li>{{technology}}</li>
            </ul>
          </div>
        </div>
        <div class="button-wrap">
          <button
            class="button button-primary"
            onclick="window.location.href='{{project.pageURL}}'"
          >Visit page</button>
          <span class="date">June, 2019</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectPage",
  props: {
    projects: Array
  }
};
</script>

<style>
html {
  background-color: red;
}
</style>
