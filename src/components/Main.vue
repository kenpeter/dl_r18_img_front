<template>
  <div class="main">

    <VPaginator :options="options" :resource_url="resource_url" @update="updateResource"></VPaginator>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [],
      resource_url: 'http://dl_r18_img_back.local',
      options: {
        remote_data: 'nested.data',
        remote_current_page: 'nested.current_page',
        remote_last_page: 'nested.last_page',
        remote_next_page_url: 'nested.next_page_url',
        remote_prev_page_url: 'nested.prev_page_url',
        next_button_text: 'Go Next',
        previous_button_text: 'Go Back',
      },
    };
  },
  methods: {
    updateResource(data) {
      /* eslint no-console: ["error", { allow: ["warn", "error", "log"] }] */
      console.log(data);
      this.list = data;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
