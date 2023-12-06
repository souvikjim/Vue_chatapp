<template>
  <div>
    <message-list :messages="messages" />
    <message-input @send="addMessage" />
  </div>
</template>

<script>
import MessageList from "@/components/MessageList.vue";
import MessageInput from "@/components/MessageInput.vue";

export default {
  components: {
    MessageList,
    MessageInput,
  },
  data() {
    return {
      messages: [
        { id: 1, sender: "User", text: "Hello!" },
        { id: 2, sender: "Bot", text: "Hi there!" },
      ],
    };
  },
  methods: {
    addMessage(newMessage) {
      this.messages.push({ id: this.messages.length + 1, sender: "User", text: newMessage });
      // Simulate a bot response (you can replace this with actual API calls)
      this.messages.push({ id: this.messages.length + 1, sender: "Bot", text: "I received your message!" });
    },
  },
};
</script>
