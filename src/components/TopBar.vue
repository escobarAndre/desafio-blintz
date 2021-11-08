<template>
  <div class="top-bar bg-gray-100 w-auto min-w-95 h-auto rounded border-gray-200 border-2 m-0 p-2 inline-block justify-between md:p-5 md:flex md:min-w-0">
    <div class="flex justify-between px-2 py-2 mb-4 md:p-0 md:mb-0" >
      <div class="inline-block font-bold text-xs tracking-wider text-left">
        <p class="mb-2">FILTER</p>
        <select v-model="selectedFilter" @change="filter()" class="border w-1/1 h-9 border-indigo-900 rounded bg-white focus:border-indigo-900 md:w-40">
          <option disable value="">Choose a filter</option>
          <option v-for="filter in filters" :key="filter.text">
            {{ filter.text }}
          </option>
        </select>
      </div>
      <div class="inline-block font-bold text-xs tracking-wider text-left mx-0 md:mx-4">
        <p class="mb-2">SORT</p>
        <select v-model="selectedSort" @change="sort()" class="border w-1/1 h-9 border-indigo-900 rounded bg-white focus:border-indigo-900 md:w-40">
          <option disable value="">Choose a sort</option>
          <option v-for="sort in sorts" :key="sort.text">
            {{ sort.text }}
          </option>
        </select>
      </div>
    </div>
    <div>
      <div class="inline-block w-full font-bold text-xs tracking-wider text-left px-2 pb-3 mx-0 md:mx-4 md:px-4 md:pb-0">
        <p class="mb-2">SEARCH</p>
        <input @change="search()" v-model="selectedSearch" name="filter" type="text" placeholder="Search Packages" class="border w-full h-9 border-indigo-900 rounded p-3 focus:border-indigo-900">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  created: function () {
    this.sort()
  },
  methods: {
    filter () {
      if (this.selectedFilter === 'Active') {
        this.newProperties = this.properties.filter(function (e) {
          return e.active === true
        })
        this.$emit('new-properties', this.newProperties)
      } else if (this.selectedFilter === 'Inactive') {
        console.log(this.properties)
        this.newProperties = this.properties.filter(function (e) {
          return e.active === false
        })
        this.$emit('new-properties', this.newProperties)
      } else if (this.selectedFilter === 'All') {
        this.newProperties = this.properties
        this.$emit('new-properties', this.newProperties)
      }
    },
    sort () {
      if (this.selectedSort === 'Address') {
        if (this.selectedFilter === 'Active') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === true
          }).sort(
            function (a, b) {
              if (a.address > b.address) {
                return 1
              } else if (a.address < b.address) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else if (this.selectedFilter === 'Inactive') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === false
          }).sort(
            function (a, b) {
              if (a.address > b.address) {
                return 1
              } else if (a.address < b.address) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else {
          // eslint-disable-next-line vue/no-mutating-props
          this.newProperties = this.properties.sort(
            function (a, b) {
              if (a.address > b.address) {
                return 1
              } else if (a.address < b.address) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        }
      } else if (this.selectedSort === 'City') {
        if (this.selectedFilter === 'Active') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === true
          }).sort(
            function (a, b) {
              if (a.city > b.city) {
                return 1
              } else if (a.city < b.city) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else if (this.selectedFilter === 'Inactive') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === false
          }).sort(
            function (a, b) {
              if (a.city > b.city) {
                return 1
              } else if (a.city < b.city) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else {
          // eslint-disable-next-line vue/no-mutating-props
          this.newProperties = this.properties.sort(
            function (a, b) {
              if (a.city > b.city) {
                return 1
              } else if (a.city < b.city) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        }
      } else if (this.selectedSort === 'ZIP') {
        if (this.selectedFilter === 'Active') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === true
          }).sort(
            function (a, b) {
              if (a.zip > b.zip) {
                return 1
              } else if (a.zip < b.zip) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else if (this.selectedFilter === 'Inactive') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === false
          }).sort(
            function (a, b) {
              if (a.zip > b.zip) {
                return 1
              } else if (a.zip < b.zip) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else {
          // eslint-disable-next-line vue/no-mutating-props
          this.newProperties = this.properties.sort(
            function (a, b) {
              if (a.zip > b.zip) {
                return 1
              } else if (a.zip < b.zip) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        }
      } else if (this.selectedSort === 'State') {
        if (this.selectedFilter === 'Active') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === true
          }).sort(
            function (a, b) {
              if (a.state > b.state) {
                return 1
              } else if (a.state < b.state) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else if (this.selectedFilter === 'Inactive') {
          this.newProperties = this.properties.filter(function (e) {
            return e.active === false
          }).sort(
            function (a, b) {
              if (a.state > b.state) {
                return 1
              } else if (a.state < b.state) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        } else {
          // eslint-disable-next-line vue/no-mutating-props
          this.newProperties = this.properties.sort(
            function (a, b) {
              if (a.state > b.state) {
                return 1
              } else if (a.state < b.state) {
                return -1
              } return 0
            })
          this.$emit('new-properties', this.newProperties)
        }
      }
    }
  },
  props: {
    properties: Array
  },
  watch: {
    selectedSearch: function () {
      this.newProperties = this.properties.filter(propertie => propertie.city.includes(this.selectedSearch) | propertie.address.includes(this.selectedSearch))
      this.$emit('new-properties', this.newProperties)
    }
  },
  data () {
    return {
      newProperties: [],
      selectedSearch: '',
      selectedFilter: '',
      selectedSort: 'Address',
      filters: [
        { text: 'All', value: 'A' },
        { text: 'Active', value: 'B' },
        { text: 'Inactive', value: 'C' }
      ],
      sorts: [
        { text: 'Address', value: 'A' },
        { text: 'City', value: 'B' },
        { text: 'State', value: 'C' },
        { text: 'ZIP', value: 'D' }
      ]
    }
  }

}
</script>