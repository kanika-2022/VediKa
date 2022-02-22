f<template>
  <div
    class="testimonial-cont section-main-container" style="margin:0px !important; max-width:100% !important ;padding:0px;"
  >
  <sections page="product-listing" />

  <div class="glide-cont" :class="'glide'+ _uid" ref="glide" >
      <div data-glide-el="track" class="glide__track">
        <div class="glide__slides" :class="{ 'ssr-slides-box': !checkisBrowser() && !isMounted }">
          <div class="glide__slide quotes-slider" v-for="(block, i) in blocks" :key="i">
              <div class="banner-image">
                  <fdk-link :link="block.props.banner_link.value">
                    <img
                      style="width:100%;height:100%;object-fit:cover;"
                      v-if="block.props && block.props.banner_image.value"
                      :src="block.props.banner_image.value" 
                      alt=""
                  />
                  </fdk-link>
              </div>
            
          </div>
        </div>
      </div>
      <!--- Bullets -->
      <div class="glide__bullets" data-glide-el="controls[nav]" v-if="blocks.length > 1">
          <button class="glide__bullet" :data-glide-dir="'=' + entry" v-for="(entry, index) in glidePaginate(blocks.length, 1)" :key="index"></button>
      </div>
      <div
        class="arrows"
        v-if="
          blocks.length > 1
        "
      >
        <!-- <section>
          <div
            class="prev-btn btn-nav-testimonial"
            ref="prevArrow"
            @click="prevSlide"
          >
            <div class="icon icon-prev">
            </div>
          </div>
          <div
            class="next-btn btn-nav-testimonial"
            ref="nextArrow"
            @click="nextSlide"
          >
            <div class="icon icon-next">
            </div>
          </div>
        </section> -->
      </div>
    </div>
    
  </div>
</template>
<!-- #region  -->
<settings>
{
    "name": "application-banner",
    "label": "Application Banner",
    "props": [
        {
            "type": "checkbox",
            "id": "autoplay",
            "default": false,
            "label": "AutoPlay Slides"
        },
        {
            "type": "range",
            "id": "slide_interval",
            "min": 1,
            "max": 10,
            "step": 1,
            "unit": "sec",
            "label": "Change slides every",
            "default": 2
        },
          {
            "type": "range",
            "id": "item_count",
            "min": 1,
            "max": 1,
            "step": 1,
            "unit": "",
            "label": "No of items",
            "default": 1,
            "info": "Maximum items allowed per row for Horizontal view, for gallery max 3 are viewable and only 3 blocks are required"
        }
    ],
    "blocks": [
        {
            "type": "application-banner",
            "name": "Application Banner",
            "props": [
                {
                    "type": "image_picker",
                    "id": "banner_image",
                    "default": "",
                    "label": "Banner Image"
                },
                {
                   "type": "url",
                    "id": "banner_link",
                    "label": "Banner Link",
                    "default": "",
                    "info": "Link to redirect"
                }
            ]
        }
    ],
   "preset":{
    "blocks": [
      {
        "name": "Application Banner"
      },
      {
        "name": "Application Banner"
      },
      {
        "name": "Application Banner"
      }
    ]
  }

}
</settings>

<!-- #endregion -->
<style scoped lang="less">
.testimonial-cont{
  padding: 30px;
}
.testimonial-cont {
  .glide__bullets {
    position: relative;
    z-index: 2;
    margin-top: 40px;
    bottom: 0;
    left: 50%;
    display: inline-flex;
    align-items: center;
    list-style: none;
    transform: translateX(-50%);
    @media @mobile {
      margin-top: 20px;
    }
  }
  .glide__bullet {
    background-color: unset;
    border: 1px solid @color-black;
    box-shadow: unset;
    &:hover {
      background-color: @color-black;
    }
    &.glide__bullet--active {
      background-color: @color-black;
    }
  }
  .glide__slides.ssr-slides-box {
    touch-action: unset;
    overflow-x: auto;
    -ms-overflow-style: none;
    scrollbar-width: none;
    &::-webkit-scrollbar {
      display: none;
    }
    .glide__slide {
      margin-right: 30px;
      width: 100%;
    }
  }
  .glide__slides {
    align-items: stretch;
    .glide__slide { 
      height: auto;
    }
  }
  .arrows {
    position: absolute;
    display: flex;
    justify-content: flex-end;
    top: 50%;
    width: 100%;
    margin: -40px 0 0 0;
    @media @tablet {
      display: none;
    }
    section {
        position: relative;
        width: 100%;
        margin: 0 auto;
        display: flex;
        padding: 0 20px;
        box-sizing: border-box;
      }
  }
  .btn-nav-testimonial {
    z-index: @layer;
    background-color: transparent;
    padding: unset;
    cursor: pointer;
    width: 50px;
    display: flex;
    justify-content: center;
    transition: transform .2s;
    &:hover {
      transform: scale(1.2);
    }
  }
  .next-btn {
    margin-left: auto;
  }
  
  .icon {
    display: inline-block;
    width: 30px;
    height: 30px;
    background-size: cover;
  }
  .icon-next {
    background-image: url(../assets/images/nav-arrow.svg);
    transform: rotate(180deg);
  }
  .icon-prev {
    background-image: url(../assets/images/nav-arrow.svg);
  }
  .quotes-slider {
    font-style: normal;
    // padding: 0 15px;
    text-align: center;
    display: flex;
    flex-direction: column;
    
    cite {
      display: block;
      font-weight: 300;
      section {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        >:first-child {
          font-size: 20px;
        }
        >:nth-child(2) {
          font-size: 16px;
          padding: 8px 0 0px 0;
          @media @mobile {
            font-size: 12px;
            padding: 14px 0 0 0;
          }
        }
      }
    }
  }
  // cite::before {
  //   content: "\2014 \0020";
  // }
  .quotes-slider p {
    // margin-bottom: 30px;
    font-size: 16px;
    line-height: 1.6em;
    font-family: "Century Gothic";
    @media @tablet {
      font-size: 16px;
      line-height: 1.6em;
      font-family: "Century Gothic";
    }
    @media @mobile {
      font-size: 16px;
      line-height: 1.6em;
      font-family: "Century Gothic";
    }
  }

  .quote-icon {
    display: flex;
    // align-items: center;
    justify-content: center;
    &.left {
      margin: 20px 0 0px 0;
      // justify-content: flex-start;
      justify-content: center;

    }
    &.right {
      margin: 0px 0 20px 0;
      // justify-content: flex-end;
      justify-content: center;

      img {
        transform: rotate(180deg);
      }
    }
    
  }
  .testimonial {
    height: 100%;
    padding: 10px 10px;
    width: 80%;
    margin: 0 auto;
    box-sizing: border-box;
    @media @tablet {
      padding: 10px 10px;
      width: 100%;
    }
  }
}
// .glide__slide.quotes-slider.glide__slide--active {
//     transform: scale(1.1);
//     box-shadow: 0 10px 25px #0000001a;
//     position: relative;
//     z-index: 10;
//     transition: all linear 0.3s;
// }
.testimonial-cont .quotes-slider{
  background-color: #fff;
}
</style>
<script>
import { isBrowser, isNode } from "browser-or-node";
import { detectMobileWidth, glidePaginate } from "../helper/utils";
import Glide from "@glidejs/glide";
import emergeImage from "./../global/components/common/emerge-image.vue";
import "../../node_modules/@glidejs/glide/dist/css/glide.core.min.css";
import "../../node_modules/@glidejs/glide/dist/css/glide.theme.min.css";

export default {
  props: ["settings","global_config"],
  components: {
    "emerge-image": emergeImage,
  },
  watch: {
    settings: function(newVal, oldVal) {
      this.cleanupComponent()
      this.initializeComponent()
    },
  },
  computed: {
    blocks() {
      return this.settings.blocks.length === 0
        ? this.settings.preset.blocks
        : this.settings.blocks;
    }
  },
  data: function() {
    return {
      isMounted: false,
      glideOptions: {
          type: 'carousel',
          startAt: 1,
          gap: 10,
          focusAt : 'center',
          perView: this.settings.props.item_count.value,
          breakpoints: {
            1024: {
              perView: 1
            },
            600: {
              perView: 1
            },
            480: {
              perView: 1
            }
          }
      },
      carouselHandle: null
    };
  },
  mounted() {
    this.initializeComponent()
  },
  methods: {
    checkisBrowser(){
      return isBrowser
    },
    glidePaginate,
    prevSlide() {
      this.carouselHandle.go(`<`)
    },
    nextSlide() {
      this.carouselHandle.go(`>`)
    },
    initCarousel() {
      //if IsNode OR Layout is horizontal(optional flag) OR carouselHandle(carousel) is not already initialized
      if (isNode || this.carouselHandle) {
        return;
      }
      if(!this.$refs.glide) {
        setTimeout(()=>{ this.initCarousel() }, 1000)
        return;
      }
      // waiting for data to render, hence nextTick
      this.$nextTick(()=>{
        try {
          
          this.carouselHandle = new Glide(this.$refs.glide , this.glideOptions)
          this.carouselHandle.mount()
        } catch(ex) {
           //There is an exception logged, due to rendering delay, so this try,catch is required
        }
      })
    },
    initializeComponent() {
      this.isMounted = true
      if(this.settings.props.autoplay.value && this.blocks.length > 1) {
        this.glideOptions.autoplay = this.settings.props.slide_interval.value * 1000
      } else {
        this.glideOptions.autoplay = false
      }
      this.initCarousel();
    },
    cleanupComponent() {
      if(isBrowser && this.carouselHandle) {
        this.carouselHandle.destroy();
        this.carouselHandle = null;
      }
    }
  },
  beforeDestroy() {
    this.cleanupComponent()
  }
};
</script>
