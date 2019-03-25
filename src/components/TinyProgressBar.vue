
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
      progressData: 0
    }
  },
  computed: {
    /**
     * Getters & setters:
     */
    progress: {
      get: function () {
        return this.progressData;
      },
      set: function (newValue) {
        if (isNaN(newValue)) {
          return;
        }

        if (newValue < 0) {
          this.progressData = 0;
        } else if (newValue > 100) {
          this.progressData = 100;
        } else {
          this.progressData = +newValue;
        }
      }
    },
    /**
     * Other:
     */
    styledBar: function () {
      return {
        'height': this.height + 'px'
      }
    },
    styledProgress: function () {
      return {
        'width': this.progressData + '%', 
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
