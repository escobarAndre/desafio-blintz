<template>
  <div class="home px-0 pb-10 pt-3 md:px-7 xl:px-0 xl:px-10">
    <top-bar :properties="allProperties"
             @new-properties="newProperties"></top-bar>
    <product v-for="propertie in properties"
             :title="propertie.address"
             :subtitle="propertie.city + ',' + propertie.state + ',' + propertie.zip"
             :image="propertie.image"
             :key="propertie">
    </product>
  </div>
</template>

<script>
import TopBar from '../components/TopBar.vue'
import Product from '../components/Product.vue'

export default {
  components: {
    TopBar, Product
  },
  methods: {
    newProperties (payload) {
      this.properties = payload
    }
  },
  data () {
    return {
      allProperties: [
        { address: 'Trump Plz #123', city: 'New Jersey', state: 'NJ', zip: '33140', image: 'https://placeimg.com/300/300/any', active: true },
        { address: 'Truman E Rd', city: 'Kansas City', state: 'MO', zip: '33140', image: 'https://placeimg.com/300/300/any', active: true },
        { address: 'Jazz Avenue 32', city: 'Salt Lake City', state: 'UT', zip: '33333', image: 'https://placeimg.com/300/201/any', active: false }
      ],
      properties: [
        { address: 'Trump Plz #123', city: 'New Jersey', state: 'NJ', zip: '33140', image: 'https://placeimg.com/300/300/any', active: true },
        { address: 'Truman E Rd', city: 'Kansas City', state: 'MO', zip: '33140', image: 'https://placeimg.com/300/200/any', active: true },
        { address: 'Jazz Avenue 32', city: 'Salt Lake City', state: 'UT', zip: '33333', image: 'https://placeimg.com/300/301/any', active: false }
      ]
    }
  }
}
</script>