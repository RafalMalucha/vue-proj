<template>
    <ul>
        {{ infoList }}
        <VideoListItem/>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue';

export default {
  name: 'VideoList',
  components: {
    VideoListItem,
},
  props: ['infoList']
}
</script>

<style>
</style>