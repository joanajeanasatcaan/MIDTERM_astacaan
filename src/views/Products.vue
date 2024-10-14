<template>
  <div>
    <ProductForm @add-product="addProduct" />
    <ProductList :products="products" @edit-product="editProduct" />
  </div>
</template>

<script>
import ProductForm from '../components/ProductForm.vue';
import ProductList from '../components/ProductList.vue';

export default {
  components: { ProductForm, ProductList },
  data() {
    return {
      products: []
    };
  },
  methods: {
    addProduct(newProduct) {
      this.products.push(newProduct);
    },
    editProduct({ index, product }) {
      this.$set(this.products, index, product);
    }
  }
};
</script>
