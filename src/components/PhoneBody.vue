<template>
  <div class="phone-body">
    <div v-if="step === 1" class="feed">
      <vuegram-post v-for="post in posts"
                    :post="post"
                    :key="posts.indexOf(post)">
      </vuegram-post>
    </div>
    <div v-if="step === 2">
      <div class="selected-image"
           :style="{ backgroundImage: 'url(' + image + ')' }"></div>
      <div class="filter-container">
        <!-- Where filter choices will be -->
      </div>
    </div>
  </div>
</template>

<script>
  import VuegramPost from "./VuegramPost";

  export default {
    name: "PhoneBody",
    props: {
      step: Number,
      posts: Array,
      filters: Array,
      image: String
    },
    components: {
      "vuegram-post": VuegramPost
    }
  };
</script>

<style lang="scss" src="../../styles/phone-body.scss">
  // Styles from stylesheet
</style>
