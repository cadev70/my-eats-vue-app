<template>
  <div>
    <b-card no-body style="width: 20rem" class="mb-2">
      <b-skeleton-wrapper :loading="loading">
        <template #loading>
          <b-overlay show rounded="true">
            <b-skeleton-img card-img="top" aspect="16:9" width="20rem">
            </b-skeleton-img>
          </b-overlay>
        </template>
      </b-skeleton-wrapper>
      <b-card-img-lazy
        ref="cardImage"
        :src="image"
        alt="Image"
        top
        @error.native="onImageError"
        @load.native="onImageLoaded"
      ></b-card-img-lazy>
      <b-card-body>
        <b-card-text class="h5 text-left">{{ title }}</b-card-text>
        <div class="text-left">
          <b-link to="#" class="text-left dark">{{ description }}</b-link>
        </div>
      </b-card-body>
    </b-card>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true,
    },
    url: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      loading: true,
    };
  },
  methods: {
    onImageError(e) {
      e.target.style.display = "none";
      this.loading = true;
      // console.log(`error @ ${this.image}`);
    },
    onImageLoaded() {
      const img = this.$refs["cardImage"];
      if (img.isShown) {
        this.loading = false;
        // console.log(`shown @ ${this.image}`);
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
