
<template>
  <div class="bar" :style="styledBar">
    <div class="progress" :style="styledProgress"></div>
  </div>
</template>

<script>
export default {
  name: 'TinyProgressBar',
  props: {
    color: {
      type: String, 
      default: "#1ed760"
    }, 
    height: {
      type: Number, 
      default: 2
    }
  },
  data() {
    return {
      progress: 0
    }
  },
  methods: {
    setProgress: function (progress) {
      if (isNaN(progress)) {
        return;
      }

      if (progress < 0) {
        this.progress = 0;
      } else if (progress > 100) {
        this.progress = 100;
      } else {
        this.progress = progress;
      }
    }
  },
  computed: {
    styledBar: function () {
      return {
        'height': this.height + 'px'
      }
    },
    styledProgress: function () {
      return {
        'width': this.progress + '%', 
        'background-color': this.color
      }
    }
  }
}
</script>

<style scoped>
.bar {
  width: 100%;
  overflow: hidden;
}
.progress {
  width: 100%;
  height: 100%;
}
</style>
