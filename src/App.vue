<template lang="pug">
  #app
    sidebar(:sidebar-open='sidebarOpen')
    main(@click='toggleSidebar')
      b-button#sidebar-btn(@click='toggleSidebarBtn' variant="primary") toggle sidebar
      br
      img(src='./assets/logo.png')
</template>

<script>
import Sidebar from '@/components/SideBar'

let sidebar = Sidebar

export default {
  name: 'app',
  components: {
    sidebar
  },
  data () {
    return {
      sidebarOpen: false
    }
  },
  methods: {
    toggleSidebar (event) {
      if (event.target.id === 'sidebar-btn') return
      this.sidebarOpen = false
    },
    toggleSidebarBtn (event) {
      this.sidebarOpen = !this.sidebarOpen
    }
  }
}
</script>

<style lang="postcss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  //margin-top: 60px;
}
</style>
