<template>
  <SlickCV :resume="resume" class="slickcv"></SlickCV>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import resumeData from "@/assets/resume.json";
import SlickCV from "@/components/slickCV/SlickCV.vue";

@Options({
  components: {
    SlickCV,
  },
})
export default class CV extends Vue {
  private resume: Record<any, any> = {};
  created() {
    this.resume = resumeData;
  }
}
</script>
<style type="text/css">


.slickcv {
  padding-top: 5em;
  font-family: Montserrat, Lato, Roboto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/
  background-color: #594f4f;
  background-image: linear-gradient(
    /*#ffba44,*/
    /*#c3ff61,*/
    #9de0ad,
    #45ada8,
    #547980,
    #594f4f,
    #000f32
  );
}



</style>
