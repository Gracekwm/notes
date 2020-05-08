# vue 滚动监听

``` js

watch: {
    toBottomHeight: function(val) {
      if (val === 0) {
        console.log('val', val)
        this.joinActivities()
      }
    }
  },
      
mounted() {  window.addEventListener('scroll', this.getToBottomHeight)},
    
methods: {
    getToBottomHeight() {
      let clientHeight =
        document.documentElement.clientHeight || document.body.clientHeight
      let scrollTop =
        document.documentElement.scrollTop || document.body.scrollTop
      let scrollHeight =
        document.documentElement.scrollHeight || document.body.scrollHeight
      this.toBottomHeight = scrollHeight - clientHeight - scrollTop
    }
}
```