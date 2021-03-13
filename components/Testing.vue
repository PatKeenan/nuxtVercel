<template>
  <div>
    <button class="btn " :class="{ 'btn-blue': isActive }">Testing</button>
    <button
      class="btn bg-green-300"
      v-on:click="
        {
          sayHi();
        }
      "
    >
      {{ testing }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Test",
  created() {},
  data() {
    return {
      isActive: false
    };
  },
  props: ["testing"],
  methods: {
    sayHi() {
      this.isActive = !this.isActive;
      console.log("worked");
    }
  }
};
</script>

<style lang="postcss" scoped>
.btn {
  @apply font-bold py-2 px-4 rounded transition ease-in-out duration-200 shadow-lg;
  outline: none;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-gray-500;
}
.btn:active {
  transform: scale(0.9);
}
</style>
