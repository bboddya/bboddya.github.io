<template>
  <!-- Через директиву v-for выполнен перебор массива данных с передачей параметров в дочерний компонент -->
  <div>
    <ul>
      <li v-for="(product, index) in products" :key="index">
        <ProductCard
          :code="product.code"
          :title="product.title"
          :priceGoldAlt="product.priceGoldAlt"
          :priceRetailAlt="product.priceRetailAlt"
          :priceGold="product.priceGold"
          :priceRetail="product.priceRetail"
          :productId="product.productId"
          :unitRatio="product.unitRatio"
          :unit="product.unit"
          :unitRatioAlt="product.unitRatioAlt"
          :unitAlt="product.unitAlt"
          :primaryImageUrl="product.primaryImageUrl"
          :assocProducts="product.assocProducts"
        />
      </li>
    </ul>
  </div>
</template>

<script>
/* Ипортирован json файл с данными + подключен дочерний компонент вывода карточки товара */
import ProductCard from "./ProductCard";
import json from "../store/products.json";

export default {
  name: "ProductList",
  components: {
    ProductCard,
  },
  data() {
    return {
      products: json,
    };
  },
};
</script>

<style>
</style>