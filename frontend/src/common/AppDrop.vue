<template>
    <div
      @drop.stop="onDrop"
      @dragover.prevent
      @dragenter.prevent
    >
      <slot/>
    </div>
  </template>
  
  <script setup>
  import { DATA_TRANSFER_PAYLOAD } from "../constants.js"; 
  const emit = defineEmits(['drop']);
  
  function onDrop(event) {
    const { dataTransfer } = event;
    if (!dataTransfer) return;
    
    const payload = dataTransfer.getData(DATA_TRANSFER_PAYLOAD);
    if (payload) {
      const transferData = JSON.parse(payload);
      emit('drop', transferData);
    }
  }
  </script>
  
  <style>
  /* Add your styles here */
  </style>
  