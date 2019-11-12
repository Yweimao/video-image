<template>
  <div id="app">
    <component :is="currentComponet"></component>
    <router-view/>
  </div>
</template>

<script>
    import ActionOne from './components/action-one'
    import ActionTwo from './components/action-two'

    export default {
        name: 'App',
        components: {
            ActionOne,
            ActionTwo
        },
        data() {
            return {
                ActionOne: ActionOne,
                ActionTwo: ActionTwo,
                index: 1
            }
        },
        computed: {
            currentComponet() {
                if (this.index == 1) {
                    return this.ActionTwo
                }
            }
        }
    }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
