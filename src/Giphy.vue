<template>
    <div>
        <center>
            <img :src="image" :title="alt" />
        </center>
    </div>
</template>

<script>
import Vue from 'vue'
import VueResource from 'vue-resource'
Vue.use(VueResource);

export default {
  props: {
    query: {
        type: String,
        default: 'success'
    },
    apiKey: {
        type: String,
        required: true
    }
  },
  data: function() {
        return {
            image: '',
            alt: ''
        }
    },
    methods: {
        showGiphy: function () {
          var url = "http://api.giphy.com/v1/gifs/random?api_key=" + this.apiKey + "&tag=" + this.query;
          this.$http.get(url).then(response => {
              this.alt = response.body.data.caption
              this.image = response.body.data.image_url
          })
        }
    }, mounted() {
        this.showGiphy()
    }

}
</script>
