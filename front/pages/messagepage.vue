<template>
    <div>
        <div v-if="me">
         <v-list
          two-line
          subheader
        >
          <v-subheader class="d-flex align-center mt-0">
            <v-text-field
            prepend-icon="mdi-magnify"
            label=""
            placeholder="닉네임과 메모로 검색하세요."
            filled
            rounded
            dense
            class="white pt-6"
            ></v-text-field>
            <v-btn @click="sheet = !sheet" dense flat x-small elevation="0" class="px-0">
            <v-icon>
                mdi-cog-outline
            </v-icon>
            </v-btn>
            <v-bottom-sheet v-model="sheet">
            <v-sheet
                class="text-center"
                height="100px"
                rounded
            >
                
                <div class="pt-4">
                닉네임, 메모로 검색
                </div>
                <div class="pt-4">
                메시지로 검색
                </div>
            </v-sheet>
            </v-bottom-sheet>
          </v-subheader>

          <v-list-item
            v-for="item in items"
            :key="item.title"
            link
          >
            
            <v-list-item-avatar>
              <v-icon :class="[item.iconClass]">
                {{ item.icon }}
              </v-icon>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>

              <v-list-item-subtitle>{{ item.subtitle }}</v-list-item-subtitle>
            </v-list-item-content>
            
            <v-list-item-action>
              <v-btn icon>
                <v-icon color="grey lighten-1">
                  mdi-star-outline
                </v-icon>
              </v-btn>
            </v-list-item-action>
            
          </v-list-item>

          

          

          <v-list-item
            v-for="item in items2"
            :key="item.title"
            link
          >
            <v-list-item-avatar>
              <v-icon :class="[item.iconClass]">
                {{ item.icon }}
              </v-icon>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>

              <v-list-item-subtitle>{{ item.subtitle }}</v-list-item-subtitle>
            </v-list-item-content>

            <v-list-item-action>
              <v-btn
                icon
                ripple
              >
                <v-icon color="grey lighten-1">
                  mdi-star-outline
                </v-icon>
              </v-btn>
            </v-list-item-action>
            
          </v-list-item>
        </v-list>
        </div>

        <div v-else>
          <LoginForm />
        </div>


    </div>
    
    
</template>

<script>
import LoginForm from '~/components/LoginForm';


export default {
    components: {
        
        
        LoginForm,
    },
    layout:'messagedefault',
    data () {
      return {
        sheet: false,
        dialog: false,
        items: [
          { icon: 'mdi-account', iconClass: 'red lighten-1 white--text', title: '섬세한또치4467', subtitle: '잘 부탁드립니다.' },
          { icon: 'mdi-account', iconClass: 'green lighten-1 white--text', title: 'globe94', subtitle: '네 알겠습니다.' },
          { icon: 'mdi-account', iconClass: 'grey lighten-1 white--text', title: 'atoneK9', subtitle: '좋은 글 남겨주셔서 감사드립니다.' },
        ],
        items2: [
          { icon: 'mdi-account', iconClass: 'blue white--text', title: '코코넛ENT', subtitle: '네 감사합니다.' },
          { icon: 'mdi-account', iconClass: 'amber white--text', title: '영상제작스튜디오', subtitle: '33만원으로 제작된 영상입니다.' },
        ],
      }
    },
    computed:{
        me(){
            return this.$store.state.users.me;
        },
        
    },
}
</script>

<style>

</style>