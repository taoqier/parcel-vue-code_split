<template>
  <div id="app" class="app">
    <h1>Hello {{ title }} 🚀</h1>
    <p>📦 Parcel Vue.js Example</p>
    <component :is="com"></component>
  </div>
</template>

<script>

export default {
  name: 'app',
  data () {
    return {
      title: 'Vue.js',
      com: ''
    }
  },
  mounted () {
    let vm = this
    window.addEventListener('keyup',function (e) {
      let key = String.fromCharCode(e.keyCode)
      console.log(key)
      if (key == 'H') {
        vm.com = 'Header'
      } else if(key == 'F') {
        vm.com = 'Footer'
      }
    })
  },
  components: {
    'Header': () => import('./header'),
    'Footer': () => import('./footer')
  }
}
</script>

<style scoped>
#app {
  font-family: Helvetica, Arial, sans-serif;
  text-align: center;
  color: #fff;
  margin-top: 60px;
  background-color: rebeccapurple;
}

h1 {
  font-weight: lighter;
  color: #42b983;
}

#app a {
  color: gold;
}
</style>
