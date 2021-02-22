<template>
  <div>
    <div class="col-2 offset-5">
      <img :src="myphoto" alt="" class="img-fluid" />
    </div>
    <h1 class="col-12 text-center mt-5">{{ name }}</h1>
    <div class="d-flex justify-content-center align-items-center">
      <button class="btn btn-info mr-5" @click="onCountAdd">請按讚</button>
      <p class="m-0">按讚次數:{{ showCount }}</p>
    </div>
    <Skill :skill="skill" @onSkillShow="onSkillShow" />
    <SkillDetail :skillId="some" />
  </div>
</template>


<script>
import Skill from "./Skill.vue";
import SkillDetail from "./SkillDetail.vue";

export default {
  components: { Skill, SkillDetail },
  name: "HelloWorld",
  data() {
    return {
      name: "陳孟妤",
      myphoto: require("../assets/me.png"),
      some: "",
      skill: [
        {
          id: 1,
          name: "html",
          content: "很棒",
        },
        {
          id: 2,
          name: "css",
          content: "還好",
        },
        {
          id: 3,
          name: "javascript",
          content: "超級讚的啦",
        },
      ],
    };
  },
  computed: {
    showCount() {
      return this.$store.state.count;
    },
  },
  methods: {
    onSkillShow(value) {
      this.some = value;
      console.log(this.some);
    },
    onCountAdd() {
      this.$store.commit("addCount");
    },
  },
  mounted() {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
