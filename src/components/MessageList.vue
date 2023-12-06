<template>
  <div class="message-list" ref="messageList">
    <div v-for="message in messages" :key="message.id" :class="{ 'sent': message.sender === 'User', 'received': message.sender === 'Bot' }" class="message">
      <div class="message-content">
        <p class="message-text">{{ message.text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    messages: Array,
  },
  updated() {
    this.scrollToBottom();
  },
  methods: {
    scrollToBottom() {
      this.$refs.messageList.scrollTop = this.$refs.messageList.scrollHeight;
    },
  },
};
</script>

<style scoped>
.message-list {
  display: flex;
  flex-direction: column;
  overflow-y: auto; /* Enable vertical scrolling */
  max-height: 70vh; /* Set a max height or adjust as needed */
  margin-bottom:20px;
}

.message {
  display: inline-block;
  max-width: 70%; /* Adjust as needed */
  padding: 8px;
  border-radius: 8px;
  margin-bottom: 10px;
  border: 1px solid #ddd; /* Added border for better visibility */
}

.sent {
  align-self: flex-end;
  background-color: #4CAF50; /* Green or your preferred color */
  color: white;
}

.received {
  align-self: flex-start;
  background-color: #f1f1f1; /* Light gray or your preferred color */
}

.message-content {
  word-wrap: break-word; /* Prevent overflow in the message content */
}

.message-text {
  margin: 0; /* Remove default margin for better alignment */
}
.message-list::-webkit-scrollbar {
  width: 2px; /* Set the width of the scrollbar */
}

.message-list::-webkit-scrollbar-thumb {
  background-color: #888; /* Color of the thumb */
  border-radius: 4px; /* Radius of the thumb */
}

.message-list::-webkit-scrollbar-track {
  background-color: #eee; /* Color of the track */
}
</style>
