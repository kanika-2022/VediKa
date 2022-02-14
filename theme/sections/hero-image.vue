<template>
  <div :class="{
      'section-main-container': !settings.props.full_width.value,
      'full-width-section': settings.props.full_width.value,
    }">
      <emerge-img
        v-if="settings.props.image.value"
        :src="settings.props.image.value"
        :sources="[]"
        class="hero__image"
      />
     
  </div>
</template>
<!-- #region  -->

<settings>
{
    "name": "hero_image",
    "label": "Hero Image",
    "props": [
        {
            "id": "image",
            "type": "image_picker",
            "label": "Hero Image",
            "default": ""
        },
       
       {
            "type": "checkbox",
            "id": "full_width",
            "default": true,
            "label": "Full width",
            "info": "Check to allow items to take entire width of the viewport"
        }
    ]
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
