<template>
    <div class="col-sm-6 col-md-4 col-lg-3 comp-card-wrapp">
        <div class="comp-card settings-card box_shadow_hover_roundshadow">
            <div>
                <div class="comp-card-heading">
                    <h3>ADD DOCUMENTS</h3>
                    <h4>Add scan <br>documents</h4>
                </div>
                <div class="centrize" style="padding: 0 15px 20px 0;">
                    <div style="display: grid; width: 100%;justify-content: center;align-items: center;">
                        <addImage v-if="imgReload==false" :btnCaption="'Add Passport'" @files="passportAdd($event)"></addImage>
                        <addImage v-if="imgReload==false" :btnCaption="'Add Address'" @files="addressAdd($event)"></addImage>
                        <addImage v-if="imgReload==false" :btnCaption="'Add Other'" @files="otherAdd($event)"></addImage>
                        <button v-if="!uploadWait" class="submit" style="margin: 20px auto; width: 250px; " @click.prevent="addAllDocs">Upload Documents</button>
                        <button v-else class="button" style="width: 250px; margin: 20px auto;" disabled="disabled">WAIT <img src="/static/img/loading.gif" alt="load" style="height: 15px;position: relative;top: -2px;left:5px;"></button>
                        <p v-if="documentMess!=''" class="text_accent centrize">{{documentMess}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import vselect from 'vue-select'
    import addImage from '@/components/addImage'

    export default {
        name: "files",
        data(){
            return{
                reg: /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/,
                inputOk: 'valid',
                inputErr: 'err',
                labelCaptionUp: 'label-up',
                resStatus: '',
                filesStatus: 0,
                filesForm: false,
                ducumentsUpload: false,
                documentMess: '',
                passportFiles: [],
                addressFiles: [],
                otherFiles: [],
                preload: false,
                postUrl: 'https://cabinet.comformo.com/server/post/',
                uploadWait: false,
                imgReload: false,
            }
        },
        props:{
            companyId: '',
        },
        methods:{
            passportAdd(data){
                this.passportFiles=data
            },
            addressAdd(data){
                this.addressFiles=data
            },
            otherAdd(data){
                this.otherFiles=data
            },
            addAllDocs(){
                this.uploadWait = true
                let fd = new FormData
                if(this.passportFiles){
                    let files = this.passportFiles; //это массив файлов
                    for(let i=0;i<files.length;i++){
                        fd.append("passportFile_"+i,files[i]);
                    }
                }
                if(this.addressFiles) {
                    let files = this.addressFiles; //это массив файлов
                    for (let i = 0; i < files.length; i++) {
                        fd.append("addressFile_" + i, files[i]);
                    }
                }
                if(this.otherFiles) {
                    let files = this.otherFiles; //это массив файлов
                    for (let i = 0; i < files.length; i++) {
                        fd.append("otherFile_" + i, files[i]);
                    }
                }
                fd.append('saveCompanyDocs','save')
                fd.append('companyId', this.companyId)
                axios.post(this.postUrl, fd)
                    .then(res=>{
                        this.$emit('documentsUpload',res.data)
                        this.uploadWait = false
                        this.documentMess = 'Ok documents loaded!'
                        this.passportFiles = [],
                        this.addressFiles = []
                        this.otherFiles = []
                        this.imgReload = true
                        setTimeout(()=>{
                            this.imgReload = false
                        },500)
                    })

            },
        },
        components: {
            vselect,
            addImage,
        },
    }

</script>

<style scoped lang="sass">
    .add-comp-btn
        margin-top: 55px
        .companys_company
            height: 293px
        .modal-container
            max-width: 1200px
            width: 90% !important
            max-height: 90vh !important
        .modal-container-scroll
            overflow: scroll
            height: 80vh
        .modal-mask
            width: 100%
            height: 100%
        .modal-wrapper
            width: 100%
            height: 100%
        p.small
            text-align: left
        h4
            font-size: .91em
            text-align: center
            margin: 10px
        h5
            margin: 8px
            font-size: 1.25em
        .companys_header_top
            font-size: 1em
</style>