<template>
  <div id="app">
    <div class="app-wrapper">
      <div class="header">
        <div class="header__main header__main-thin">
          Reliable, efficient delivery
        </div>
        <div class="header__main header__main-bold">Powered by Technology</div>
        <div class="description" v-html="description"></div>
      </div>
      <div class="cards-wrapper">
        <Card
          v-for="card of cards"
          :key="`card-${card.title}`"
          :color="card.color"
          :title="card.title"
          :description="card.description"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "App",
  components: {
    Card,
  },
  data() {
    return {
      description: `Our Artificial Intelligence powered tools use millions of project data points to ensure that your project is successful`,
      cards: [
        {
          color: "cyan",
          title: "Supervisor",
          description: "Monitors activity to identify project roadblocks",
        },
        {
          color: "red",
          title: "Team Builder",
          description:
            "Scans our talent network to create the optimal team for your project",
        },
        {
          color: "orange",
          title: "Karma",
          description: "Regularly evaluates our talents to ensure quality",
        },
        {
          color: "blue",
          title: "Calculator",
          description:
            "Uses data from past projects to provide better delivery estimates",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
html,
body {
  width: 100%;
  height: 100%;
  margin: 0;
  overflow-x: hidden;
  font-family: "Poppins", sans-serif;
  font-size: 15px;
  font-weight: 400;
}

#app {
  background-color: hsl(0, 0%, 98%);
  color: hsl(229, 6%, 66%);
  width: 100%;
  height: 100%;
  .app-wrapper {
    padding: 40px 35px;
    .header {
      text-align: center;
      &__main {
        font-size: 2rem;
        color: hsl(234, 12%, 34%);
        &-thin {
          font-weight: 200;
        }
        &-bold {
          font-weight: 600;
          margin-top: 5px;
        }
      }
      .description {
        margin-top: 12px;
      }
    }
    .cards-wrapper {
      display: flex;
      margin-top: 30px;
    }
  }
}
@media (max-width: 375px) {
  #app {
    .app-wrapper {
      .header {
        &__main {
          font-size: 1.3rem;
        }
        .description {
          font-size: 0.8rem;
        }
      }
      .cards-wrapper {
        display: flex;
        flex-direction: column;
      }
    }
  }
}
</style>
