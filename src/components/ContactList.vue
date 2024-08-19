<script>
export default {
props: {
contacts: { type: Array, default: [] },
activeIndex: { type: Number, default: -1 },
},
emits: ["update:activeIndex"],
methods: {
updateActiveIndex(index) {
this.$emit("update:activeIndex", index);
}
}
};
</script>

<template>
  <ul class="divide-y divide-gray-200 space-y-2">
    <li
      class="p-4 cursor-pointer rounded-[10px] "
      v-for="(contact, index) in contacts"
      :key="contact._id"
      :class="index === activeIndex ? 'bg-blue-500 text-white' : ' text-gray-900 bg-gray-100 hover:bg-gray-200'"
      @click="updateActiveIndex(index)"
    >
      {{ contact.name}}
    </li>
  </ul>
</template>