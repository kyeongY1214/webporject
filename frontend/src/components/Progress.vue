<template>
  <div class="progress-container progress-base" :class="`progress-${type}`">
    <span class="progress-badge">
      <slot name="label">
        {{ label }}
      </slot>
    </span>
    <slot>
      <span class="progress-value" v-if="showValue"> {{ value }}% </span>
    </slot>
    <div class="progress mr-2" :style="`height: ${height}px`">
      <div
        class="progress-bar ml-2"
        :class="computedClasses"
        role="progressbar"
        :aria-valuenow="value"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="`width: ${value}%;`"
      ></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "n-progress",
  props: {
    striped: Boolean,
    showValue: Boolean,
    animated: Boolean,
    label: String,
    height: {
      type: Number,
      default: 3,
    },
    type: {
      type: String,
      default: "default",
    },
    value: {
      type: Number,
      default: 0,
      validator: (value) => {
        return value >= 0 && value <= 100;
      },
    },
  },
  computed: {
    computedClasses() {
      return [
        { "progress-bar-striped": this.striped },
        { "progress-bar-animated": this.animated },
      ];
    },
  },
};
</script>
<style></style>
