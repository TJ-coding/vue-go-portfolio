<template>
  <div id="ProjectPage" class="menu">
    <div class="card" v-for="project in projects" :key="project.id">
      <div class="thumb-nail" style="position: relative; display: inline-block">
        <img v-bind:src="project.thumbNailURL">
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
          <button class="button button-primary" v-bind:onclick="project.thumbNailURL">Visit page</button>
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
  padding: 0px;
}
body {
  background-color: #3A4861;
  color: #F0F0F0;
  font-family: "Roboto Condensed", sans-serif;
  padding: 0px;
  margin: 0px;
}
.section-title {
  text-align: center;
  margin: 0px;
  padding: 0px;
  --background-color: #2B618F;
}
.menu {
  padding-top: 1rem;
  width: auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(10rem, 25rem));
  grid-auto-rows: 1fr;
  grid-gap: 3rem;
  justify-content: center;
}
.menu .card {
  background-color: #292934;
  border-radius: 0.5rem;
  width: 100%;
  max-width: 90vw;
  height: auto;
  margin: auto;
  margin: auto;
  padding: 0;
}
.card .thumb-nail {
  width: 100%;
  overflow: hidden;
}
.card .thumb-nail > img {
  border-radius: 0.5rem;
  min-width: 100%;
  min-height: 40%;
  max-height: 15rem;
  height: auto;
  object-fit: cover;
}
.card .thumb-nail .title {
  position: absolute;
  bottom: 0px;
  left: 0px;
  width: 100%;
  opacity: 0.86;
  background-color: #BADBC7;
  padding-left: 1rem;
  font-size: 1.5rem;
  color: #223546;
}
.card .content {
  padding: 1rem;
  color: #767676;
}

.card .float-wrap {
  display: inline-block;
  width: 100%;
}
.card .float-wrap > .left {
  float: left;
}
.card .float-wrap > .right {
  float: right;
  width: 70%;
}
.card ul {
  list-style-type: none;
  margin: 0;
  margin-left: 1rem;
  padding: 0;
}
.card .subtitle {
  color: #F0F0F0;
}
.card .technology {
  width: 29%;
  border-right: 1px solid gray;
  text-align: left;
}

.card .description {
  padding: 1rem;
  padding-top: 0rem;
  word-wrap: break-word;
  text-align: left;
}

.card .date {
  position: absolute;
  right: 0px;
  bottom: 0px;
  font-size: 0.8rem;
  font-weight: 100;
}

.card .button-wrap {
  text-align: center;
  position: relative;
  display: inline-block;
  width: 100%;
}

.button {
  cursor: pointer;
  border-style: solid;
  border-width: 2px 2px 2px 2px;
  border-color: var(--button-color);
  color: var(--button-color);
  text-align: center;
  padding: 0.5rem;
  background-color: rgba(0, 0, 0, 0);
}
.menu .button:hover {
  box-shadow: inset 0 -3.25em 0 0 var(--button-color);
  color: white;
  transition: 0.25s;
}

.button-primary {
  --button-color: #6AA89D;
}
.button-secondary {
  --button-color: #89ACD7;
}

@media screen and (max-width: 600px) {
  .card .technology {
    display: none;
    width: 0px;
  }
  .card .date {
    display: none;
  }
  .card .description {
    word-break: break-word;
    text-align: center;
  }
  .card .float-wrap > .right {
    width: 100%;
  }
}
</style>
