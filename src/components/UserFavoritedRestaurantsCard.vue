<template>
  <div class="card">
    <div class="card-header">
      <strong>{{ favoriteRestaurants.length }}</strong> 收藏的餐廳
    </div>
    <div class="card-body">
      <a
        href="/restaurants/2"
        v-for="favRest in favoriteRestaurants"
        :key="favRest.id"
      >
        <img :src="favRest.image" width="60" height="60" class="avatar" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    favoriteRestaurants: {
      type: Array,
      required: true,
    },
  },
};
</script>
