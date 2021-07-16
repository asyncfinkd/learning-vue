<template>
  <div>
    <h1 v-once>{{ messageText }}</h1>
  </div>
</template>

<script>
export default {
  name: "Message",
  props: {
    messageText: String,
  },
};
</script>