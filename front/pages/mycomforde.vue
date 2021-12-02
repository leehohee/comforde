<template>
    <div>
        <v-container>
            <v-row>
                <v-card elevation="0" width="100%" class="d-flex-row justify-center align-center">
                    <div class="text-right"><v-btn outlined elevation="0" x-small rounded>계정 설정</v-btn></div>
                    <div class="d-flex"><v-img contain width="86" height="86" src="https://jejuhydrofarms.com/wp-content/uploads/2020/05/blank-profile-picture-973460_1280.png"></v-img></div>
                    <div class="text-center mt-2"><h3>웃는남자</h3></div>
                    <div class="text-center grey--text">NEW</div>
                    <v-row dense class="mt-3">
                        <v-col cols="4">
                            <div class="text-center text-caption">크몽 캐시</div>
                            <div class="text-center font-weight-bold">0원</div>
                        </v-col>
                        <v-divider vertical inset/>
                        <v-col cols="4">
                            <div class="text-center text-caption">쿠폰</div>
                            <div class="text-center font-weight-bold">1장</div>
                        </v-col>
                        <v-divider vertical inset/>
                        <v-col cols="4">
                            <div class="text-center text-caption">전문가 마일리지</div>
                            <div class="text-center font-weight-bold">20,000원</div>
                        </v-col>
                    </v-row>
                </v-card>
                
            </v-row>    
            
            <v-row class="mt-8">
                <v-card width="100%" :style="{backgroundImage:'linear-gradient(136deg, #2d2d33, #18181f)'}">
                    <v-container>
                        <v-row class=" mt-1">
                            <v-col class="white--text font-weight-bold" cols="8">판매중인 주문<span class="grey--text text-caption">(최근 3개월)</span></v-col>
                            <v-col class="grey--text text-caption text-right" cols="4">전체보기 ></v-col>
                        </v-row>
                        <v-row min-height="100%" class="d-flex">
                            <v-col>
                                <div class="py-3 text-center yellow--text" width="58px" min-height="58px" :style="{borderRadius:'50%', border:'solid 2px rgba(141,109,8,1)'}">
                                    <h2>0</h2>
                                </div>
                                <div class="pt-1 grey--text text-center"><h5>미작성</h5></div>
                            </v-col>
                            <v-col>
                                <div class="py-3 text-center yellow--text" width="58px" height="58px" :style="{borderRadius:'50%', border:'solid 2px rgba(141,109,8,1)'}">
                                    <h2>0</h2>
                                </div>
                                <div class="pt-1 grey--text text-center"><h5>진행중</h5></div>
                            </v-col>
                            <v-col>
                                <div class="py-3 text-center yellow--text" width="58px" height="58px" :style="{borderRadius:'50%', border:'solid 2px rgba(141,109,8,1)'}">
                                    <h2>1</h2>
                                </div>
                                <div class="pt-1 grey--text text-center"><h5>발송중</h5></div>
                            </v-col>
                            <v-col>
                                <div class="py-3 text-center yellow--text" width="58px" height="58px" :style="{borderRadius:'50%', border:'solid 2px rgba(141,109,8,1)'}">
                                    <h2>0</h2>
                                </div>
                                <div class="pt-1 grey--text text-center"><h5>판매완료</h5></div>
                            </v-col>
                        </v-row>
                        <v-sheet class="mt-5 mx-4">
                        
                            <v-row :style="{backgroundColor:'#1c1c23'}">
                                <v-col class="grey--text text-caption" cols="6">발송일 마감입박 0건</v-col>
                                <v-col class="grey--text text-caption" cols="6">문제해결요청 0건</v-col>
                                <v-col class="grey--text text-caption" cols="6">늦은발송 1건</v-col>
                                <v-col class="grey--text text-caption" cols="6">주문취소 0건</v-col>
                            </v-row>
                        
                        </v-sheet>
                        <div class="my-6 mx-4">
                        <v-row class="mt-4 white--text"><v-icon class="white--text text-subtitle-1">mdi-chart-bell-curve-cumulative</v-icon><span class="ml-2 text-body-2">수익관리</span></v-row>
                        <v-row class="mt-6 white--text"><v-icon class="white--text text-subtitle-1">mdi-text-box-outline</v-icon><span class="ml-2 text-body-2">광고관리</span></v-row>
                        <v-row class="mt-6 white--text"><v-icon class="white--text text-subtitle-1">mdi-advertisements</v-icon><span class="ml-2 text-body-2">광고 신청</span></v-row>
                        </div>
                    </v-container>
                </v-card>
            </v-row>    
            
            <v-row class="mt-8">
                <v-card width="100%" :style="{backgroundImage:'linear-gradient(135deg, #ffea85, #ffdd37)'}">
                    <v-container>
                        <v-row class=" mt-1">
                            <v-col class="font-weight-bold" cols="8">구매중인 주문</v-col>
                            <v-col class="grey--text text-caption text-right" cols="4">전체보기 ></v-col>
                        </v-row>
                        
                        <v-sheet class="mt-4 d-flex justify-center align-center" height="100px" :style="{borderRadius:'4px', backgroundImage:'linear-gradient(135deg, #ffea85, #ffdd37)',border:'solid 2px rgba(141,109,8,0.3)'}">
                        
                            <div>
                                <div class="text-center mb-2"><v-icon>mdi-information-outline</v-icon></div>
                                <div><h5>어머, 구매중인 주문이 없어요</h5></div>
                            </div>
                        
                        </v-sheet>
                        <div class="my-6 mx-4">
                        <v-row class="mt-4"><v-icon class="text-subtitle-1">mdi-credit-card-outline</v-icon><span class="ml-2 text-body-2">결제/환불내역</span></v-row>
                        <v-row class="mt-6"><v-icon class="text-subtitle-1">mdi-ticket-confirmation-outline</v-icon><span class="ml-2 text-body-2">쿠폰/프로모션</span></v-row>
                        <v-row class="mt-6"><v-icon class="text-subtitle-1">mdi-cash</v-icon><span class="ml-2 text-body-2">컴포디 캐시 충전</span></v-row>
                        </div>
                    </v-container>
                </v-card>
            </v-row>
            <v-card width="100%" elevation="0" class="mt-5 pb-10">
                <div class="py-5"><h4>친구초대</h4></div>
                <div class="py-5"><h4>크몽 이용방법</h4></div>
                <div class="py-5"><h4>고객센터</h4></div>
                <div class="py-5"><h4>로그아웃</h4></div>
            </v-card>    
        </v-container>
    </div>
</template>

<script>
export default {
    layout:'mypagedefault'
}
</script>

<style>

</style>