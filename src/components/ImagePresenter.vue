<template>
  <div class="presenter">
    <div class="current-image" :style="{backgroundImage: 'url(' + current.img_url + ')'}" />
    <div class="thumbnails-container">
      <div
        v-for="thumbnail in content.thumbnails"
        :key="thumbnail.img_url"
        class="thumbnails"
        @click="onThumbnailClick(thumbnail)">
        <div
          class="thumbnails-inner"
          :class="{selected: thumbnail.img_url === current.img_url, clickable:thumbnail.img_url }"
          :style="{ backgroundImage: 'url(' + thumbnail.img_url + ')' }" />
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'ImagePresenter',
    props: {
      content: {
        type: Object,
        default: () => ({}),
      },
      id: {
        type: String,
        default: '',
      },
    },
    data: () => ({
      current: null,
    }),
    created() {
      for (let i = this.content.thumbnails.length; i < 4; i += 1) {
        this.content.thumbnails.push({});
      }
      this.current = this.content.thumbnails[0];
    },
    methods: {
      onThumbnailClick(thumbnail) {
        if (thumbnail.img_url) {
          this.current = thumbnail;
        }
      },
    },
  };
</script>
face
<style scoped lang="scss">

  .presenter {
    display: flex;
    flex-direction: column;
    max-width: 700px;
    width: 100%;
    padding: 10px;
  }

  .current-image {
    width: 100%;
    border-radius: 5px;
    padding-top: (3 / 4) * 100%;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-image: url("https://cdn.joinfightcamp.com/images/website-v3/fightcamp-living-room-white-001.jpg");
  }

  .thumbnails-container {
    display: flex;
    flex-direction: row;
    margin: 10px 0;
    justify-content: space-between;
  }

  .thumbnails {
    height: 0;
    width: 24%;
    padding-bottom: 24%;
  }

  .clickable {
    cursor: pointer;
  }

  .thumbnails-inner {
    height: 0;
    width: 100%;
    padding-bottom: 100%;
    box-sizing: border-box;
    object-fit: contain;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    border-radius: 5px;
    background-color: #dddfe1;
    border: 3px solid #dddfe1;
    background-image: url("https://cdn.joinfightcamp.com/images/website-v3/fightcamp-living-room-white-001.jpg");
  }

  .selected {
    border: 3px solid #eb7580;
  }

</style>
