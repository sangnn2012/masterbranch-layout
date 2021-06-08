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
        <!-- <Card
          v-for="card of cards"
          :key="`card-${card.title}`"
          :color="card.color"
          :title="card.title"
          :description="card.description"
        /> -->
        <Card
          class="card-1"
          :color="cards[0].color"
          :title="cards[0].title"
          :description="cards[0].description"
        />
        <div>
          <Card
            class="card-2"
            :color="cards[1].color"
            :title="cards[1].title"
            :description="cards[1].description"
          />
          <Card
            class="card-3"
            :color="cards[2].color"
            :title="cards[2].title"
            :description="cards[2].description"
          />
        </div>
        <Card
          class="card-4"
          :color="cards[3].color"
          :title="cards[3].title"
          :description="cards[3].description"
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
  computed: {
    screenWidth() {
      return window.innerWidth;
    },
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
  box-sizing: border-box;
}

#app {
  background-color: hsl(0, 0%, 98%);
  color: hsl(229, 6%, 66%);
  width: 100%;
  height: 100%;
  .app-wrapper {
    padding: 40px 55px;
    .card-3 {
      margin-top: 45px;
    }
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
      justify-content: space-evenly;
      align-items: center;
    }
  }
}
@media (max-width: 375px) {
  #app {
    .app-wrapper {
      padding: 40px 30px;
      .card-3 {
        margin-top: 20px;
      }
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
