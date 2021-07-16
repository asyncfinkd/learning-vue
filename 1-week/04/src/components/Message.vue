<template>
  <h1>{{ messageText }}</h1>
</template>

<script>
export default {
  name: "Message",
  props: {
    messageText: String,
  },
};
</script>