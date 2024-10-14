<template>
  <form @submit.prevent="submitProduct">
    <div class="form-group">
      <label for="name">Product Name:</label>
      <input
        v-model="product.name"
        type="text"
        id="name"
        class="form-control"
        placeholder="Enter product name"
        required
      />
    </div>

    <div class="form-group">
      <label for="price">Price:</label>
      <input
        v-model="product.price"
        type="number"
        id="price"
        class="form-control"
        placeholder="Enter product price"
        required
      />
    </div>

    <div class="form-group">
      <label for="description">Description:</label>
      <textarea
        v-model="product.description"
        id="description"
        class="form-control"
        placeholder="Enter product description"
        required
      ></textarea>
    </div>

    <button type="submit" class="btn btn-primary mt-3">Add Product</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      product: {
        name: '',
        price: '',
        description: ''
      }
    };
  },
  methods: {
    submitProduct() {
      this.$emit('add-product', { ...this.product });

      this.product.name = '';
      this.product.price = '';
      this.product.description = '';
    }
  }
};
</script>

<style scoped>
.form-group {
  margin-bottom: 15px;
}

.form-control {
  padding: 10px;
  font-size: 16px;
}

.btn-primary {
  background-color: #007bff;
  border: none;
  padding: 10px 15px;
  font-size: 16px;
}

.btn-primary:hover {
  background-color: #0056b3;
}
</style>
