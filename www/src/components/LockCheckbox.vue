<template>
  <span>
    <input
      :id="id"
      type="checkbox"
      :checked="checked"
      @change="$emit('change', $event.target.checked)"
    >
    <label :for="id">
      <img
        :src="`${checked ? '/font-awesome/solid-lock.svg' : '/font-awesome/solid-lock-open.svg'}`"
        :alt="`${checked ? 'Locked padlock' : 'Unlocked padlock'}`"
      />
    </label>
  </span>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "LockCheckbox",

  model : {
    prop: 'checked',
    event: 'change'
  },

  props: {
    id: {
      type: String,
      required: true
    },
    checked: {
      type: Boolean,
      default: false
    }
  },

});
</script>

<style scoped>
input[type=checkbox] {
  display: none;
}

label img {
  cursor: pointer;
  height: 1em;
  width: 1em;
  vertical-align: baseline;
}
</style>
