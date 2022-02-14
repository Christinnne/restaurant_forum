// ./src/components/UserTopCards.vue
<template>
  <div class="row text-center">
    <div class="col-3">
      <a href="#">
        <img :src="topUser.image" width="140px" height="140px" />
      </a>
      <h2>{{ topUser.name }}</h2>
      <span class="badge badge-secondary"
        >追蹤人數：{{ topUser.FollowerCount }}</span
      >
      <p class="mt-3">
        <button
          v-if="topUser.isFollowed"
          type="button"
          class="btn btn-danger"
          @click.stop.prevent="notFollow"
        >
          取消追蹤
        </button>
        <button
          v-else
          type="button"
          class="btn btn-primary"
          @click.stop.prevent="follow"
        >
          追蹤
        </button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    initialTopUser: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      topUser: this.initialTopUser,
    };
  },
  methods: {
    follow() {
      this.topUser = {
        ...this.topUser,
        isFollowed: true,
      };
    },
    notFollow() {
      this.topUser = {
        ...this.topUser,
        isFollowed: false,
      };
    },
  },
};
</script>  
