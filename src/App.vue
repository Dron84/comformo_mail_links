<template>
    <div class="preload" v-if="preload">
        <div class="dash uno"></div>
        <div class="dash dos"></div>
        <div class="dash tres"></div>
        <div class="dash cuatro"></div>
    </div>
    <div id="app" v-else>
        <div v-if="dataOK == true">
            <div v-if="active">
                <div class="container_header">
                    <header class="header">
                        <a to="/"><img src="/static/img/logo.png" alt="logo" class="logo"></a>
                    </header>
                </div>
                <div class="container">
                    <nav class="top_menu">
                        | <a href="https://comformo.com/contact/" target="_blank">Contact us to Any Question</a> |
                    </nav>
                    <section class="main_wrapper">
                        <dilligance :company-id="companyId" :people-id="peopleId" :company="company"></dilligance>
                    </section>
                    <footer class="site-footer">
                        <div class="top-footer">
                            <div class="container">
                                <div class="row">
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <a href="#" class="footer-logo">
                                            <img src="/static/img/logo.png" alt="">
                                        </a>
                                        <div class="copy">
                                            Copyright 2019 © Comformo Ltd, trading as one of the top Quality Company
                                            formations
                                        </div>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Company
                                        </h3>
                                        <ul class="footer-menu">

                                            <li><a href="https://comformo.com/blog/" target="_blank">Blog</a></li>
                                            <li><a href="https://comformo.com/contact/" target="_blank">Contact us</a>
                                            </li>

                                        </ul>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Useful Links
                                        </h3>
                                        <ul class="footer-menu">

                                            <li><a href="https://comformo.com/faq/" target="_blank">FAQ</a></li>
                                            <li><a href="https://comformo.com/partnership/" target="_blank">Partner
                                                ship</a></li>
                                        </ul>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Subscribe for our news
                                        </h3>
                                        <form action="" class="newsletter-form">
                                            <div class="input-wrapp">
                                                <input type="email" name="user-enail" class="form-control"
                                                       placeholder="Your Email Here">
                                                <button class="btn">Subscribe</button>
                                            </div>
                                        </form>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="bottom-footer">
                            <div class="container">
                                <ul>
                                    <li><a href="https://comformo.com/disclaimer/" class=''
                                           target="_blank">Disclaimer</a></li>
                                    <li><a href="https://comformo.com/refund-policy/" class='' target="_blank">Refund
                                        Policy</a></li>
                                    <li><a href="https://comformo.com/privacy-policy/" class='' target="_blank">Privacy
                                        Policy</a></li>
                                    <li><a href="https://comformo.com/terms-of-payment/" class='' target="_blank">Terms
                                        of Payment</a></li>
                                    <li><a href="https://comformo.com/terms-and-conditions/" class='' target="_blank">Terms
                                        and Conditions</a></li>
                                </ul>
                                <div class="footer-visa">
                                    <img width="100" height="30"
                                         src="https://comformo.com/wp-content/uploads/2019/05/visa_PNG39.png"
                                         class="size-100x30" alt="" style="max-width: 100%; height: auto;">
                                </div>
                            </div>
                        </div>
                    </footer>
                </div>
            </div>
            <div v-else>
                <div class="container_header">
                    <header class="header">
                        <a to="/"><img src="/static/img/logo.png" alt="logo" class="logo"></a>
                    </header>
                </div>
                <div class="container">
                    <nav class="top_menu">
                        | <a href="https://comformo.com/contact/" target="_blank">Contact us to Any Question</a> |
                    </nav>
                    <section class="main_wrapper">
                        <newlink v-if="mess==''" :checkemail="email" @buttonClick="generateNewLink()"></newlink>
                        <p v-if="mess!=''">{{mess}}</p>
                    </section>
                    <footer class="site-footer">
                        <div class="top-footer">
                            <div class="container">
                                <div class="row">
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <a href="#" class="footer-logo">
                                            <img src="/static/img/logo.png" alt="">
                                        </a>
                                        <div class="copy">
                                            Copyright 2019 © Comformo Ltd, trading as one of the top Quality Company
                                            formations
                                        </div>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Company
                                        </h3>
                                        <ul class="footer-menu">

                                            <li><a href="https://comformo.com/blog/" target="_blank">Blog</a></li>
                                            <li><a href="https://comformo.com/contact/" target="_blank">Contact us</a>
                                            </li>

                                        </ul>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Useful Links
                                        </h3>
                                        <ul class="footer-menu">

                                            <li><a href="https://comformo.com/faq/" target="_blank">FAQ</a></li>
                                            <li><a href="https://comformo.com/partnership/" target="_blank">Partner
                                                ship</a></li>
                                        </ul>
                                    </div>
                                    <div class="col-md-6 col-lg-3 footer-widget">
                                        <h3 class="widget-title">
                                            Subscribe for our news
                                        </h3>
                                        <form action="" class="newsletter-form">
                                            <div class="input-wrapp">
                                                <input type="email" name="user-enail" class="form-control"
                                                       placeholder="Your Email Here">
                                                <button class="btn">Subscribe</button>
                                            </div>
                                        </form>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="bottom-footer">
                            <div class="container">
                                <ul>
                                    <li><a href="https://comformo.com/disclaimer/" class=''
                                           target="_blank">Disclaimer</a></li>
                                    <li><a href="https://comformo.com/refund-policy/" class='' target="_blank">Refund
                                        Policy</a></li>
                                    <li><a href="https://comformo.com/privacy-policy/" class='' target="_blank">Privacy
                                        Policy</a></li>
                                    <li><a href="https://comformo.com/terms-of-payment/" class='' target="_blank">Terms
                                        of Payment</a></li>
                                    <li><a href="https://comformo.com/terms-and-conditions/" class='' target="_blank">Terms
                                        and Conditions</a></li>
                                </ul>
                                <div class="footer-visa">
                                    <img width="100" height="30"
                                         src="https://comformo.com/wp-content/uploads/2019/05/visa_PNG39.png"
                                         class="size-100x30" alt="" style="max-width: 100%; height: auto;">
                                </div>
                            </div>
                        </div>
                    </footer>
                </div>
            </div>
        </div>
        <div v-else>
            <div class="container_header">
                <header class="header">
                    <a to="/"><img src="/static/img/logo.png" alt="logo" class="logo"></a>
                </header>
            </div>
            <div class="container">
                <section class="main_wrapper">
                    <h3 style="margin: 40px;">Sorry wrong link</h3>
                    <p style="text-align: center;"><a href="https://comformo.com">Go to Home page</a></p>
                </section>
                <footer class="site-footer">
                    <div class="top-footer">
                        <div class="container">
                            <div class="row">
                                <div class="col-md-6 col-lg-3 footer-widget">
                                    <a href="#" class="footer-logo">
                                        <img src="/static/img/logo.png" alt="">
                                    </a>
                                    <div class="copy">
                                        Copyright 2019 © Comformo Ltd, trading as one of the top Quality Company
                                        formations
                                    </div>
                                </div>
                                <div class="col-md-6 col-lg-3 footer-widget">
                                    <h3 class="widget-title">
                                        Company
                                    </h3>
                                    <ul class="footer-menu">

                                        <li><a href="https://comformo.com/blog/" target="_blank">Blog</a></li>
                                        <li><a href="https://comformo.com/contact/" target="_blank">Contact us</a></li>

                                    </ul>
                                </div>
                                <div class="col-md-6 col-lg-3 footer-widget">
                                    <h3 class="widget-title">
                                        Useful Links
                                    </h3>
                                    <ul class="footer-menu">

                                        <li><a href="https://comformo.com/faq/" target="_blank">FAQ</a></li>
                                        <li><a href="https://comformo.com/partnership/" target="_blank">Partner ship</a>
                                        </li>
                                    </ul>
                                </div>
                                <div class="col-md-6 col-lg-3 footer-widget">
                                    <h3 class="widget-title">
                                        Subscribe for our news
                                    </h3>
                                    <form action="" class="newsletter-form">
                                        <div class="input-wrapp">
                                            <input type="email" name="user-enail" class="form-control"
                                                   placeholder="Your Email Here">
                                            <button class="btn">Subscribe</button>
                                        </div>
                                    </form>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="bottom-footer">
                        <div class="container">
                            <ul>
                                <li><a href="https://comformo.com/disclaimer/" class='' target="_blank">Disclaimer</a>
                                </li>
                                <li><a href="https://comformo.com/refund-policy/" class='' target="_blank">Refund
                                    Policy</a></li>
                                <li><a href="https://comformo.com/privacy-policy/" class='' target="_blank">Privacy
                                    Policy</a></li>
                                <li><a href="https://comformo.com/terms-of-payment/" class='' target="_blank">Terms of
                                    Payment</a></li>
                                <li><a href="https://comformo.com/terms-and-conditions/" class='' target="_blank">Terms
                                    and Conditions</a></li>
                            </ul>
                            <div class="footer-visa">
                                <img width="100" height="30"
                                     src="https://comformo.com/wp-content/uploads/2019/05/visa_PNG39.png"
                                     class="size-100x30" alt="" style="max-width: 100%; height: auto;">
                            </div>
                        </div>
                    </div>
                </footer>
            </div>
        </div>

    </div>
</template>

<script>
    import dilligance from './components/dilligance'
    import newlink from './components/newlink'
    import axios from 'axios'

    export default {
        name: 'App',
        components: {dilligance, axios, newlink},
        data() {
            return {
                preload: true,
                companyId: '',
                peopleId: '',
                email: '',
                postUrl: 'https://cabinet.comformo.com/server/post/',
                dataOK: false,
                active: true,
                mess: '',
                company: {},
            }
        },
        methods: {
            loadComponent() {
                let search = location.search.replace('?link=', '')
                axios.post(this.postUrl, 'maillink=' + search)
                    .then(res => {
                        if (res.data.error != undefined) {
                            this.dataOK = false
                            this.preload = false
                        } else {
                            let link = res.data.link[0]
                            let company = res.data.company[0]
                            if (link.active == '1') {
                                this.companyId = link.companyId
                                this.email = link.email
                                this.peopleId = link.personId
                                this.active = true
                                this.company = company
                                this.dataOK = true
                                this.preload = false
                            } else {
                                this.companyId = link.companyId
                                this.email = link.email
                                this.peopleId = link.personId
                                this.active = false
                                this.dataOK = true
                                this.preload = false
                            }
                        }
                    })
            },
            generateNewLink() {
                let fd = new FormData()
                fd.append('companyId', this.companyId)
                fd.append('email', this.email)
                fd.append('personId', this.peopleId)
                fd.append('maillinkGenerate', 'Generate')
                axios.post(this.postUrl, fd)
                    .then(res => {
                        if (res.data.mess == 'Sql INSERT is ok') {
                            this.mess = 'Check your email! And go to new link in email!'
                        }
                    })
            }
        },
        mounted() {
            this.loadComponent()
        },
    }
</script>