<template>
    <div>
    <button @click="openModal">Open Chat</button>

    <ChatModal ref="chatModal" />
  </div>
</template>

<script>
import ChatModal from "@/components/ChatModal.vue";

export default {
  methods: {
    openModal() {
      this.$refs.chatModal.showModal = true;
    },
  },
  components: {
    ChatModal,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
