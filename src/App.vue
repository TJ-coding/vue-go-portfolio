<template>
  <div id="app">
    <HelloWorld v-bind:projects="projects"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      projects: [
        {
          id: 0,
          thumbNailURL: "https://tj-coding.info/resource/career-thumbnail.gif",
          title: "Natural language processing",
          subTitle: "NLP",
          description:
            "Suitable career path for the fictional character Tintin was found using NLP techniques. The program was then used on myself to determine suitable career path.",
          programmingLanguage: "Python",
          technologies: ["NLTK", "GloVe", "Word2vec"],
          pageURL: "https://tj-coding.info/projectPage/career/index.html"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
