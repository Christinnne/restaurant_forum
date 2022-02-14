// ./src/components/RestaurantsTopCard.vue
<template>
  <div class="card mb-3" style="max-width: 540px; margin: auto">
    <div class="row no-gutters">
      <div class="col-md-4">
        <a href="#">
          <img class="card-img" :src="restaurant.image" />
        </a>
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">{{ restaurant.name }}</h5>
          <span class="badge badge-secondary"
            >收藏數：{{ restaurant.FavoriteCount }}</span
          >
          <p class="card-text">
            {{ restaurant.description }}
          </p>
          <router-link
            :to="`/restaurants/${restaurant.id}/dashboard`"
            class="btn btn-primary mr-2"
            >Show</router-link
          >

          <button
            v-if="restaurant.isFavorited"
            type="button"
            class="btn btn-danger mr-2"
            @click.stop.prevent="deleteFavorite"
          >
            移除最愛
          </button>
          <button
            v-else
            type="button"
            class="btn btn-primary"
            @click.stop.prevent="addFavorite"
          >
            加到最愛
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    initialRestaurant: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      restaurant: this.initialRestaurant,
    };
  },
  methods: {
    deleteFavorite() {
      this.restaurant = {
        ...this.restaurant,
        isFavorited: false,
      };
    },
    addFavorite() {
      this.restaurant = {
        ...this.restaurant,
        isFavorited: true,
      };
    },
  },
};
</script>
