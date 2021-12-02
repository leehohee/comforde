<template>
    <div>
        <v-container>
            <v-row>
                
                
                <v-card
                    color="white"
                    max-height="98"
                    class="pa-0 ma-0"
                    elevation="0"
                    nuxt to="/"

                >
                    <div class="d-flex flex-no-wrap">

                    <v-avatar
                        class="ma-0"
                        size="98"
                        tile
                    >
                        <v-img
                        src="https://d2v80xjmx68n4w.cloudfront.net/gigs/QbVBu1625654810.jpg"
                        max-height="98"
                        ></v-img>
                    </v-avatar>
                    <div class="pl-3">
                        <v-card-subtitle
                        
                        v-text="'미술, 디자인, 작가가 모여 감각적인 로고 제작해 드립니다.'"
                        ></v-card-subtitle>
                        <br>
                        <v-card-subtitle
                        
                        v-text="'로고고디자인'"
                        ></v-card-subtitle>
                        <v-row
                        align="center"
                        class="ml-n1 mt-2"
                        >
                            
                        </v-row>

                        <v-card-actions>
                        

                        
                        </v-card-actions>
                    </div>

                    
                    </div>
                    
                </v-card>
              
            </v-row>
            <v-row class="mt-10">
              <v-card width="100%" fluid>
                <v-btn
                block
                outlined
                x-large
                class="justify-start"
                >
                <v-radio
                  
                  
                  label="11,000원"
                  
                ></v-radio>
                STANDARD
                </v-btn>
              </v-card>
              
              <v-card width="100%" fluid>
                <v-btn
                block
                outlined
                x-large
                class="justify-start"
                >
                <v-radio
                  
                  
                  label="22,000원"
                  
                ></v-radio>
                DELUXE
                </v-btn>
              </v-card>

              <v-card width="100%" fluid>
                <v-btn
                block
                outlined
                x-large
                class="justify-start"
                >
                <v-radio
                  
                  
                  label="33,000원"
                  
                ></v-radio>
                PREMIUM
                </v-btn>
              </v-card>

            </v-row>
        </v-container>
    </div>

</template>

<script>
export default {
    layout:'buydefault'
}
</script>

<style>

</style>