<template>
  <div class="home">
    <div class="headerAndFooter header">
      <div class="headerBlock headerLeft" @click="toggleImage">
        <font-awesome-icon :icon="['fas', 'image']" />
      </div>

      <div class="headerBlock name">Nikolaus Koopmann</div>
      <div class="headerBlock headerRight">
        <a href="https://www.linkedin.com/in/nikolaus-koopmann-447444107/"
          ><font-awesome-icon :icon="['fab', 'linkedin']"
        /></a>
      </div>
    </div>
    <div v-if="showImg" class="content">
      <img src="@/assets/images/niko.png" />
    </div>
    <div class="headerAndFooter footer">
      <div class="headerBlock headerLeft">
        <a href="mailto:nikolauskoopmann@gmail.com"
          ><font-awesome-icon :icon="['fas', 'envelope']"
        /></a>
      </div>
      <router-link to="cv" class="headerBlock headerRight">cv</router-link>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Options({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {
  private showImg = false;
  private windowWidth: number = window.innerWidth;

  toggleImage() {
    this.showImg = !this.showImg;
    console.log(this.showImg);
  }

  get mobile(): boolean {
    return this.windowWidth < 1000;
  }

  created() {
    this.showImg = this.mobile;
  }

  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
    });
  }

  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  }

  onResize() {
    this.windowWidth = window.innerWidth;
    this.showImg = this.mobile;
  }
}
</script>
<style type="text/css">
.home {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: black;
}

.headerAndFooter {
  font-family: MoonGlade, PixoReto, Roboto, Lato, Arial, serif;
  width: 100%;
  display: flex;
  justify-content: space-between;
  font-size: x-large;
}

.header {
  position: fixed;
  padding-top: 0.5em;
}

.footer {
  position: fixed;
  padding-bottom: 0.5em;
  bottom: 0;
}

.headerBlock {
  display: inline-block;
}

.headerLeft {
  padding-left: 1em;
}

.headerRight {
  padding-right: 1em;
}

.content {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0.4;
  pointer-events: none;
}

@media all and (max-width: 1000px) {
  .content {
    float: right;
  }
}
.name {
  font-size: large;
}
</style>
