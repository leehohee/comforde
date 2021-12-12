<template>
    <div class="justify-center" :style="{ zIndex:'101', width:'100vw'}">
  <v-container class="flex-grow-0 flex-shrink-0" dense flat :style="{ position:'relative',zIndex:'100', width:'1170px'}">
      
      <div class="pt-10" :style="{ fontSize:'18px', fontWeight:'600'}">카테고리에서 인기있어요!</div>
      <div class="ml-n16" :style="{ position:'relative',zIndex:'100', width:'100%'}">
            <v-sheet
                
                elevation="0"
                width="1270px"
            >
                <v-slide-group
                v-model="model"
                class="py-4"
                active-class="success"
                
                >
                <v-slide-item
                    v-for="n in 15"
                    :key="n"
                    v-slot="{ active, }"
                >
                    <v-card
                    :color="active ? undefined : 'lighten-1'"
                    class="ma-4"
                    height="150"
                    width="222"
                    
                    
                    >
                      <v-skeleton-loader
                        v-bind="attrs"
                        type="article"
                        ></v-skeleton-loader>
                    <v-row
                        class="fill-height"
                        align="center"
                        justify="center"
                    >
                        <v-scale-transition>
                        <v-icon
                            v-if="active"
                            color="white"
                            size="48"
                            v-text="'mdi-close-circle-outline'"
                        ></v-icon>
                        </v-scale-transition>
                    </v-row>
                    </v-card>
                </v-slide-item>
                </v-slide-group>
            </v-sheet>
          
          
      </div>
       
      <div class="pt-10" :style="{ fontSize:'18px', fontWeight:'600'}">로고 카테고리에서 인기있어요!</div>
      <div class="ml-n16" :style="{ position:'relative',zIndex:'100', width:'100%'}">
            <v-sheet
                
                elevation="0"
                width="1270px"
            >
                <v-slide-group
                v-model="model"
                class="py-4"
                active-class="success"
                
                >
                <v-slide-item
                    v-for="n in 15"
                    :key="n"
                    v-slot="{ active, toggle }"
                >
                    <v-card
                    :color="active ? undefined : 'grey lighten-1'"
                    class="ma-4"
                    height="150"
                    width="222"
                    @click="toggle"
                    >
                    <v-row
                        class="fill-height"
                        align="center"
                        justify="center"
                    >
                        <v-scale-transition>
                        <v-icon
                            v-if="active"
                            color="white"
                            size="48"
                            v-text="'mdi-close-circle-outline'"
                        ></v-icon>
                        </v-scale-transition>
                    </v-row>
                    </v-card>
                </v-slide-item>
                </v-slide-group>
            </v-sheet>
          
          
      </div>

      <div class="pt-10" :style="{ fontSize:'18px', fontWeight:'600'}">패키지 카테고리에서 인기있어요!</div>
      <div class="ml-n16" :style="{ position:'relative',zIndex:'100', width:'100%'}">
            <v-sheet
                
                elevation="0"
                width="1270px"
            >
                <v-slide-group
                v-model="model"
                class="py-4"
                active-class="success"
                
                >
                <v-slide-item
                    v-for="n in 15"
                    :key="n"
                    v-slot="{ active, }"
                >
                    <v-card
                    :color="active ? undefined : 'grey lighten-1'"
                    class="ma-4"
                    height="150"
                    width="222"
                    
                    >
                    <v-row
                        class="fill-height"
                        align="center"
                        justify="center"
                    >
                        <v-scale-transition>
                        <v-icon
                            v-if="active"
                            color="white"
                            size="48"
                            v-text="'mdi-close-circle-outline'"
                        ></v-icon>
                        </v-scale-transition>
                    </v-row>
                    </v-card>
                </v-slide-item>
                </v-slide-group>
            </v-sheet>
          
          
      </div>
  </v-container>  

    <v-card
    class="mx-auto pl-15 py-5"
    width="1170"
    tile
    :style="{ backgroundColor:'#081e36'}"
  >
    <v-list-item two-line>
      <v-list-item-content>
        <v-list-item-subtitle class="white--text">디자인에서 패키지까지</v-list-item-subtitle>
        <v-list-item-title class="text-h5 mb-1 mt-2 white--text">
          디자이너가 가진 모든 고민들, 한방에 해결하세요! 
        </v-list-item-title>
      </v-list-item-content>

      
    </v-list-item>

    <v-card-actions class="pl-4">
      <v-btn
        
        color="yellow"
        
      >
        디자인 의뢰하기 >
      </v-btn>
    </v-card-actions>
  </v-card>

    </div>
</template>

<script>
import PostCard from '~/components/PostCard';
import PostForm from '~/components/PostForm';
import LoginForm from '~/components/LoginForm';
export default {
    layout:'webpagedefault',
    components: {
        PostCard,
        PostForm,
        LoginForm,
    },
    
    data() {
        return {
            name: 'Nuxt.js',
            model: null,
            
            randomimg : [],
            attrs: {
                class: '',
                boilerplate: true,
                elevation: 0,
            },
        };
    },
    computed:{
        me(){
            return this.$store.state.users.me;
        },
        mainPosts(){
            return this.$store.state.posts.mainPosts;
        },
        hasMorePost(){
            return this.$store.state.posts.hasMorePost;
        },
        randomImg(){
            return this.$store.state.posts.randomPaths;
        }
    },
    
    
    
    
    methods:{
        
    },
    head(){
        return {
            title: '메인페이지'
        }
    },
    

};
</script>

<style>

</style>