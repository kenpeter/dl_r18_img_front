<template>
  <div class="main">
    <ul class="list-inline">
      <li v-for="(item, index) in list" class="list-group-item">
        <a :href="`http://dl_r18_img_back.local/upload/${item.category.name}/${item.fileName}`" target="_blank">
          <img :src="`http://dl_r18_img_back.local/upload/${item.category.name}/${item.fileName}`"
            class="img-thumbnail"
            width="90"
            height="122"
          />
        </a>
      </li>
    </ul>

    <VPaginator :options="options" :resource_url="resource_url" @update="updateResource"></VPaginator>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [],
      resource_url: 'http://dl_r18_img_back.local/?page=10&limit=100',
      options: {},
    };
  },
  methods: {
    updateResource(data) {
      /* eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
      this.list = data;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
