<template>
  <div class="our_location">
    <iframe width="100%" height="600" v-bind:src="settings.props.location_link.value" frameborder="0" scrolling="no" marginheight="0" marginwidth="0"></iframe><br />
    <div id="locations" v-if="settings.blocks.length > 0">
      <div class="location" v-for="(block, index) in settings.blocks"
                      :key="index">
          <h1>{{block.props.city_name.value}}</h1>
          <strong>{{block.props.sector_name.value}}</strong>
          <p class="addresss">{{block.props.address.value}}</p>
          <a v-bind:href="block.props.link" type="button">{{block.props.button_name.value}}</a>
      </div>
    </div>
 </div>
</template>
<!-- #region  -->
<settings>
{
    "name": "our_location",
    "label": "Our Location",
    "props": [
        {
           "type": "url",
            "id": "location_link",
            "default": "",
            "label": "Location Link"
        }
    ],
     "blocks": [
        {
            "type": "our_location",
            "name": "Our Location",
            "props": [
                {
                    "type": "text",
                    "id": "city_name",
                    "label": "City name"
                },
                {
                    "type": "text",
                    "id": "sector_name",
                    "label": "Sector Name"
                },
                {
                    "type": "textarea",
                    "id": "address",
                    "label": "Address",
                    "placeholder": "Address"
                },
                {
                    "type": "text",
                    "id": "button_name",
                    "label": "Name",
                    "default": "Get Directions"
                },
                {
                    "type": "url",
                    "id": "link",
                    "label": "Link",
                    "default": "",
                    "info": "Link to redirect"
                }
            ]
        }
    ],
   "preset":{
    "blocks": [
      {
        "name": "Our Location"
      },
      {
        "name": "Our Location"
      }
    ]
  }
}
</settings>

<!-- #endregion -->
<style scoped lang="less">
.hero__image {
  /deep/ .fy__img {
    width: 100%;
  }
}
.overlay {
  position: absolute;
  top: 55%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  display: flex;
  &__content {
    display: flex;
    flex-direction: column;
    padding: 0 @header-padding-desktop;
    width: 30%;
    align-items: center;
    text-align: center;
    @media @mobile {
      width: 50%;
      padding: 0;
    }
  }
  &__left {
    align-items: flex-start;
    justify-content: flex-start;
    @media @mobile {
      align-items: center;
      justify-content: center;
    }
    .overlay__content {
      align-items: flex-start;
      text-align: left;
      @media @mobile {
        align-items: center;
        text-align: center;
      }
    }
  }
  &__center {
    align-items: center;
    justify-content: center;
  }
  &__right {
    align-items: flex-end;
    justify-content: flex-end;
    @media @mobile {
      align-items: center;
      justify-content: center;
    }
    .overlay__content {
      align-items: flex-end;
      text-align: right;
      @media @mobile {
        align-items: center;
        text-align: center;
      }
    }
  }
  &__image {
    max-width: 100%;
    margin-bottom: 10px;
  }
  &__text {
    font-size: 40px;
    line-height: 49px;
    font-weight: 700;
    margin-bottom: 48px;
    @media @tablet {
      margin-bottom: 35px;
    }
    @media @mobile {
      font-size: 14px;
      margin-bottom: 30px;
    }
  }
}
 #locations{
    position: absolute;
    margin: auto;
    top: 150px;
    left: 0;
    display: flex;
    justify-content: space-between;
    flex-direction: row-reverse;
    align-items: center;
    right: 0;

    }
    .location{
    background: #fff;
    text-align: center;
    max-width: 30%;
    border: 2px solid #000;
    border-style: solid;
    padding: 30px 10px;
    margin: auto;
    }
    .location a{
        background: black;
        color: white;
        padding: 10px 40px;
        text-decoration: none;
        font-size: 16px;
    }
    .location p{
        margin-bottom: 50px;
    }
 @media only screen and (max-width: 767px){
     #locations {
        position: absolute;
        margin: auto;
        top: 150px;
        left: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        right: 0;
    }
    .location{
        background: #fff;
        text-align: center;
        max-width: 100%;
        border: 2;
        border-style: solid;
        padding: 30px 10px;
        margin: 20px auto;
    }
 }
 .our_location{
    position: relative;
 }

</style>

<script>
// import btn from "./../components/common/button.vue";
import emergeImage from "../global/components/common/emerge-image.vue";

export default {
  components: {
    "emerge-img": emergeImage
  },
  props: ["settings", "global_config"],
  watch: {
    settings: function(newVal, oldVal) {},
  },
  mounted() {},
  data: function() {
    return {
      // url: ""
    };
  },
};
</script>
