<template class="medium-container">
  <div id="app" class="flex-row">
    <car-view :options="options" class="flex-small"/>
    <car-parts :parts="parts" @delete:part="deletePart" class="flex-small"/>

    <shopping-cart/>
    <car-side/>
  </div>
</template>

<script>
import CarParts from "@/components/CarParts.vue";
import CarView from "@/components/CarView.vue";
import ShoppingCart from "@/components/ShoppingCart.vue";
import CarSide from "@/components/CarSide.vue";

export default {
  name: "App",
  components: {
    CarParts,
    CarView,
    ShoppingCart,
    CarSide
  },

  data() {
    return {
      options: [
        {
          id: 1,
          title: "Blue",
          img: "https://via.placeholder.com/150/0000FF?text=side"
        },
        {
          id: 2,
          title: "Red",
          img: "https://via.placeholder.com/150/ff0000?text=top"
        },
        {
          id: 3,
          title: "Yellow",
          img: "https://via.placeholder.com/150/ffff00?text=back"
        }
      ],

      parts: [
        {
          id: 1,
          name: "Wheel Cover",
          imageUrl: "https://via.placeholder.com/150/ffa500",
          price: 100.0
        },
        {
          id: 2,
          name: "Flame Sticker",
          imageUrl: "https://via.placeholder.com/150/008000",
          price: 100.0
        },

        {
          id: 3,
          name: "Headlight Covers",
          imageUrl: "https://via.placeholder.com/150/800080",
          price: 100.0
        },

        {
          id: 4,
          name: "Tail Light Colors",
          imageUrl: "https://via.placeholder.com/150/ffff00",
          price: 100.0
        },

        {
          id: 5,
          name: "Vinyl Strips",
          imageUrl: "https://via.placeholder.com/150/808080",
          price: 100.0
        }
      ]
    };
  },

  methods: {
    deletePart(id) {
      this.parts = this.parts.filter(part => part.id !== id);
    },

    addOption(id) {
      this.options = this.options.filter(option => option.id !== id);
    }
  }
};
</script>

<style>
</style>
