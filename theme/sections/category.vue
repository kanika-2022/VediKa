<template>
  <div
    
    :class="{
      'section-main-container': !settings.props.full_width.value,
      'full-width-section': settings.props.full_width.value,
    }"
  >
    <div class="gallery-container">
      <div class="card-container">
        <div class="top-items">
          <div class="title-block">
            <div
              :style="'color:' + global_config.props.text_heading_link_color +'font-family:'+global_config.props.HeaderPrimaryFont +'font-size:'+global_config.props.HeaderFontSize"
              class="section-heading" >
              {{ settings.props.title.value }}
            </div>
           
          </div>
          <template v-if="settings.blocks.length > 0">
            <div v-if="settings.props.layout.value === 'grid'">
             <div class="category_grid">
                    <div class="category_item" v-for="(block, index) in settings.blocks"
                      :key="index"
                      ><a v-bind:href="block.props.category_link.value"> 
                          <img
                              style="max-width: 100%;height:100%;filter: opacity(.8) drop-shadow(0 0 0 black);"
                              v-if="block.props.category_image.value"
                              :src="block.props.category_image.value"
                              alt=""
                          /></a>
                      <div class="itemName" v-if="block.props.category_name.value">{{block.props.category_name.value}}</div>                    
                      <!-- <div class="instagram"></div>
                      </div> -->
                    </div>

              </div>
            </div>

            <div v-if="settings.props.layout.value === 'horizontal'">
              <div class="glide-cont" :class="'glide'+ _uid" ref="glide" >
                <div data-glide-el="track" class="glide__track">
                  <div class="glide__slides" :class="{ 'ssr-slides-box': !checkisBrowser() && !isMounted }">
                    
                    <div class="category_horizontal">
                        <div class="category_item" v-for="(block, index) in settings.blocks"
                            :key="index"
                            ><a v-bind:href="block.props.category_link.value"> 
                                <img
                                    style="max-width: 100%;height:100%;filter: opacity(.8) drop-shadow(0 0 0 black);"
                                    v-if="block.props.category_image.value"
                                    :src="block.props.category_image.value"
                                    alt=""
                                /></a>
                            <div class="itemName" v-if="block.props.category_name.value">{{block.props.category_name.value}}</div>                    
                            <!-- <div class="instagram"></div>
                            </div> -->
                            </div>
                  </div>
                </div>
                <div class="glide__bullets" data-glide-el="controls[nav]" v-if="settings.blocks.length > settings.props.item_count.value">
                  <button class="glide__bullet" :data-glide-dir="'=' + entry" v-for="(entry, index) in glidePaginate(settings.blocks.length, settings.props.item_count.value)" :key="index" ></button>
                </div>
                <div class="arrows"
                  v-if="
                    settings.blocks.length > 0 &&
                    settings.blocks.length > settings.props.item_count.value
                  "
                >
                  <section>
                    <div
                      class="prev-btn btn-nav-gallery"
                      ref="prevArrow"
                      @click="prevSlide"
                    >
                      <div class="icon icon-prev">
                      </div>
                    </div>
                    <div
                      class="next-btn btn-nav-gallery"
                      ref="nextArrow"
                      @click="nextSlide"
                    >
                      <div class="icon icon-next">
                      </div>
                    </div>
                  </section>
                </div>
              </div>
            </div>
          </template>
          <template v-else>
             <placeholder-items
              :count="settings.props.item_count.value * 2"
              :items_per_row="settings.props.item_count.value"
              type="image"
              text=""
              :layout="settings.props.layout.value"
            />
          </template>
          <div class="view-all-mobile" :class="{ 'view-all-horizontal': settings.props.layout.value === 'horizontal'}">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<!-- #region  -->
<settings>
{
    "name": "category",
    "label": "Category",
    "props": [
        {
            "type": "text",
            "id": "title",
            "default": "",
            "label": "Title"
        },
        {
            "id": "layout",
            "type": "select",
            "options": [
                {
                    "value": "grid",
                    "text": "Grid View"
                }
            ],
            "default": "grid",
            "label": "Layout",
            "info": "Alignment of content"
        },
        {
            "type": "range",
            "id": "item_count",
            "min": 4,
            "max": 4,
            "step": 1,
            "unit": "",
            "label": "No of items",
            "default": 4,
            "info": "Maximum items allowed per row for Horizontal view, for gallery max 5 are viewable and only 5 blocks are required"
        },
        {
            "type": "checkbox",
            "id": "full_width",
            "default": false,
            "label": "Full width",
            "info": "Check to allow items to take entire width of the viewport"
        }
    ],
    "blocks": [
        {
            "type": "category",
            "name": "Category",
            "props": [
                {
                    "type": "image_picker",
                    "id": "category_image",
                    "label": "Gallery Image",
                    "default": ""
                },
                {
                    "type": "url",
                    "id": "category_link",
                    "label": "Link",
                    "default": "",
                    "info": "Link to redirect"
                },
                {
                    "type":"text",
                    "id":"category_name",
                    "label":"Category Name",
                    "default":""
                }
            ]
        }
    ],
    "preset":{
      "blocks":[
        {
          "name":"Category"
        },
        {
          "name":"Category"
        },
        {
          "name":"Category"
        },
        {
          "name":"Category"
        }
      ]
    }
}
</settings>
<!-- #endregion -->
<style scoped lang="less">

.gallery-container {
  // margin: 20px 0px 30px 0px;
  @media @mobile {
    margin-top: 0;
  }
  .card-container {
    margin: 0;
    .top-items {
      // padding: 14px;
      border-radius: @border-radius;
      background: transparent;
      // margin: 10px 0 0 0;
    }

    .title-block {
      display: flex;
      text-transform: uppercase;
      text-align: center;
      box-sizing: border-box;
      position: relative;
      max-width: @page-width;
      .margin-0-auto();
      > div {
        flex: 0 0 100%;
      }
    }
    .link {
      position: absolute;
      line-height: 35px; //this is used to match the title-block height
      right: 0px;
      bottom: @title-margin-desktop;
      @media @tablet {
        display: none;
      }
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
  .prev-btn {
    margin-right: 22px;
  }

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
  .glide__slide {
    height: auto;
    a {
      display: flex;
      height: 100%;
    }
    /deep/ .placeholder-svg {
      height: 99%;
      display: flex;
      svg {
        width: 100%;
      }
    }
  }
  .glide__slides.ssr-slides-box {
    touch-action: unset;
    overflow-x: auto;
    .glide__slide {
      margin-right: 30px;
      width: auto;
      max-width: 218px;
    }
  }
  .btn-nav-gallery {
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
    width: 45px;
    height: 45px;
    background-size: cover;
  }
  .icon-next {
    background-image: url(../assets/images/nav-arrow.svg);
    transform: rotate(180deg);
  }
  .icon-prev {
    background-image: url(../assets/images/nav-arrow.svg);
  }
  
}
.category_item{
  position: relative;
  width: 23%;
  padding: 1%;
  display:inline-block;
  vertical-align: top;
}
.itemName{
    position: absolute;
    font-family: "Century Gothic";
    font-size: 16px;
    color: white;
    top: 50%;
    left: 50%;

}
.category_item:hover{
  transform:scale(1.1);
  transition: all linear 0.3s;

}
.category_grid{
    display:block;
}
.category_horizontal{
    display: flex;
    flex-basis: column;
}
.section-main-container{
    max-width: 100% !important;
    background: white  !important;
    height: 100% !important;
    padding: 20px 40px 50px !important;
}
</style>
<script>
import { detectMobileWidth, glidePaginate } from "../helper/utils";
import { isBrowser, isNode } from "browser-or-node";
import groupList from "./../global/components/group-list.vue";
import galleryItem from "./../global/components/gallery-item.vue";
import Glide from '@glidejs/glide'
import '../../node_modules/@glidejs/glide/dist/css/glide.core.min.css';
import '../../node_modules/@glidejs/glide/dist/css/glide.theme.min.css';
import placeholderItemsVue from "../global/components/sections/placeholder-items.vue";

export default {
  props: ["settings","global_config"],
  components: {
    "gallery-item": galleryItem,
    "group-list": groupList,
    "placeholder-items": placeholderItemsVue,
  },
  watch: {
    settings: function (newVal, oldVal) {
      this.cleanupComponent();
      this.initializeComponent();
    },
  },
  mounted() {
    this.initializeComponent()
  },
  data: function () {
    return {
      isMounted: false,
      glideOptions: {
        type: 'carousel',
        startAt: 0,
        gap: 30,
        focusAt: 0,
        perView: this.settings.props.item_count.value,
        breakpoints: {
          1024: {
            perView: 3
          },
          600: {
            perView: 2
          },
          480: {
            perView: 1
          }
        }
      },
      carouselHandle: null
    };
  },
  methods: {
    checkisBrowser(){
      return isBrowser
    },
    glidePaginate,
    prevSlide() {
      let item_count = this.settings.props.item_count.value;
      if (detectMobileWidth()) {
        if(this.carouselHandle.index - 1 >= 0) {
          this.carouselHandle.go(`=${this.carouselHandle.index - 1}`)
        }
      } else {
        if(this.carouselHandle.index - item_count >= 0) {
          this.carouselHandle.go(`=${this.carouselHandle.index - item_count}`)
        } else {
          this.carouselHandle.go(`<<`)
        }
      }
    },
    nextSlide() {
      let item_count = this.settings.props.item_count.value;
      if (detectMobileWidth()) {
        if(this.carouselHandle.index + 1 >= this.settings.blocks.length-1) {
          this.carouselHandle.go(`=${this.carouselHandle.index + 1}`) 
        }
      } else {
        if(this.carouselHandle.index + item_count < this.settings.blocks.length) {
          this.carouselHandle.go(`=${this.carouselHandle.index + item_count}`)
        } else {
          this.carouselHandle.go(`>>`)
        }
      }
    },
    initCarousel() {
      if (isNode || this.settings.props.layout.value !== 'horizontal' || this.carouselHandle ) {
        return;
      }
      if(!this.$refs.glide) {
        setTimeout(()=>{ this.initCarousel() }, 1000)
        return;
      }
      this.$nextTick(()=>{
        try {
          if(window.screen.width > 480 && window.screen.width <= 768) {
            this.glideOptions.gap = 40
          } else if (window.screen.width <= 480) {
            this.glideOptions.gap = 12
          }
          
          this.carouselHandle = new Glide(this.$refs.glide , this.glideOptions)
          let glideClass = this.$refs.glide.getAttribute('class')
          this.carouselHandle.on(['move.after'], () => {
              let allDots = document.querySelectorAll(`.${glideClass} [data-glide-dir]`)
              if(allDots && allDots.length > 0 ) {
                allDots.forEach(ele => {
                  ele.classList.remove('glide__bullet--active')
                })
              }
              let currentDot = this.carouselHandle ? document.querySelectorAll(`.${glideClass} [data-glide-dir='=${this.carouselHandle.index}']`) : null;
              if(currentDot && currentDot.length > 0) { 
                currentDot[0].classList.add('glide__bullet--active') 
              }
          })
          this.carouselHandle.mount()
        } catch(ex) {
        }
      })
    },
    initializeComponent() {
      this.isMounted = true;
      if(window.screen.width > 600 && window.screen.width <= 1024) {
        this.settings.props.item_count.value = 3
      } else if (window.screen.width > 480 && window.screen.width <= 600) {
        this.settings.props.item_count.value = 2
      } else if (window.screen.width <= 480) {
        this.settings.props.item_count.value = 1
      }
      this.glideOptions.perView = this.settings.props.item_count.value;
      this.initCarousel()
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
  },
};
</script>
