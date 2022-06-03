<template>
  <AppColorful></AppColorful>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import AppColorful from "@/views/AppColorful.vue";

@Options({
  components: {
    AppColorful,
  },
})
export default class App extends Vue {}
</script>
