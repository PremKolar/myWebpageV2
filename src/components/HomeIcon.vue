<template>
  <div class="btn" @click="$emit('clicked')">
    <font-awesome-icon size="lg" :icon="['fas', icon]" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { Prop } from "vue-property-decorator";

@Options({
  components: {},
})
export default class HomeIcon extends Vue {
  @Prop({ required: true }) icon!: string;

}
</script>
<style scoped>
.btn {
  cursor: pointer;
}
</style>
