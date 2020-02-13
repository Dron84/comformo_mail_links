<template>
    <div class="container">
            <h4 class="modal-title text-center">DEClARATION INFORMATION FORM</h4>
            <form action="" class="ubo-form">
                <p style="text-align: left;">Declaration by the ultimate beneficial owner (UBO) of Company “{{company.companyName}}” </p>
                <p style="text-align: left;">I, the undersigned, being the UBO of "{{company.companyName}}", request that COMFORMO LTD
                    acts as our service provider and declare and affirm that:</p>
                <ul>
                    <li>
                        <div class="ubo-checkboxes clearfix">
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="decliam" checked value="true"
                                       id="d-rad-1">
                                <label for="d-rad-1"><span></span>I am</label>
                            </div>
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="decliam" value="false" id="d-rad-2">
                                <label for="d-rad-2"><span></span>I am not</label>
                            </div>
                            <span  style="text-align: left;">aware that the provision of corporate services is regulated by the Proceeds of Crime Act 2002 (POCA) (as amended by the Serious Organised Crime and Police Act 2005 (SOCPA)), the Money Laundering, Terrorist Financing and Transfer of Funds (Information on the Payer) Regulations 2017 (MLR 2017) and the Terrorism Act 2000 (TA 2000) (as amended by the Anti-Terrorism, Crime and Security Act 2001 (ATCSA 2001) and the Terrorism Act 2006 (TA 2006)), and as such, directors and staff in Firms providing corporate services, having any knowledge or suspicion that another person is involved in a money laundering or terrorist financing offence and who has become aware of the information on which the knowledge or reasonable suspicion is based in the course of his occupation, profession or business, are required to disclose such information to the Financial Conduct Authority. In such circumstances they are not obliged to discuss such reports with clients because of the restrictions imposed by the tipping off provisions of the anti-money laundering legislation.</span>
                        </div>
                    </li>
                    <li>
                        <div class="ubo-checkboxes clearfix">
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="declihave" checked value="true"
                                       id="d-rad-3">
                                <label for="d-rad-3"><span></span>I have</label>
                            </div>
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="declihave" value="false"
                                       id="d-rad-4">
                                <label for="d-rad-4"><span></span>have not been</label>
                            </div>
                            <span style="text-align: left;">been involved in any illegal activity in any part of the world and have not been declared bankrupt or have been a director or otherwise concerned in the management of any company which has been subject to an insolvent liquidation and/or I am unaware of any activities I have engaged in, that involve money-laundering.</span>
                        </div>
                    </li>
                    <li><p style="text-align: left;">Any contributions that will be made into the Company as share capital or otherwise as shareholder’s funds or from external financing will not derive from unlawful or immoral sources either in their country of origin or in my country of ordinary residence or in United Kingdom.</p></li>
                    <li><p style="text-align: left;">If applicable - The settlor or named beneficiary(ies) of a trust holding a beneficial interest have not been involved in any illegal activity and have not been declared bankrupt anywhere in the world. </p></li>
                    <li>
                        <div class="ubo-checkboxes clearfix">
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="entrusted" checked value="true"
                                       id="d-rad-5">
                                <label for="d-rad-5"><span></span>I have</label>
                            </div>
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="entrusted" value="false"
                                       id="d-rad-6">
                                <label for="d-rad-6"><span></span>I have not been</label>
                            </div>
                            <span style="text-align: left;">(delete as appropriate) entrusted with a public prominent function.</span>
                        </div>
                    </li>
                    <li>
                        <div class="ubo-checkboxes clearfix">
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="declrelated" checked value="true"
                                       id="d-rad-7">
                                <label for="d-rad-7"><span></span>I am related to a person</label>
                            </div>
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="declrelated" value="false"
                                       id="d-rad-8">
                                <label for="d-rad-8"><span></span>I am not related to any person</label>
                            </div>
                            <span style="text-align: left;">(delete as appropriate) who holds a public function.</span>
                        </div>
                    </li>
                    <li>
                        <div class="ubo-checkboxes clearfix">
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="pepList" checked value="true"
                                       id="d-rad-9">
                                <label for="d-rad-9"><span></span>I have been included in a list</label>
                            </div>
                            <div class="ubo-checkbox">
                                <input type="radio" class="c_checkbox" v-model="pepList" value="false"
                                       id="d-rad-10">
                                <label for="d-rad-10"><span></span>I have never been included in any list</label>
                            </div>
                            <span>(delete as appropriate) of Politically Exposed Persons (PEPs). </span>
                        </div>
                    </li>
                </ul>

                <p style="text-align: left;">(Furthermore, I hereby confirm that the information provided above is true, correct and complete and agree to immediately notify Comformo in writing in case of a change with respect to the above and representations made herein.</p>
                <p style="text-align: left;">Additionally, I hereby agree for Comformo to disclose my identity as UBO of the Company to any commercial bank for the purpose of opening a bank account in the name of the Company.</p>

                <div class="input_group">
                    <input type="text" id="fullName" v-model="fullName">
                    <label for="fullName" class="label-up">Full Name</label>
                </div>
                <div class="input_group">
                    <input type="text" id="address" v-model="address">
                    <label for="address" class="label-up">Address</label>
                </div>
                <div class="input_group">
                    <input type="text" id="passport" v-model="passport">
                    <label for="passport" class="label-up">Passport No. / ID No</label>
                </div>
                <div class="signature-block clearfix">
                    <div class="signature">
                        <signature @signed="canvasSave" class="signature-pad" ref="canvas"></signature>
                    </div>
                    <div class="signature-buttons">
                        <button class="submit-transparent" style="width: 250px; margin-bottom: 20px" @click.prevent="clear()">CLEAR</button>
                        <button v-if="!saveStatus" class="submit-yellow" style="width: 250px" @click.prevent="save()">Success signature</button>
                        <button v-else class="submit-yellow" :class="{'submit valid-button': saveStatus}" style="width: 250px;" >Signature saved</button>
                    </div>
                </div>
                <files @documentsUpload="documentsUpload($event)" :company-id="companyId"></files>
                <div class="centrize">
                    <div v-if="!dilliganceForm">
                        <button v-if="!wait" class="submit popup-submit" :disabled="checkSign" @click.prevent="saveDillegance">save</button>
                        <button v-else class="submit popup-submit"  style="width: 300px; margin: 0 auto;" disabled="disabled">WAIT <img src="/static/img/loading.gif" alt="load" style="height: 15px;position: relative;top: -2px;left:5px;"></button>
                    </div>
                    <div v-else>
                        <p v-if="dilliganceForm">You are all is Complete. You can close the window</p>
                    </div>

                </div>

            </form>

        </div>
</template>

<script>
    import axios from 'axios'
    import signature from './signature'
    import files from './files'

    export default {
        name: "dilligance",
        data(){
            return{
                reg: /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/,
                inputOk: 'valid',
                inputErr: 'err',
                labelCaptionUp: 'label-up',
                option:{
                    penColor:"rgb(0, 0, 0)",
                    backgroundColor:"rgb(255,255,255)"
                },
                saveStatus: false,
                decliam: false,
                declihave: false,
                declrelated: false,
                pepList: false,
                usa_citizen: false,
                usa_rezident: false,
                usa_resident_card: false,
                usa_mail_address: false,
                usa_care: false,
                usa_phone: false,
                usa_standing_order: false,
                usa_sign_auth: false,
                signature: null,
                dilliganceForm: false,
                documentUpload: false,
                postUrl: 'https://cabinet.comformo.com/server/post/',
                wait: false,
                entrusted: false,
                companyName: '',
                fullName: '',
                address: '',
                passport: '',
            }
        },
        props: {
            companyId: '',
            peopleId: '',
            company: {},
        },
        computed:{
            checkSign(){
                if(this.fullName!=''&&this.address!=''&&this.passport!=''&&this.signature!=null&&this.documentUpload==true){
                    return false
                }else{
                    return true
                }
            }
        },
        methods:{
            clear(){
                this.$refs.canvas.clearSignature();
                this.saveStatus = false
            },
            save(){
                this.$refs.canvas.saveSignature();
                this.saveStatus = true
            },
            canvasSave(signature){
                this.signature = signature
            },
            resizeCanvas: function() {
                let ratio =  Math.max(window.devicePixelRatio || 1, 1);
                this.$refs.canvas.width = this.$refs.canvas.offsetWidth * ratio
                this.$refs.canvas.height = this.$refs.canvas.offsetHeight * ratio
                this.$refs.canvas.getContext('2d').scale(ratio, ratio)
            },
            documentsUpload(data){
                if(data.files.mess=='Sql INSERT is ok'){
                    this.documentUpload = true
                }
            },
            saveDillegance(){
                this.wait =true
                let fd = new FormData
                fd.append('decliam', this.decliam)
                fd.append('declihave', this.declihave)
                fd.append('declrelated', this.declrelated)
                fd.append('pepList', this.pepList)
                fd.append('entrusted', this.entrusted)
                fd.append('fullName',this.fullName)
                fd.append('address',this.address)
                fd.append('passport',this.passport)
                fd.append('USACitizen', this.usa_citizen)
                fd.append('USAResident', this.usa_rezident)
                fd.append('USAValidGreenCard', this.usa_resident_card)
                fd.append('USAMailAddressBoxNum', this.usa_mail_address)
                fd.append('USAinCareAddress', this.usa_care)
                fd.append('USAphoneNumber', this.usa_phone)
                fd.append('USAtransferFunds', this.usa_standing_order)
                fd.append('USAvalidAttorney', this.usa_sign_auth)
                fd.append('DeclanationSign', this.signature)
                fd.append('peopleUpdate', this.peopleId)
                fd.append('person', 'update')
                axios.post(this.postUrl, fd)
                    .then((res)=>{
                        if(res.data.mess=='Sql UPDATE is ok'){
                            this.dilliganceForm = true
                            this.wait = false
                        }
                    })
            },
            CloseWindow(){
                window.close()
            }
        },
        components:{
            signature,files
        },
    }
</script>

<style scoped>

</style>