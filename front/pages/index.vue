<template>
    <v-container class="ma-0 pa-0" fluid>
    
        <v-carousel
        :show-arrows="false"
        height="130"
        hide-delimiter-background
        delimiter-icon="mdi-circle-medium"
        >
            <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
            
            ></v-carousel-item>
        </v-carousel>

        <CategoryMenu />

        <LikeServiceMenu />
        <RecommendListMenu :mainItems="mainItems"/>
        <MainFooterMenu />
        
        


        
    </v-container>      
</template>

<script>
import CategoryMenu from '~/components/CategoryMenu';
import LikeServiceMenu from '~/components/LikeServiceMenu';
import RecommendListMenu from '../components/RecommendListMenu.vue';
import MainFooterMenu from '../components/MainFooterMenu.vue';


export default {
    components: {
        CategoryMenu,
        LikeServiceMenu,
        RecommendListMenu,
        MainFooterMenu,
    },
    
    data () {
      return {
        items: [
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/Au8Dj_curated_content_item_main_mobile_654.jpg",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/YFwsc_curated_content_item_main_mobile_655.png",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/Au8Dj_curated_content_item_main_mobile_654.jpg",
        },
        {
          src: "https://d2v80xjmx68n4w.cloudfront.net/assets/images/curated_contents/YFwsc_curated_content_item_main_mobile_655.png",
        },
      ],
        
      }
    },
    fetch({store}){  //fetch는 보통 store 넣을때 많이 쓴다.
        return store.dispatch('posts/loadItems', { reset: true});
    },
    computed:{
        height (){
            switch (this.$vuetify.breakpoint.name){
                case 'xs' : return 100
                case 'md' : return 500
                default : return 300
            }
        },
        mainItems(){
            return this.$store.state.posts.mainItems;
        },

        
    },
}
</script>

<style>
a {
    text-decoration: none !important;
    color:black !important;
}
.border-top-solid {
    border-top : solid #e6e6e6 1px !important;
}
.border-bottom-solid {
    border-bottom : solid #e6e6e6 1px !important;
}
</style>