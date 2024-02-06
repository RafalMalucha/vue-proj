<template>
  <HelloWorld msg="łeeeeeeeeeeeeeee"/>
  <SearchBar @phraseChange="onPhraseChange"></SearchBar>
  <VideoList v-bind:key="videos"></VideoList>
  {{ videos.length }}
</template>

<script>
import axios from 'axios'
import HelloWorld from './components/HelloWorld.vue'
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';
const API_KEY = 'AIzaSyBjY6I-e9b9kT7k3TfAMqQtqKcLF9fw8pI'

export default {
  name: 'App',
  components: {
    HelloWorld,
    SearchBar,
    VideoList
},
  data() {
    return {videos: []}
  },
  methods: {
    // onPhraseChange(phrase){
    //   axios.get('https://www.googleapis.com/youtube/v3/search', {
    //     params: {
    //       key: API_KEY,
    //       type: 'video',
    //       part: 'snippet',
    //       q: phrase
    //     }
    //   }).then(resposne => {
    //     var infoList = []
    //     console.log("new data")
    //     this.videos = resposne.data.items
    //     for (let i = 0; i < 5; i++) {
    //       console.log(this.videos.at(i))
    //       infoList.push(this.videos.at(i))
    //     }
    //     console.log(infoList)
    //   })
    // }
    onPhraseChange(phrase){
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: phrase
        }
      }).then(resposne => {
        this.dupa = resposne.data.items
        const mockData = [{
        "kind": "youtube#searchResult",
        "etag": "H8yyVN5uwIA8s07__dKciObP0iU",
        "id": {
            "kind": "youtube#video",
            "videoId": "zPUSDU0hrwE"
        },
        "snippet": {
            "publishedAt": "2024-01-30T17:00:04Z",
            "channelId": "UC0k238zFx-Z8xFH0sxCrPJg",
            "title": "Inside Bryce Dallas Howard’s Charming New York Cottage | Open Door | Architectural Digest",
            "description": "Today, Architectural Digest is welcomed by Bryce Dallas Howard to tour her charming cottage in New York. Growing up in ...",
            "thumbnails": {
                "default": {
                    "url": "https://i.ytimg.com/vi/zPUSDU0hrwE/default.jpg",
                    "width": 120,
                    "height": 90
                },
                "medium": {
                    "url": "https://i.ytimg.com/vi/zPUSDU0hrwE/mqdefault.jpg",
                    "width": 320,
                    "height": 180
                },
                "high": {
                    "url": "https://i.ytimg.com/vi/zPUSDU0hrwE/hqdefault.jpg",
                    "width": 480,
                    "height": 360
                }
            },
            "channelTitle": "Architectural Digest",
            "liveBroadcastContent": "none",
            "publishTime": "2024-01-30T17:00:04Z"
        }
    },
    {
        "kind": "youtube#searchResult",
        "etag": "FwmkbVcyUii2aYo-pzyTuZ9CrAw",
        "id": {
            "kind": "youtube#video",
            "videoId": "G-T3qKl6y-c"
        },
        "snippet": {
            "publishedAt": "2020-11-16T16:54:26Z",
            "channelId": "UCyZK-pQ-NOCUkOOdbZWuSGQ",
            "title": "Delivery Dance",
            "description": "TFW when you get a good deal on the food you love with Grubhub Perks, so you have no choice but to dance. Grub what you ...",
            "thumbnails": {
                "default": {
                    "url": "https://i.ytimg.com/vi/G-T3qKl6y-c/default.jpg",
                    "width": 120,
                    "height": 90
                },
                "medium": {
                    "url": "https://i.ytimg.com/vi/G-T3qKl6y-c/mqdefault.jpg",
                    "width": 320,
                    "height": 180
                },
                "high": {
                    "url": "https://i.ytimg.com/vi/G-T3qKl6y-c/hqdefault.jpg",
                    "width": 480,
                    "height": 360
                }
            },
            "channelTitle": "Grubhub",
            "liveBroadcastContent": "none",
            "publishTime": "2020-11-16T16:54:26Z"
        }
    },
    {
        "kind": "youtube#searchResult",
        "etag": "fey2u70X54r4-6NMeNuVu3x3hA0",
        "id": {
            "kind": "youtube#video",
            "videoId": "9p9sGtV4UoU"
        },
        "snippet": {
            "publishedAt": "2023-06-27T16:00:25Z",
            "channelId": "UC0k238zFx-Z8xFH0sxCrPJg",
            "title": "Inside Amanda Seyfried’s Peaceful New York Home | Open Door | Architectural Digest",
            "description": "Today Architectural Digest is welcomed by Amanda Seyfried for a tour of her peaceful home in New York City. 'Mean Girls' and ...",
            "thumbnails": {
                "default": {
                    "url": "https://i.ytimg.com/vi/9p9sGtV4UoU/default.jpg",
                    "width": 120,
                    "height": 90
                },
                "medium": {
                    "url": "https://i.ytimg.com/vi/9p9sGtV4UoU/mqdefault.jpg",
                    "width": 320,
                    "height": 180
                },
                "high": {
                    "url": "https://i.ytimg.com/vi/9p9sGtV4UoU/hqdefault.jpg",
                    "width": 480,
                    "height": 360
                }
            },
            "channelTitle": "Architectural Digest",
            "liveBroadcastContent": "none",
            "publishTime": "2023-06-27T16:00:25Z"
        }
    },
    {
        "kind": "youtube#searchResult",
        "etag": "74hQLRVpP-T-r8F1sBNMaOHuEFs",
        "id": {
            "kind": "youtube#video",
            "videoId": "haK2TnmVoT0"
        },
        "snippet": {
            "publishedAt": "2022-02-02T13:00:02Z",
            "channelId": "UC0k238zFx-Z8xFH0sxCrPJg",
            "title": "Inside Gwyneth Paltrow&#39;s Tranquil Family Home | Open Door | Architectural Digest",
            "description": "Today AD is welcomed to Montecito by Gwyneth Paltrow for a tour of her peacefully luxurious family home. Paltrow first fell under ...",
            "thumbnails": {
                "default": {
                    "url": "https://i.ytimg.com/vi/haK2TnmVoT0/default.jpg",
                    "width": 120,
                    "height": 90
                },
                "medium": {
                    "url": "https://i.ytimg.com/vi/haK2TnmVoT0/mqdefault.jpg",
                    "width": 320,
                    "height": 180
                },
                "high": {
                    "url": "https://i.ytimg.com/vi/haK2TnmVoT0/hqdefault.jpg",
                    "width": 480,
                    "height": 360
                }
            },
            "channelTitle": "Architectural Digest",
            "liveBroadcastContent": "none",
            "publishTime": "2022-02-02T13:00:02Z"
        }
    },
    {
        "kind": "youtube#searchResult",
        "etag": "kkTdGEpRegc-a8iAcChX1vrYJkk",
        "id": {
            "kind": "youtube#video",
            "videoId": "xTpv9lc_qMw"
        },
        "snippet": {
            "publishedAt": "2013-01-17T19:57:07Z",
            "channelId": "UCoCqne57WL2mJ6-kWqiOQXw",
            "title": "Kit Kat Dancing Babies New Ad India (Official)",
            "description": "Good things happen when you take a KIT KAT break. Breaks offer opportunities that you may otherwise miss because you're too ...",
            "thumbnails": {
                "default": {
                    "url": "https://i.ytimg.com/vi/xTpv9lc_qMw/default.jpg",
                    "width": 120,
                    "height": 90
                },
                "medium": {
                    "url": "https://i.ytimg.com/vi/xTpv9lc_qMw/mqdefault.jpg",
                    "width": 320,
                    "height": 180
                },
                "high": {
                    "url": "https://i.ytimg.com/vi/xTpv9lc_qMw/hqdefault.jpg",
                    "width": 480,
                    "height": 360
                }
            },
            "channelTitle": "KIT KAT",
            "liveBroadcastContent": "none",
            "publishTime": "2013-01-17T19:57:07Z"
        }}]
      this.infoList = mockData
      console.log(this.infoList)
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
