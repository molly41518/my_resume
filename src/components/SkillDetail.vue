<template>
  <div class="skillDetail">
    <h1>{{ showInfo.info }}</h1>
  </div>
</template>

<script>
export default {
  name: "skillDetail",
  props: ["skillId"],
  data() {
    return {
      id: [],
      showSkillInfo: [],
      skillInfo: [
        {
          id: 1,
          info: "一定要會的技術",
        },
        {
          id: 2,
          info: "一定要會才有外觀",
        },
        {
          id: 3,
          info: "其實現在還不太會",
        },
      ],
    };
  },
  computed: {
    showInfo() {
      if (!this.skillId) return false;
      return this.skillInfo.find((item) => {
        return item.id == this.skillId;
      });
    },
  },
};
</script>

<style lang="scss" scoped>
</style>