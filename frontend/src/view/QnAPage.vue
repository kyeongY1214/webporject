<template >
  <div class="app" v-bind:style="{ background: color }">
    <div class="container">
      <div class="col-md-8 ml-auto mr-auto">
        <newQnAProgress />
      </div>
    </div>
  </div>
</template>

<script>
import newQnAProgress from "../pages/components/newQnAProgress.vue";

export default {
  data() {
    return {
      color: "linear-gradient(0deg,rgba(44,44,44,.2),rgba(224,23,3,.6))",
    };
  },
  methods: {},
  components: {
    newQnAProgress,
  },
};
</script>
<style scope>
.app {
  display: flex;
  height: 100%;
  width: 100%;
  justify-content: center;
  align-items: center;
  left: 50%;
  top: 50%;
  text-align: center;
}
</style>
