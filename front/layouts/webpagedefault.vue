<template>
    <v-app>
            
            <div class="white d-flex justify-center mb-6" :style="{ position:'fixed', top: '0px',zIndex:'101', width:'100vw', height:'74px'}">
            <v-toolbar class="flex-grow-0 flex-shrink-0" dense flat :style="{ position:'relative',zIndex:'100', width:'1170px'}">
                

                <v-toolbar-title style="font-weight:bold">
                  <nuxt-link to="/postindex">Comforde</nuxt-link>
                </v-toolbar-title>
                <v-spacer />
                <v-toolbar-items>
                  <v-form @submit.prevent="onSearchHashtag">
                    <div :style="{ display: 'flex', height: '100%', alignItems: 'center' }">
                      <v-text-field
                        v-model="hashtag"
                        
                        hide-details
                        prepend-icon="mdi-magnify"
                      >
                      <template v-slot:label>
                        <span style="font-size:14px">디자이너를 검색해 보세요</span>
                      </template>
                      </v-text-field>
                    </div>
                  </v-form>
                  <v-btn text :style="{ display: 'flex', alignItems: 'center' }">
                    <nuxt-link to="/postindex">디자이너 등록</nuxt-link>
                  </v-btn>






                  <v-btn text nuxt to="/" :style="{ display: 'flex', alignItems: 'center' }">
                    <div>로그인</div>
                  </v-btn>
                  <v-btn color="yellow" elevation="0" nuxt to="/signup" :style="{ display: 'flex', alignItems: 'center' }">
                    <div>무료 회원가입</div>
                  </v-btn>









                </v-toolbar-items>
                    
                    
                
            </v-toolbar>
            </div>
            <div class="white d-flex justify-center mb-6" :style="{ position:'fixed', top: '50px',zIndex:'101', width:'100vw',borderBottom: '1px solid #e4e5ed'}">
            <v-toolbar class="flex-grow-0 flex-shrink-0 nowrap" dense flat :style="{ position:'relative',zIndex:'100', width:'1170px'}">
              <v-card class="d-flex" flat tile style="font-weight:700">
                <v-menu
                  open-on-hover
                  bottom
                  
                  
                  :offset-y="offset"
                >
                  <template v-slot:activator="{ on, attrs }">
                    
                    <v-btn
                      text
                      class="justify-left ml-n4"
                      :style="{ display: 'flex', alignItems: 'center' }"
                      v-bind="attrs"
                      v-on="on"
                    >
                    <v-icon>mdi-menu</v-icon>
                      전체카테고리
                    <v-icon>mdi-menu-down</v-icon>
                    </v-btn>
                  </template>
                  <v-card elevation="24">
                    <v-list>
                      <v-list-item
                        v-for="(item, index) in items"
                        :key="index"
                        
                      >
                        <v-list-item-title><v-badge
                          color="white"
                          icon="mdi-alpha-n"
                          
                          bordered
                          
                        >{{ item.title }}
                        </v-badge>
                        </v-list-item-title>
                      </v-list-item>
                    </v-list>
                  </v-card>
                </v-menu>
                <v-btn text :style="{ display: 'flex', alignItems: 'center' }">
                  <div>로고</div>
                </v-btn>
                <v-btn text :style="{ display: 'flex', alignItems: 'center' }">
                  <div>패키지</div>
                </v-btn>
                <v-btn text :style="{ display: 'flex', alignItems: 'center' }">
                  <div>그밖에</div>
                </v-btn>
                
              </v-card>
              <v-spacer />  
                <v-card flat tile>
                  
                  
                  
                  <v-btn text :style="{ display: 'flex', alignItems: 'center' }">
                    <div>원하는 디자이너를 못 찾겠다면 ></div>
                  </v-btn>
                </v-card>
                    
                    
                
            </v-toolbar>

            </div>
        <v-row no-gutters>
                
          <v-divider></v-divider>
            
        </v-row>   







        
        <v-row no-gutters :style="{ paddingTop:'100px', paddingBottom:'80px'}" justify="start">
            <v-col cols="12" md="6">



               
               <nuxt></nuxt>
               





            </v-col>
            <v-col cols="12" md="6">
                
            </v-col>

        </v-row>











        <v-footer
          :style="{backgroundColor:'white', width:'100vw',borderTop: '1px solid darkgray'}"
          padless
          class="d-flex justify-center mb-1"
        >


          <v-card
            flat
            tile
            class="text-center"
          >
          </v-card>
          <v-card
            flat
            tile
            class="text-center"
          >
            <v-card-text>
              <v-btn
                v-for="icon in icons"
                :key="icon"
                class="mx-4"
                icon
              >
                <v-icon size="24px">
                  {{ icon }}
                </v-icon>
              </v-btn>
            </v-card-text>

            <v-card-text class="pt-0" :style="{ fontSize:'12px',position:'relative',zIndex:'100', width:'1170px'}">
              (주)컴포디는 통신판매중개자이며, 통신판매의 당사자가 아닙니다. 상품, 상품정보, 거래에 관한 의무와 책임은 판매회원에게 있습니다.<br>

              (주)컴포디 사이트의 상품/판매회원/중개 서비스/거래 정보, 콘텐츠, UI 등에 대한 무단복제, 전송, 배포, 스크래핑 등의 행위는 저작권법, 콘텐츠산업 진흥법 등 관련법령에 의하여 엄격히 금지됩니다. [안내 보기]
            </v-card-text>

            

            <v-card-text class="">
              <strong>Copyright © 2021 Comforde Inc. All rights reserved.</strong>
            </v-card-text>
          </v-card>
        </v-footer>

    </v-app>  
</template>

<script>

export default {
    created(){
      this.$router.push('/webindex')
    },
    components: {
        
        
    },
    
    data(){
        return {
            hashtag: '',
            items: [
              { title: '로고·브랜딩' },
              { title: '상세·이벤트페이지' },
              { title: '명함·인쇄·홍보물' },
              { title: 'PPT·인포그래픽' },
              { title: '웹·모바일 디자인' },
              { title: '패키지 디자인' },
              { title: '일러스트·캐릭커쳐' },
              { title: '웹툰·캐릭터·이모티콘' },
              { title: '블로그·SNS·썸네일' },
              { title: '포토샵·파일변환' },
              { title: '제품·3D프린팅' },
              { title: '공간디자인' },
              { title: '북·앨범디자인' },
              { title: '캘리그라피·폰트' },
              { title: '의류디자인' },
              { title: '간판·시공' },
            ],
            offset: true,
            icons: [
              'mdi-facebook',
              'mdi-twitter',
              'mdi-linkedin',
              'mdi-instagram',
            ],    
        };
    },
    
    
    methods:{
        onSerachHashtag(){
            this.$router.push({
                path: `/hashtag/${encodeURIComponent(this.hashtag)}`,
            });
            this.hashtag='';
        },

    },

    
}

</script>
    

<style scoped>
    a {
        display:inline-block;
        text-decoration: none;
        color: inherit;
    }
    ul {
        text-decoration: none;
        list-style: none;
    }
    li {
        text-decoration: none;
    }
    

    .lnb {
  overflow-x: auto;
  background-color: #fff;
  position:fixed;
  top: 40px;
  z-index:100; }
  .lnb::-webkit-scrollbar {
    display: none !important; }
  .lnb-list {
    display: inline-flex;
    align-items: center;
    justify-content: flex-start;
    height: 40px;
    padding: 0 7px;
    margin-left: -15px;
    white-space: nowrap;
    border-bottom: 1px solid #e0e2e7; }
  .lnb-item.is-active a {
    color: #3da5f5;
    border-bottom-color: #3da5f5; }
  .lnb-item a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-size: 13px;
    line-height: 20px;
    letter-spacing: -0.01em;
    color: #191a20;
    height: 40px;
    padding: 0 8px;
    font-weight: 700;
    border-bottom: 2px solid transparent; }
    .lnb-item a:hover {
      color: #3da5f5; }
  @media screen and (min-width: 768px) {
    .lnb {
      height: 50px;
      overflow-x: visible;
      border-bottom: 1px solid #e0e2e7; }
      .lnb-list {
        height: auto;
        padding: 0;
        margin-left: 0;
        border-bottom: 0; }
      .lnb-item a {
        font-size: 14px;
        line-height: 24px;
        letter-spacing: -0.01em;
        height: 50px; } }
</style>