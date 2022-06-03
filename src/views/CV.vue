<template>
  <div class="slickFont CVletters">
    CV
  </div>
  <SlickCV :resume="resume" :style="colormapStyle" class="slickcv"></SlickCV>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import resumeData from "@/assets/resume.json";
import SlickCV from "@/components/slickCV/SlickCV.vue";
import { Prop } from "vue-property-decorator";

@Options({
  components: {
    SlickCV
  }
})
export default class CV extends Vue {
  @Prop({ required: true }) firstColor!: string;
  private resume: Record<string, any> = {};

  get colormapStyle(): Record<string, any> {
    return { backgroundImage: `linear-gradient(${this.firstColor}, #fdd279, #acc172, #67a77a, #36897e, #286873, #2f4858)`,
    backgroundColor: this.firstColor};
  }


  created() {
    this.resume = resumeData;
  }
}
</script>
<style>

.slickcv {
  font-family: Montserrat, Lato, Roboto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/
  /*background-color: #594f4f;*/
  /*background-image: linear-gradient(*/
  /*  !*#ffba44,*! !*#c3ff61,*!*/
  /*  #000000,*/
  /*  #fdd279,*/
  /*  #acc172,*/
  /*  #67a77a,*/
  /*  #36897e,*/
  /*  #286873,*/
  /*  #2f4858*/
  /*  !*#000000,*! !*#594f4f,*! !*#45ada8,*! !*#547980,*! !*#594f4f,*! !*#000f32*!*/
  /*);*/
  max-width: 100vw;
}

.CVletters {
  font-weight: bolder;
  font-size: 2em;
  margin-top: 3em;
  margin-bottom: 1em;
}

</style>
