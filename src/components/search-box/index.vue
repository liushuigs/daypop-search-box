<template>
  <form
    action="https://feeds.daypop.ai"
    @submit="onsubmit"
    :class="['header-search', lng === 'arabic' ? 'rtl': '']">
    <span class="icon"></span>
    <input type="text" :placeholder="placeholder" class="text" name="s" v-model="s" />
    <input type="hidden" name="from" value="totok" />
    <input type="hidden" name="utm_source" value="totok" />
    <input type="hidden" name="utm_medium" value="app" />
    <input type="hidden" name="utm_campaign" value="covid-19-search" />
    <input type="hidden" name="lng" :value="lng" />
  </form>
</template>
<script>
  export default {
    props: {
      lng: {
        type: String,
        default: '',
        validator(val) {
          return ['', 'arabic', 'en'].includes(val)
        }
      },
      placeholder: {
        type: String,
        default: 'Search for keywords'
      }
    },
    data() {
      return {
        s: '',
      }
    },
    methods: {
      onsubmit(evt) {
       if (!this.s) {
         evt.preventDefault()
       }
      }
    }
  }
</script>
<style>
  html {
    font-family: sans-serif;
    -webkit-tap-highlight-color: transparent;
  }
</style>
<style scoped>
  .header-search {
    height: 2.625rem;
    background-color: #ffffff;
    box-shadow: 0 0 0 0 rgba(0, 0, 0, 0.07);
    border: solid 1px #cccccc;
    border-radius: 0.188rem;
    display: flex;
    align-items: center;
  }
  .header-search.rtl {
    direction: rtl;
  }
  .header-search > .icon {
    display: block;
    width: 1.5rem;
    height: 1.5rem;
    background: url("./search-24px.png") no-repeat center center/cover;
    margin: 0 0.5rem 0 1.188rem;
  }
  .header-search > .text {
    height: 1rem;
    line-height: 1rem;
    font-size: 0.875rem;
    color: #808080;
    flex: 1;
    margin-right: 1.188rem;
    outline: 0;
  }
</style>
