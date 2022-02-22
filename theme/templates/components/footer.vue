<template>
  <div
    class="main-footer"
    :style="
      `--footer_nav_hover_color:${global_config.props.footer_nav_hover_color};border-top: 1px solid ${global_config.props.footer_border_color};background-color: ${global_config.props.footer_bg_color};color: ${global_config.props.footer_text_color}`
    "
  >
    <div class="main-footer__bottom">
      <div class="about-block" v-if="context.description !== ''">
        <h5 class="footer-head">ABOUT US</h5>
        <p class="desc">
          {{ context.description }}
        </p>
      </div>
      <div class="grid__item footer__item--158fcb94-3842-4595-8844-9f971c660134" data-type="custom"><style data-shopify="">@media only screen and (min-width: 769px) and (max-width: 959px) {
              .footer__item--158fcb94-3842-4595-8844-9f971c660134 {
                width: 50%;
                padding-top: 40px;
              }
              .footer__item--158fcb94-3842-4595-8844-9f971c660134:nth-child(2n + 1) {
                clear: left;
              }
            }
            @media only screen and (min-width: 960px) {
              .footer__item--158fcb94-3842-4595-8844-9f971c660134 {
                width: 28%;
              }
              
            }</style><div class="footer__item-padding"><p class="h4 footer__title small--hide">Payment's Accepted</p>
    <div id="Footer-158fcb94-3842-4595-8844-9f971c660134" class="collapsible-content collapsible-content--small">
    <div class="collapsible-content__inner">
      <div class="footer__collapsible"><div class="image-wrap text-spacing" style="height: 0; padding-bottom: 39.53125%;"><img class="lazyautosizes lazyloaded" data-widths="[360, 540, 720, 900, 1080, 1600]" data-aspectratio="2.5296442687747036" data-sizes="auto" role="presentation" alt="" data-srcset="//cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_360x.jpg?v=1630319405 360w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_540x.jpg?v=1630319405 540w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_720x.jpg?v=1630319405 720w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_900x.jpg?v=1630319405 900w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_1080x.jpg?v=1630319405 1080w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_1600x.jpg?v=1630319405 1600w" sizes="240px" srcset="//cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_360x.jpg?v=1630319405 360w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_540x.jpg?v=1630319405 540w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_720x.jpg?v=1630319405 720w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_900x.jpg?v=1630319405 900w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_1080x.jpg?v=1630319405 1080w, //cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_1600x.jpg?v=1630319405 1600w">
            <noscript>
              <img class="lazyloaded" src="//cdn.shopify.com/s/files/1/2529/7758/files/WhatsApp_Image_2021-08-30_at_3.59.30_PM_400x.jpg?v=1630319405" alt="">
            </noscript>
          </div><p>{{ context.app_info.copyright_text }}</p>
      </div>
    </div>
  </div>
</div>
</div>
      <div class="item-block">
        <div
          class="link-block"
          v-for="(item, index) in context.navigation"
          :key="index"
        >
          <h5 class="footer-head">
            <fdk-link :link="item.link">
              {{ item.display }}
            </fdk-link>
          </h5>
          <ul
            class="list"
            v-for="(subItem, index) in item.sub_navigation"
            :key="index"
          >
            <li>
              <fdk-link :link="subItem.link">
                {{ subItem.display }}
              </fdk-link>
            </li>
          </ul>
        </div>
      </div>
      <div class="social-link-block">
        <h5 class="footer-head">SIGN UP AND SAVE</h5>
        <p>Subscribe to get special offers, free giveaways, and once-in-a-lifetime deals.</p>
        <div class="flat">
        <form method="post" action="/contact#newsletter-footer" id="newsletter-footer" accept-charset="UTF-8" class="contact-form"><input type="hidden" name="form_type" value="customer"><input type="hidden" name="utf8" value="✓"><label for="Email-1494292487693" class="hidden-label">Enter your email</label>
          <input type="hidden" name="contact[tags]" value="prospect,newsletter">
          <input type="hidden" name="contact[context]" value="footer">
          <div class="footer__newsletter">
            <input type="email" value="" placeholder="Enter your email" name="contact[email]" id="Email-1494292487693" class="footer__newsletter-input" autocorrect="off" autocapitalize="off">
            <button type="submit" class="footer__newsletter-btn" name="commit" aria-label="Subscribe">
                <svg aria-hidden="true" focusable="false" role="presentation" class="icon icon-email" viewBox="0 0 64 64"><path d="M63 52H1V12h62zM1 12l25.68 24h9.72L63 12M21.82 31.68L1.56 51.16m60.78.78L41.27 31.68"></path></svg>              <span class="footer__newsletter-btn-label">
                Subscribe
              </span>
            </button>
          </div></form>
          <!--
          <ul
            class="list"
            v-if="
              context.support.contact.email.active &&
                context.support.contact.email.email.length > 0
            "
          >
            <li>Email: {{ context.support.contact.email.email[0].value }}</li>
          </ul>
          
          <ul
            class="list"
            v-if="
              context.support.contact.phone.active &&
                context.support.contact.phone.phone.length > 0
            "
          >
            <li>Call : {{ context.support.contact.phone.phone[0].number }}</li>
          </ul> -->
          <ul class="row">
            <li
              v-for="(item, index) in context &&
                context.app_info &&
                context.app_info.social_links"
              :key="index"
            >
              <span v-if="item.link">
                <fdk-link :link="item.link" target="_blank" :title="item.title">
                  <img alt="social.title" :src="item.icon" />
                </fdk-link>
              </span>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <!-- <div class="sub-footer_bottom">
      <div>{{ context.app_info.copyright_text }}</div>
      <div></div>
    </div> -->
  </div>
</template>

<script>
import { logoUrl } from "../../helper/utils";
export default {
  props: {
    context: {},
  },
  data() {
    return {
      isMounted: false,
    };
  },
  mounted() {
    this.isMounted = true;
  },
  computed: {
    getLogoUrl() {
      return logoUrl(this.context.logo, this.context.mobileLogo);
    },
  },
};
</script>

<style lang="less" scoped>
.main-footer {
  margin-top: 3.125rem;
  font-size: 0.8125rem;
  letter-spacing: 0.65px;
  font-size: 12px;
  color: white;
  overflow-x:hidden;
  @media @mobile {
    text-align: center;
  }
  .sub-footer_bottom {
    padding: 36px 24px;
    display: flex;
    flex-direction: row;

    @media @mobile {
      flex-direction: column;
    }
    @media screen and (max-width: 709px) {
      flex-direction: column;
    }
    justify-content: space-between;
  }

  .footer-links {
    display: flex;
    align-items: center;
    justify-content: center;
    @media @mobile {
      flex-wrap: wrap;
    }
    .link-item {
      margin-right: 0.9375rem;
      @media @mobile {
        margin-bottom: 0.625rem;
      }
      // color: @color-gray;
      position: relative;
      &:after {
        bottom: 0;
        content: "";
        display: block;
        height: 1px;
        left: 50%;
        position: absolute;
        background: var(--footer_nav_hover_color);
        transition: width 0.3s ease 0s, left 0.3s ease 0s;
        width: 0;
      }
      &:hover {
        &:after {
          width: 100%;
          left: 0;
        }
        color: var(--footer_nav_hover_color);
      }
    }
  }

  &__bottom {
    padding: 25px 25px;
    display: flex;
    flex-direction: row;
    @media screen and (max-width: 709px) {
      flex-direction: column;
    }
    justify-content: space-between;
    .about-block {
      .footer-head {
        font-size: 16px;
        margin-bottom: 16px;
        @media @mobile {
          font-size: 16px;
        }
      }
      .desc {
        margin-bottom: 10px;
        width: 250px;
        line-height: 2;
        @media screen and (max-width: 1111px) {
          max-width: 128px;
        }

        @media @tablet {
          max-width: 112px;
        }
        @media screen and (max-width: 709px) {
          max-width: max-content;
        }
        @media @mobile {
          max-width: max-content;
        }
      }

      .email {
        width: 250px;
        margin-top: 20px;
        margin-bottom: 20px;
        height: 30px;
        border: 1px solid white;
      }
      input[type="text"],
      textarea {
        background-color: var(--footer_bg_color);
        border-color: white;
      }
      .btn {
        width: 140px;
        height: 30px;
        color: white;
        background-color: black;
        margin-top: 30px;
        margin-bottom: 30px;
        letter-spacing: 4px;
      }
      ::placeholder {
        color: white;
      }
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      width: 25%;
      @media screen and (max-width: 709px) {
        width: 100%;
        align-items: center;
        text-align: center;
      }
      @media @mobile {
        width: auto;
      }
    }
    .link-block {
      @media @mobile {
        margin: 8px;
        width: auto;
      }
      .footer-head {
        font-size: 16px;

        margin-bottom: 16px;
        @media @mobile {
          font-size: 16px;
        }
      }
      li {
        margin-bottom: 10px;
        @media @mobile {
          font-size: 14px;
        }
      }
      .row {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        @media @mobile {
          justify-content: center;
        }
        li {
          margin: auto 2px;
          img {
            width: 30px;
            color: var(--footer_bg_color);
          }
        }
      }
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      width: 25%;
    }
    .social-link-block {
      @media screen and (max-width: 709px) {
        width: 100%;
        align-items: center;
        text-align: center;
        margin-top: 10px;
      }
      @media @mobile {
        margin: 8px;
        width: auto;
      }
      .flat {
        @media screen and (max-width: 709px) {
          display: flex;
          flex-direction: row;
          justify-content: space-evenly;
          width: 100%;
        }
        @media @mobile {
          flex-direction: column;
          width: auto;
          justify-content: space-evenly;
        }
      }
      .footer-head {
        font-size: 16px;

        margin-bottom: 16px;
        @media @mobile {
          font-size: 16px;
        }
      }
      li {
        margin-bottom: 10px;
        @media @mobile {
          font-size: 14px;
        }
      }
      .row {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        @media screen and (max-width: 709px) {
          justify-content: center;
        }
        @media @mobile {
          justify-content: center;
        }
        li {
          margin: auto 2px;
          img {
            width: 30px;
            color: var(--footer_bg_color);
          }
        }
      }
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      width: 25%;
    }
    .item-block {
      display: flex;
      flex-wrap: wrap;
      @media screen and (min-width: 709px) {
        justify-content: space-evenly;
        width: 50%;
      }
      @media screen and (max-width: 709px) {
        justify-content: center;
      }
      @media @mobile {
        flex-direction: column;
      }
    }
    @media @tablet {
      padding: 1.25rem 3.125rem 1.875rem 3.125rem;
    }
    @media @mobile {
      flex-direction: column;
    }
    .logo-block {
    }
    .social-block {
      margin-left: auto;
      display: flex;
      align-items: center;
      flex: 0 0 17%;
      justify-content: flex-end;
      @media @mobile {
        flex: 0 0 100%;
        margin-top: 30px;
        justify-content: center;
        margin-left: unset;
      }
      .icons-box {
        display: flex;
        flex-wrap: wrap;
        li {
          margin-right: 5px;
          &:last-child {
            margin-right: 0;
          }
        }
      }
    }

    .app-logo {
      max-width: 80px;
      margin-bottom: 0.3125rem;
    }
  }
}
</style>
