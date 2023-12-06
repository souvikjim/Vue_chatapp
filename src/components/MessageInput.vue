<template>
  <div class="message-input">
    <input v-model="newMessage" @keyup.enter="sendMessage" placeholder="Type your message..." />
    <button @click="sendMessage">Send</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newMessage: "",
    };
  },
  methods: {
    sendMessage() {
      this.$emit("send", this.newMessage);
      this.newMessage = "";
    },
  },
};
</script>

<style scoped>
.message-input {
  display: flex;
  width: 97%; /* Adjust the width as needed */
  max-width: 600px; /* Adjust the max-width as needed */
  margin-top: -17px; /* Add margin to separate from the MessageList */
}

.message-input input {
  flex: 1;
  padding: 8px;
  margin-right: 10px;
  overflow-wrap: break-word;
}

.message-input button {
  padding: 8px 12px;
  cursor: pointer;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
}
</style>
