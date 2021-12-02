<template>
    <v-card elevation="0" min-width="100%" style="width:100%, margin-bottom:20px">
        <v-container fluid>
            
            <v-form ref="form" v-model="valid" @submit.prevent="onSubmitForm">
                <h4>기본정보</h4>
                <v-textarea
                    outlined
                    auto-grow
                    clearable
                    v-model="content"
                    label="서비스를 잘 들어낼 수 있는 내용을 입력해주세요."
                    :hide-details="hideDetails"
                    :success-messages="successMessages"
                    :success="success"
                    @input="onChangeTextarea"
                />
                <h4 class="mt-5">서비스 설명</h4>
                <v-textarea
                    outlined
                    auto-grow
                    clearable
                    v-model="content1"
                    label=" 취소 및 환불규정은 판매하시는 서비스의 관련 법령에 따라 일괄 적용됩니다."
                    :hide-details="hideDetails"
                    :success-messages="successMessages"
                    :success="success"
                    @input="onChangeTextarea"
                />
                <h4 class="mt-5">요청사항</h4>
                <v-textarea
                    class="mb-5"
                    outlined
                    auto-grow
                    clearable
                    v-model="content2"
                    label="결제를 완료한 의뢰인에게만 보여지며, 작성된 답변은 거래화면에서 확인 가능합니다."
                    :hide-details="hideDetails"
                    :success-messages="successMessages"
                    :success="success"
                    @input="onChangeTextarea"
                />
                <v-btn type="submit" absolute right>올리기</v-btn>
                <input ref="imageInput" type="file" multiple hidden @change="onChangeImages">
                <v-btn @click="onClickImageUpload" type="button">사진올리기</v-btn>
                <div>
                    <div v-for="(p, i) in imagePaths" :key="p" style="display: inline-block">
                        <img :src="`http://localhost:3085/${p}`" :alt="p" style="width: 200px">
                        <div>
                            <button @click="onRemoveImage(i)" type="button">제거</button>
                        </div>
                    </div>
                </div>
            </v-form>
        </v-container>
    </v-card>
  
</template>

<script>
import { mapState } from 'vuex';
export default {
    data(){
        return {
            valid:false,
            hideDetails:true, //에러표시해두는곳 
            successMessages:'',
            success: false,
            content:'',
        }
    },
    computed:{
        ...mapState('users', ['me']),
        ...mapState('posts',['imagePaths'])
    },
    methods:{
        onChangeTextarea(value){
            if(value.length){

                this.hideDetails = true;
                this.success = false;
                this.successMessages = '';
            }
        },
        onSubmitForm(){
            if(this.$refs.form.validate()){
                this.$store.dispatch('posts/add',{
                    content: this.content,
                    
                })
                    .then(()=>{
                        this.content = '';
                        this.hideDetails = false;
                        this.success = true;
                        this.successMessages = '게시글 등록 성공!';
                    })
                    .catch(()=>{

                    });
            }
        },
        onClickImageUpload(){
            this.$refs.imageInput.click();
        },
        onChangeImages(e){
            console.log(e.target.files);
            const imageFormData = new FormData();
            [].forEach.call(e.target.files, (f)=>{
                imageFormData.append('image', f);
            });
            this.$store.dispatch('posts/uploadImages', imageFormData);

        },
        onRemoveImage(index){
            this.$store.commit('posts/removeImagePath', index);
        }
    }
}
</script>

<style>

</style>