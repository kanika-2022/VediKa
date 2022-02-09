<template>
    <div>
        <h1>FAQ</h1>
           <div id="faqs">
               <div class="contents">
                   <img v-bind:src="settings.props.image_link">
                   <div class="title">{{settings.props.title.value}}</div>
                   <p>{{settings.props.faqContent.value}}</p>
               </div>
           </div>
        </div>
</template>
<!-- Need only one root element-->
<settings>
{
    "name": "shipping-policy",
    "label": "Shipping Policy",
    "blocks": [
        {
            "type": "shipping-policy",
            "name": "FAQ",
            "props": [
                {
                    "type": "text",
                    "id": "heading_name",
                    "label": "Heading Name"
                },
                {
                    "type": "textarea",
                    "id": "faqtext",
                    "label": "Text for FAQ",
                    "default": "",
                    "info": "Text for FAQ",
                    "placeholder": "Text"
                },
                {
                    "type": "image_picker",
                    "id": "author_image",
                    "default": "",
                    "label": "Author Image"
                }
            ]
        }
    ],
   "preset":{
    "blocks": [
      {
        "name": "FAQ"
      },
      {
        "name": "FAQ"
      },
      {
        "name": "FAQ"
      }
    ]
  }

}
</settings>
<script>
import emergeImage from "./../global/components/common/emerge-image.vue";

export default {
   props: ["settings"],
   name: 'shipping-policy',
    components: {
    "emerge-image": emergeImage,
  },
   data(){
    //    return {
    //    headingName: 'FAQ',
    //    contents:[
    //     {imageUrl:'https://cdn.shopify.com/s/files/1/2529/7758/files/IMG_0061_540x.jpg?v=1628580933',title:'Made To Order',content:'Each of our outfits can be Custom Made to your measurements. You can either fill in your measurements on the product page under "Custom Fit" or WhatsApp them to us with your order number.'},
    //     {imageUrl:'https://cdn.shopify.com/s/files/1/2529/7758/files/IMG_0067_540x.jpg?v=1629797666',title:'Express Shipping',content:'We usually take around 10-12 days to dispatch your orders. Incase you need them on a specific date do reach out to us on WhatsApp and our team will assist you accordingly.'},
    //     {imageUrl:'https://cdn.shopify.com/s/files/1/2529/7758/files/IMG_0066_540x.jpg?v=1629797809',title:'Customizations',content:'Each outfit being completely hand crafted & made to order, our team can always assist you with basic customizations to give you the perfect look.'}
    //    ]
    // }
  }
}
</script>
<style scoped>
h1{
    text-align: center;
}
#faqs{
    display: flex;
    padding: 0 40px;
}
.contents{
    width:30%;
    margin-left:40px;
    margin-bottom:20px;
}
.contents img{
    max-width:100%
}
</style>