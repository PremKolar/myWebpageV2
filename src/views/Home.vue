<template>
  <div class="home">


    <!--   Baustelle -->
<!--    <div-->
<!--      style="-->
<!--        display: flex;-->
<!--        flex-direction: column;-->
<!--        justify-content: center;-->
<!--        align-items: center;-->
<!--        width: 100%;-->
<!--        height: 100%;-->
<!--        position: absolute;-->
<!--      "-->
<!--    >-->
<!--      <div style="font-size: xx-large">Under Construction</div>-->
<!--      <div style="font-size: large">(rebuilding the entire site)</div>-->
<!--    </div>-->
    <!--    -->



    <div class="content" :style="{ opacity: opacity }" @mousemove="calcOpacity">
      <img
        class="image"
        src="@/assets/images/goldenIndo.jpg"
        alt="me and iceberg"
        :class="{ driftImg: mobile }"
      />
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
  private opacity = 0;
  private maxOpacity = 0.5;
  private opacityMobile = 0.3;

  get mobile(): boolean {
    return this.windowWidth < 1000;
  }

  calcOpacity(event: { clientX: number; clientY: number }): void {
    if (this.mobile) {
      this.opacity = this.opacityMobile;
      return;
    }
    let x_contribution = Math.sin(
      (event.clientX * Math.PI) / window.innerWidth
    );
    let y_contribution = Math.sin(
      ((event.clientY + window.scrollY) * Math.PI) / window.innerHeight
    );
    this.opacity = this.maxOpacity * x_contribution * y_contribution;
  }

  created() {
    this.showImg = this.mobile;
  }

  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
    });
    if (this.mobile) this.opacity = this.opacityMobile;
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
<style type="text/css" scoped>
.home {
  /*position: fixed;*/
  height: 100vh;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: black;
  max-width: 100vw;
  overflow: hidden;
}

.content {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  /*opacity: 0.4;*/
  float: inherit;
  overflow: hidden;
}

.driftImg {
  animation: drift 30s;
}

@keyframes drift {
  0% {
    -webkit-transform: translateX(650px);
    transform: translateX(650px);
  }
  100% {
    -webkit-transform: translateX(0);
    transform: translateX(0);
  }
}

@media all and (max-width: 1000px) {
  .content {
    float: right;
  }
}

.image {
  /*object-fit: scale-down;*/
  /*width: 100vw;*/
  overflow: hidden;
}
</style>
