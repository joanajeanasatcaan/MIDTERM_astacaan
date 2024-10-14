<template>
  <ul>
    <li v-for="(product, index) in products" :key="index">
      <div v-if="editingIndex !== index">
        <span>{{ product.name }} - {{ product.price }} - {{ product.description }}</span>
        <button @click="startEditing(index)">Edit</button>
      </div>
      <div v-else>
        <input v-model="editProduct.name" type="text" required />
        <input v-model="editProduct.price" type="number" required />
        <textarea v-model="editProduct.description" required></textarea>
        <button @click="saveEdit(index)">Save</button>
        <button @click="cancelEdit">Cancel</button>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: ['products'],
  data() {
    return {
      editingIndex: null,
      editProduct: {
        name: '',
        price: null,
        description: ''
      }
    };
  },
  methods: {
    startEditing(index) {
      this.editingIndex = index;
      this.editProduct = { ...this.products[index] };
    },
    saveEdit(index) {
      this.$emit('edit-product', { index, product: this.editProduct });
      this.editingIndex = null;
    },
    cancelEdit() {
      this.editingIndex = null;
    }
  }
};
</script>
