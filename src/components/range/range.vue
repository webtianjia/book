<style lang="less" scoped>
    .range{
      position: relative;
      z-index: 1;
      line-height: normal;
      .range-wrap{
        width: 100%;
        height: 4px;
        margin: 16px 0;
        background-color: #e9eaec;
        border-radius: 3px;
        vertical-align: middle;
        position: relative;
        cursor: pointer;
      }
      .range-bar{
        height: 4px;
        background: #57a3f3;
        border-radius: 3px;
        position: absolute;
      }
      .range-button-wrap{
        width: 18px;
        height: 18px;
        text-align: center;
        background-color: transparent;
        position: absolute;
        top: -7px;
        transform: translateX(-50%);
      }
      .range-slider-button{
        width: 12px;
        height: 12px;
        border: 2px solid #57a3f3;
        border-radius: 50%;
        background-color: #fff;
        transition: all .2s linear;
      }
    }
</style>
<template>
  <div class="range">
    <div class="range-wrap" ref="lineDiv" @click.self="clickMove($event)">
      <div class="range-bar" :style="{'width':value+'px'}"></div>
      <div class="range-button-wrap" :style="{'left':value+'px'}"
           @touchstart="start"
           @touchmove="move($event)"
           @touchend="end"
           @mousedown="start"
           @mousemove="move($event)"
           @mouseup="end"
          >
            <div class="range-slider-button"></div>
      </div>
    </div>
  </div>
</template>
<script>
  function camelCase (name) {
    return name.replace(SPECIAL_CHARS_REGEXP, function (_, separator, letter, offset) {
      return offset ? letter.toUpperCase() : letter;
    }).replace(MOZ_HACK_REGEXP, 'Moz$1');
  }
  function getStyle (element, styleName) {
    if (!element || !styleName) return null
      styleName = camelCase (styleName)
    if (styleName === 'float') {
      styleName = 'cssFloat'
    }
    try {
      const computed = document.defaultView.getComputedStyle(element, '')
      return element.style[styleName] || computed ? computed[styleName] : null
     } catch (e) {
      return element.style[styleName]
    }
  }
    export default {
      props: {
        min: {
          type: Number,
          default: 0
        },
        max: {
          type: Number,
          default: 100
        }
      },
      data () {
        return {
          currentValue: this.value,
          isBoolean: false,
          x: 0,
          value: 0
        }
      },
      watch: {
        value (val) {
          this.currentValue = Math.round((val / this.$refs.lineDiv.offsetWidth) * 100)
        },
        currentValue (val) {
          this.$emit('input', val)
        }
      },
      computed: {
        sliderWidth () {
          return parseInt(getStyle(this.$refs.slider, 'width'), 10);
        }
      },
      methods: {
        move (event) {
          if (this.isBoolean) {
            if (!event.touches) {
              this.x = event.clientX
            } else {
              this.x = event.touches[0].pageX
            }
          }
          this.left()
        },
        start () {
          this.isBoolean = true
        },
        end () {
          this.isBoolean = false
        },
        getPosition (node) {
          let left = node.offsetLeft
          let top = node.offsetTop
          let current = node.offsetParent
          while (current != null) {
            left += current.offsetLeft
            top += current.offsetTop
            current = current.offsetParent
          }
          return {
            left: left,
            top: top
          }
        },
        left () {
          let left = this.x - this.getPosition(this.$refs.lineDiv).left
          if (left >= this.$refs.lineDiv.offsetWidth - 15) {
            left = this.$refs.lineDiv.offsetWidth
          }
          if (left < 0) {
            left = 0
          }
          this.value = left
        },
        clickMove (event) {
          const currentX = event.clientX
          const sliderOffsetLeft = this.$refs.slider.getBoundingClientRect().left;
          const newPos = (currentX - sliderOffsetLeft) / this.sliderWidth * 100;
          if (this.range) {
            let type = '';
            if (newPos <= this.firstPosition) {
              type = 'First';
            } else if (newPos >= this.secondPosition) {
              type = 'Second';
            } else {
              if ((newPos - this.firstPosition) <= (this.secondPosition - newPos)) {
                type = 'First';
              } else {
                type = 'Second';
              }
            }
            this[`change${type}Position`](newPos);
          } else {
            this.changeSinglePosition(newPos);
          }
        },
        changeSinglePosition (newPos) {
          if (newPos < 0) {
            newPos = 0
          } else if (newPos > 100) {
            newPos = 100
          }
          const lengthPerStep = 100 / ((this.max - this.min) / this.step);
          const steps = Math.round(newPos / lengthPerStep);
          this.currentValue = Math.round(steps * lengthPerStep * (this.max - this.min) * 0.01 + this.min);
          this.setSinglePosition(this.currentValue);
          if (!this.dragging) {
            if (this.currentValue !== this.oldSingleValue) {
              this.$emit('on-change', this.currentValue);
              this.dispatch('FormItem', 'on-form-change', this.currentValue);
              this.oldSingleValue = this.currentValue;
            }
          }
        }
      }
    }
</script>
