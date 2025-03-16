<template>
  <div class="product-container">
    <img 
      :src="item.imageUrl ? 'http://localhost:8000' + item.imageUrl : defaultImage" 
      alt="Product Image" 
      class="product-image"
    />
    <div class="details-wrap">
      <h3>{{ item.name }}</h3>
      <p>Rp{{ item.price }}</p>
    </div>
    <button class="remove-button" @click="$emit('remove-item', item.code)">Remove</button>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      defaultImage: "https://via.placeholder.com/100" // Gambar default jika tidak ada imageUrl
    };
  }
};
</script>

<style scoped>
.product-container {
  display: flex;
  align-items: center;
  border-bottom: 1px solid #ddd;
  padding: 16px;
  width: 100%;
  background: #f9f9f9;
  border-radius: 8px;
  transition: background 0.3s ease;
}

.product-container:hover {
  background: #f1f1f1;
}

.product-image {
  flex: 1;
  height: 100px;
  max-width: 100px;
  border-radius: 8px;
}

.details-wrap {
  flex: 3;
  padding: 0 16px;
}

.remove-button {
  flex: 1;
  background-color: #dc3545;
  color: white;
  padding: 8px 12px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.remove-button:hover {
  background-color: #c82333;
}
</style>
