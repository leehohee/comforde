<template>
  <v-app>
    <v-app-bar
      class="white"
      app
      dense
      flat
      outlined
      justify="space-between"
      no-gutter
      :style="{
        position: 'fixed',
        top: '0px',
        zIndex: '100',
        width: '100%',
        marginLeft: '0px',
      }"
    >
      <v-btn
        v-if="1"
        icon
        nuxt
        to="/webindex"
        :style="{
          marginLeft: '0px',
          paddingLeft: '0px',
          display: 'flex',
          alignItems: 'center',
        }"
      >
        <v-icon>mdi-bell-outline</v-icon>
      </v-btn>
      <v-btn
        v-else
        icon
        nuxt
        to="/"
        :style="{
          marginLeft: '0px',
          paddingLeft: '0px',
          display: 'flex',
          alignItems: 'center',
        }"
      >
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-spacer></v-spacer>

      <v-toolbar-title>
        <nuxt-link to="/"><h4>COMFORDE</h4></nuxt-link>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click.stop="drawer = !drawer"
        :style="{
          marginRight: '0px',
          paddingRight: '0px',
          display: 'flex',
          alignItems: 'center',
        }"
      >
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer
      app
      v-model="drawer"
      right
      :style="{ zIndex: '100' }"
      hide-overlay
      width="100%"
      clipped
    >
      <v-row>
        <v-col cols="1"
          ><v-btn
            class="px-0 mt-1"
            flat
            elevation="0"
            @click.stop="drawer = !drawer"
            ><v-icon large>mdi-chevron-left</v-icon></v-btn
          ></v-col
        >
        <v-col cols="11">
          <v-form ref="form" v-model="valid" @submit.prevent="onSubmitForm">
            <v-text-field
              placeholder="검색어를 입력하세요."
              class="pa-0 ml-4"
              hide-details="false"
              clearable
              rounded
              v-model="search"
            >
            </v-text-field>
          </v-form>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-container>
            
            <v-list-item v-for="(searchItem,i) in searchItems" :key="i" dense>
              <v-list-item-icon>
                <v-icon v-text="i+1"></v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>{{searchItem.content}}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-container>
        </v-col>
      </v-row>
    </v-navigation-drawer>

    <v-main>
      <v-col cols="12" md="12">
        <nuxt />
      </v-col>
    </v-main>

    <v-footer app>
      <v-bottom-navigation
        v-model="value"
        absolute
        
        class="white"
        :style="{
          boxShadow: '0 -1.5px 0 0 rgb(0 0 0 / 10%)',
          paddingRight: '5vw',
          paddingLeft: '3vw',
          position: 'fixed',
          
          top: 'calc(100vh - 56px)',
          zIndex: '100',
          width: '100%',
        }"
        grow
      >
        <v-btn nuxt to="/" value="home" class="white">
          <span :style="{ fontSize: '0.6rem', marginTop: '0.5rem'}"
            >홈</span
          >
          <v-icon>mdi-home</v-icon>
        </v-btn>

        <v-btn nuxt to="/categorypage" value="category" class="white">
          <span :style="{ fontSize: '0.6rem', marginTop: '0.5rem' }"
            >카테고리</span
          >
          <v-icon>mdi-view-grid-outline</v-icon>
        </v-btn>

        <v-btn nuxt to="/likepage" value="favorites" class="white">
          <span :style="{ fontSize: '0.6rem',marginTop: '0.5rem' }"
            >찜목록</span
          >
          <v-icon>mdi-cards-heart-outline</v-icon>
        </v-btn>

        <v-btn nuxt to="/messagepage" value="message" class="white">
          <span :style="{ fontSize: '0.6rem', marginTop: '0.5rem'}"
            >메시지</span
          >
          <v-icon>mdi-email-outline</v-icon>
        </v-btn>

        <v-btn nuxt to="/mypage" value="user" class="white">
          <span :style="{ fontSize: '0.6rem', marginTop: '0.5rem' }"
            >마이페이지</span
          >
          <v-icon>mdi-account-outline</v-icon>
        </v-btn>
      </v-bottom-navigation>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  components: {},

  data() {
    return {
      hashtag: "",
      drawer: false,
      search:'',
    };
  },
  computed:{
        
        searchItems(){
            return this.$store.state.posts.searchItems;
        },
        
    },

  methods: {
    onSerachHashtag() {
      this.$router.push({
        path: `/hashtag/${encodeURIComponent(this.hashtag)}`,
      });
      this.hashtag = "";
    },
    onSubmitForm() {
      this.$store
        .dispatch("posts/searchItems", {
          
          search: this.search,
        })
        .then(() => {
          console.log('잘됨');
        })
        .catch(() => {
          alert("검색실패");
        });
    },
    
  },
};
</script>
    

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@500&display=swap");

a {
  display: inline-block;
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
h4 {
  font-family: "Noto Sans KR";
  font-weight: 500;
}
</style>