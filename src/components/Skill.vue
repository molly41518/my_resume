<template>
  <div class="skill">
    <div class="row justify-content-center">
      <div
        v-for="(item, index) in skill"
        :key="index"
        class="col-3 card mr-1 ml-1"
      >
        <div class="card-body">
          <h5 class="card-title">{{ item.name }}</h5>
          <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
          <p class="card-text">
            {{ item.content }}
          </p>
          <a
            href="javascript:;"
            class="card-link btn btn-primary"
            @click="onSkillDetail(item.id)"
            >看更多</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "skill",
  props: ["skill"],
  methods: {
    onSkillDetail(id) {
      this.$emit("onSkillShow", id);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>