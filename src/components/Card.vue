<template>
  <div
    class="card-wrapper"
    :style="`border-top: 5px solid ${colorHash[color]};`"
  >
    <div class="title">{{ title }}</div>
    <div class="description">{{ description }}</div>
    <img :src="getImageUrl" :alt="title" />
  </div>
</template>

<script>
export default {
  name: "Category",
  props: {
    color: {
      type: String,
      require: true,
    },
    title: {
      type: String,
      require: true,
    },
    description: {
      type: String,
      require: true,
    },
  },
  data() {
    return {
      colorHash: {
        red: "hsl(0, 78%, 62%)",
        cyan: "hsl(180, 62%, 55%)",
        orange: "hsl(34, 97%, 64%)",
        blue: "hsl(212, 86%, 64%)",
      },
    };
  },
  computed: {
    getImageUrl() {
      const iconName = this.title
        .split(" ")
        .map((word) => word.toLowerCase())
        .join("-");
      return require(`@/assets/icon-${iconName}.svg`);
    },
  },
};
</script>

<style lang="scss" scoped>
.card-wrapper {
  background-color: #fff;
  border-radius: 5px;
  padding: 20px 15px;
  width: 311px;
  height: 202px;
  box-shadow: 0 10px 20px hsl(229, 6%, 66%);
  .title {
    color: hsl(234, 12%, 34%);
    font-weight: 600;
    font-size: 1.5rem;
  }
  .description {
    margin-top: 10px;
    font-size: 0.8rem;
  }
  img {
    margin-top: 25px;
    width: 50px;
    float: right;
  }
}
@media (max-width: 375px) {
  .card-wrapper {
    margin-top: 20px;
    width: 270px;
    height: 157px;
    .title {
      font-size: 1.1rem;
    }
    .description {
      font-size: 0.7rem;
    }
  }
}
</style>