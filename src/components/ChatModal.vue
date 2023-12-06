<template>
  <div v-if="showModal" class="modal-overlay" @click="closeModal">
    <div class="modal-content" @click.stop>
      <button class="close-button" @click="closeModal">&times;</button>
      <ChatApp />
    </div>
  </div>
</template>

<script>
import ChatApp from "@/components/ChatApp.vue";

export default {
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    closeModal() {
      this.showModal = false;
    },
  },
  components: {
    ChatApp,
  },
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-content {
  position: relative;
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  max-width: 600px;
  width: 100%;
  max-height: 600px;
  height: 100%;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide the default scrollbar */
  display: flex;
  flex-direction: column;
}

.close-button {
  position: absolute;
  top: 2px;
  right: 2px;
  font-size: 18px;
  cursor: pointer;
  border: none;
  border-radius: 50%;
  color: black;
}

/* Ensure the MessageList takes the remaining space */
.message-list {
  flex: 1;
  overflow-y: auto; /* Add scrollbar if content overflows */
  margin-bottom: 10px; /* Adjust margin as needed */
  width:97%;
}

/* Keep MessageInput at the bottom */
.message-input {
  margin-top: auto;
}
</style>
