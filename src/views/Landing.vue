<template>
    <div>
    
  <section class="section section-lg section-shaped overflow-hidden my-0">
        <div class="shape shape-style-1 shape-default shape-skew">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
        <div class="container py-0 pb-lg">
            <div class="row justify-content-between align-items-center">
                <div class="col-lg-6 mb-5 mb-lg-0">
                    <h1 class="text-white font-weight-light">Obituaries.co.za</h1>
                 
                  
                </div>
                <div class="col-lg-12 mb-lg-auto">
                    <div class="rounded shadow-lg overflow-hidden transform-perspective-right">
                        <b-carousel id="carousel1"
                                    controls
                                    indicators>
                            <!-- Text slides with image -->
                          
                            <b-carousel-slide v-bind:img-src="Premiumpicture" >
                                 <h1 style="background-color:black">{{premiunAllSearch.firstname}}</h1>

                                                        </b-carousel-slide>

                            <b-carousel-slide v-bind:img-src="Premiumpicture2">

                            <h1 style="background-color:black"></h1>
                            </b-carousel-slide>
                            <b-carousel-slide v-bind:img-src="Premiumpicture3">
                                                        <h1 style="background-color:black"></h1>

                            </b-carousel-slide>
                                                        
                        </b-carousel>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <template>
    <!-- Modals -->
    <div class="row">
        <div class="col-md-4">
            <base-button block type="primary" class=" mb-3" @click="modals.modal1 = true">
                Default
            </base-button>
            <modal :show.sync="modals.modal1">
                <h6 slot="header" class="modal-title" id="modal-title-default">Type your modal title</h6>

                <p>Far far away, behind the word mountains, far from the countries Vokalia and
                    Consonantia, there live the blind texts. Separated they live in Bookmarksgrove
                    right at the coast of the Semantics, a large language ocean.</p>
                <p>A small river named Duden flows by their place and supplies it with the necessary
                    regelialia. It is a paradisematic country, in which roasted parts of sentences
                    fly into your mouth.</p>

                <template slot="footer">
                    <base-button type="primary">Save changes</base-button>
                    <base-button type="link" class="ml-auto" @click="modals.modal1 = false">Close
                    </base-button>
                </template>
            </modal>
        </div>
        <div class="col-md-4">
            <base-button block type="warning" class=" mb-3" @click="modals.modal2 = true">
                Sign up
            </base-button>

            <modal :show.sync="modals.modal2"
                   gradient="danger"
                   modal-classes="modal-danger modal-dialog-centered">
                <h6 slot="header" class="modal-title" id="modal-title-notification">Your attention is required</h6>

                <div class="py-3 text-center">
                    <i class="ni ni-bell-55 ni-3x"></i>
                    <h4 class="heading mt-4">You should read this!</h4>
                    <p>A small river named Duden flows by their place and supplies it with the
                        necessary regelialia.</p>
                </div>
                <template>
                        <div class="text-muted text-center mb-3">
                            <small>Sign in with</small>
                        </div>
                        <div class="btn-wrapper text-center">
                            <base-button type="neutral">
                                <img slot="icon" src="img/icons/common/github.svg">
                                Github
                            </base-button>

                            <base-button type="neutral">
                                <img slot="icon" src="img/icons/common/google.svg">
                                Google
                            </base-button>
                        </div>
                    </template>
                    <template>
                        <div class="text-center text-muted mb-4">
                            <small>Or sign in with credentials lindo2</small>
                        </div>
                        <form>
                        <base-input placeholder="name" v-model="email"></base-input>
                        
                            </base-input>
                            <base-input alternative
                                        type="password"
                                        placeholder="Password"
                                        addon-left-icon="ni ni-lock-circle-open" v-model="password">
                            </base-input>
                            <base-checkbox>
                                Remember me
                            </base-checkbox>
                            <div class="text-center">
                                <base-button type="primary" class="my-4" v-on:click="Register">Sign up2</base-button>
                            </div>
                        </form>
                    </template>

                <template slot="footer">
                    <base-button type="white">Ok, Got it</base-button>
                    <base-button type="link"
                                 text-color="white"
                                 class="ml-auto"
                                 @click="modals.modal2 = false">
                        Close
                    </base-button>
                </template>
            </modal>
        </div>
        <div class="col-md-4">
            <base-button block type="default" class=" mb-3" @click="modals.modal3 = true">
                Login
            </base-button>

            <modal :show.sync="modals.modal3"
                   body-classes="p-0"
                   modal-classes="modal-dialog-centered modal-sm">
                <card type="secondary" shadow
                      header-classes="bg-white pb-5"
                      body-classes="px-lg-5 py-lg-5"
                      class="border-0">
                    <template>
                        <div class="text-muted text-center mb-3">
                            <small>Sign in with</small>
                        </div>
                        <div class="btn-wrapper text-center">
                            <base-button type="neutral">
                                <img slot="icon" src="img/icons/common/github.svg">
                                Github
                            </base-button>

                            <base-button type="neutral">
                                <img slot="icon" src="img/icons/common/google.svg">
                                Google
                            </base-button>
                        </div>
                    </template>
                    <template>
                        <div class="text-center text-muted mb-4">
                            <small>Or sign in with credentials lindo</small>
                        </div>
                        <form role="form">
                            <base-input alternative
                                        class="mb-3"
                                        placeholder="email"
                                        addon-left-icon="ni ni-email-83">
                            </base-input>
                            <base-input alternative
                                        type="password"
                                        placeholder="Password"
                                        addon-left-icon="ni ni-lock-circle-open">
                            </base-input>
                            <base-checkbox>
                                Remember me
                            </base-checkbox>
                            <div class="text-center">
                                <base-button type="primary" class="my-4" v-on:click="signIn">Sign In</base-button>
                            </div>
                        </form>
                    </template>
                </card>
            </modal>
        </div>
    </div>
</template>

 
        <div class="position-relative">
            <!-- shape Hero -->
            <section class="section-shaped my-0">
                <div class="shape shape-style-1 shape-default shape-skew">
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
                <div class="container shape-container d-flex">
                    <div class="col px-0">
                        <div class="row">
                            <div class="col-lg-6">
                           
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            <!-- 1st Hero Variation -->
        </div>
        <section class="section section-lg pt-lg-0 mt--200">
            <div class="container">
                <div class="row justify-content-center">
                    <div class="col-lg-12">
                        <div class="row row-grid">
                            <div class="col-lg-4">
                            
                                <card class="border-0" hover shadow body-classes="py-5">
                                 <img v-bind:src="allSearch2.picture"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">

                                    <h6 class="text-primary text-uppercase">{{firstname2}}&nbsp;{{Middlename2}}&nbsp;{{Nickname2}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap 4
                                        that includes the most important components and features.</p>
                                    <div>
                                        <badge type="primary" rounded>design</badge>
                                        <badge type="primary" rounded>system</badge>
                                        <badge type="primary" rounded>creative</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="primary" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                   <img v-bind:src="allSearch3.picture"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">


                                    <h6 class="text-primary text-uppercase">{{firstname3}}&nbsp;{{Middlename3}}&nbsp;{{Nickname3}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="success" rounded>business</badge>
                                        <badge type="success" rounded>vision</badge>
                                        <badge type="success" rounded>success</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="success" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                   <img v-bind:src="picture4"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">

                                    <h6 class="text-warning text-uppercase">Prepare Launch</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="warning" rounded>marketing</badge>
                                        <badge type="warning" rounded>product</badge>
                                        <badge type="warning" rounded>launch</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="warning" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                        </div>
                        <div class="row row-grid">
                            <div class="col-lg-4">
                            
                                <card class="border-0" hover shadow body-classes="py-5">
                                 <img v-bind:src="picture5"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">

                                    <h6 class="text-primary text-uppercase">{{firstname2}}&nbsp;{{Middlename2}}&nbsp;{{Nickname2}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap 4
                                        that includes the most important components and features.</p>
                                    <div>
                                        <badge type="primary" rounded>design</badge>
                                        <badge type="primary" rounded>system</badge>
                                        <badge type="primary" rounded>creative</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="primary" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                   <img v-bind:src="picture6"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">


                                    <h6 class="text-primary text-uppercase">{{firstname6}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="success" rounded>business</badge>
                                        <badge type="success" rounded>vision</badge>
                                        <badge type="success" rounded>success</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="success" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                                                        <img v-bind:src="picture7"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">

                                    <h6 class="text-warning text-uppercase">Prepare Launch</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="warning" rounded>marketing</badge>
                                        <badge type="warning" rounded>product</badge>
                                        <badge type="warning" rounded>launch</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="warning" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                        </div>
                        <div class="row row-grid">
                            <div class="col-lg-4">
                            
                                <card class="border-0" hover shadow body-classes="py-5">
                                 <img v-bind:src="picture8"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">

                                    <h6 class="text-primary text-uppercase">{{firstname2}}&nbsp;{{Middlename2}}&nbsp;{{Nickname2}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap 4
                                        that includes the most important components and features.</p>
                                    <div>
                                        <badge type="primary" rounded>design</badge>
                                        <badge type="primary" rounded>system</badge>
                                        <badge type="primary" rounded>creative</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="primary" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                   <img v-bind:src="picture9"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 width="80%" height="80%"">


                                    <h6 class="text-primary text-uppercase">{{firstname3}}&nbsp;{{Middlename3}}&nbsp;{{Nickname3}}</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="success" rounded>business</badge>
                                        <badge type="success" rounded>vision</badge>
                                        <badge type="success" rounded>success</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="success" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                            <div class="col-lg-4">
                                <card class="border-0" hover shadow body-classes="py-5">
                                <img v-bind:src="picture10"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 width="80%" height="80%"">
                                    <h6 class="text-warning text-uppercase">Prepare Launch</h6>
                                    <p class="description mt-3">Argon is a great free UI package based on Bootstrap
                                        4 that includes the most important components and features.</p>
                                    <div>
                                        <badge type="warning" rounded>marketing</badge>
                                        <badge type="warning" rounded>product</badge>
                                        <badge type="warning" rounded>launch</badge>
                                    </div>
                                    <base-button tag="a" href="#" type="warning" class="mt-4">
                                        Learn more
                                    </base-button>
                                </card>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
      
        <section class="section bg-secondary">
            <div class="container">
                <div class="row row-grid align-items-center">
                    <div class="col-md-6">
                        <div class="card bg-default shadow border-0">
                            <img v-lazy="'img/theme/unnamed (3).png'" class="card-img-top">
                            <blockquote class="card-blockquote">
                                <svg preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 583 95"
                                     class="svg-bg">
                                    <polygon points="0,52 583,95 0,95" class="fill-default"></polygon>
                                    <polygon points="0,42 583,95 683,0 0,95" opacity=".2" class="fill-default"></polygon>
                                </svg>
                                <h4 class="display-3 font-weight-bold text-white">Dorah Sitole</h4>
                                <h5 class="display-3 font-weight-bold text-white">1953 - 2021</h5>
                                <p class="lead text-italic text-white">Sithole, who previously served as food editor for TRUE LOVE magazine, passed on just weeks after releasing her latest cookbook 40 Years of Iconic Food, which embraces African cuisine.</p>
                            </blockquote>
                        </div>
                    </div>
                   <div class="col-md-6">
                        <div class="card bg-default shadow border-0">
                            <img v-lazy="'img/theme/unnamed (3).png'" class="card-img-top">
                            <blockquote class="card-blockquote">
                                <svg preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 583 95"
                                     class="svg-bg">
                                    <polygon points="0,52 583,95 0,95" class="fill-default"></polygon>
                                    <polygon points="0,42 583,95 683,0 0,95" opacity=".2" class="fill-default"></polygon>
                                </svg>
                                <h4 class="display-3 font-weight-bold text-white">Dorah Sitole</h4>
                                <h5 class="display-3 font-weight-bold text-white">1953 - 2021</h5>
                                <p class="lead text-italic text-white">Sithole, who previously served as food editor for TRUE LOVE magazine, passed on just weeks after releasing her latest cookbook 40 Years of Iconic Food, which embraces African cuisine.</p>
                            </blockquote>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="section section section-shaped my-0 overflow-hidden">
            <div class="shape shape-style-1 bg-gradient-warning shape-skew">
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
                <span></span>
            </div>
            <div class="container py-0">
                <div class="row row-grid align-items-center">
                    <div class="col-md-6 order-lg-2 ml-lg-auto">
                        <div class="position-relative pl-md-5">
                            <img src="img/ill/flower2.png" class="img-center img-fluid">
                        </div>
                    </div>
                    <div class="col-lg-6 order-lg-1">
                        <div class="d-flex px-3">
                            <div>
                                <icon name="ni ni-building" size="lg" class="bg-gradient-white" color="primary" shadow
                                      rounded></icon>
                            </div>
                            <div class="pl-4">
                                <h4 class="display-3 text-white">Modern Interface</h4>
                                <p class="text-white">The Arctic Ocean freezes every winter and much of the sea-ice then
                                    thaws every summer, and that process will continue whatever happens.</p>
                            </div>
                            
                        </div>
                        
                        <card shadow class="shadow-lg--hover mt-5">
                            <div class="d-flex px-3">
                                <div>
                                    <icon name="ni ni-ambulance" gradient="warning" color="white" shadow
                                          rounded></icon>
                                </div>
                                <div class="pl-4">
                                    <div class="container mb-5">
            <!-- Inputs -->
            <h3 class="h4 text-success font-weight-bold mb-4">Search</h3>
            <div class="mb-3">
                <small class="text-uppercase font-weight-bold">Form controls</small>
            </div>
            <form>
            <div class="row">
                <div class="col-lg-10 col-sm-6">
                    <base-input placeholder="name" v-model="searchString">

                    </base-input>
                    <base-input placeholder="Search" v-model="search.Nickname"
                                addon-left-icon="ni ni-zoom-split-in">
                    </base-input>
                </div>
                <div class="col-lg-10 col-sm-6">
                    <base-input placeholder="Regular" v-model="search.Middlename">
                    </base-input>
                    <base-input placeholder="Birthday"
                                addon-right-icon="ni ni-zoom-split-in">
                    </base-input>
                </div>
                <button v-on:click="submitName">
                                    Search
                                </button>
                                
              
            </div>
            </form>
                
        </div>
        
                                </div>
                            </div>
                        </card>
                    </div>
                </div>
            </div>
             
        </section>
        <section class="section section-lg">
            <div class="container">
                <div class="row justify-content-center text-center mb-lg">
                    <div class="col-lg-8">
                        <h2 class="display-3">You search results below</h2>
                       
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-6 col-lg-3 mb-5 mb-lg-0">
                        <div class="px-4">
                            <img v-bind:src="allSearch.picture"
                                 class="rounded-circle img-center img-fluid shadow shadow-lg--hover"
                                 style="width: 200px;">
                            <div class="pt-4 text-center">
                                <h5 class="title">
                                    <span class="d-block mb-1">{{firstname}}&nbsp;{{Middlename}}&nbsp;{{Nickname}}</span>
                                    <small class="h6 text-muted">{{Lastname}}
                                     {{Address}}
                                     {{DateOfBirth}}
                                     {{DateOfDeath}}
                                     {{PlaceOfDeath}}
                                     {{MaritalStatus}}
                                     {{Occupation}}
                                     </small>
                                </h5>
                               
                            </div>
                            
                        </div>
                    </div>
                    
                </div>
            </div>
        </section>
        <section class="section section-lg pt-0">
            <div class="container">
                <card gradient="warning"
                      no-body
                      shadow-size="lg"
                      class="border-0">
                    <div class="p-5">
                        <div class="row align-items-center">
                            <div class="col-lg-8">
                                <h3 class="text-white">We made website building easier for you.</h3>
                                <p class="lead text-white mt-3">I will be the leader of a company that ends up being
                                    worth billions of dollars, because I got the answers. I understand culture.</p>
                            </div>
                            <div class="col-lg-3 ml-lg-auto">
                                <base-button tag="a" href="https://www.creative-tim.com/product/vue-argon-design-system"
                                             type="white" block size="lg">
                                    Download Vue
                                </base-button>
                            </div>
                        </div>
                    </div>
                </card>
            </div>
        </section>
      
        
       
    </div>
</template>

<script>
import Modal from "@/components/Modal.vue";


import { BCarousel } from "bootstrap-vue/esm/components/carousel/carousel";
import { BCarouselSlide } from "bootstrap-vue/esm/components/carousel/carousel-slide";
import 'firebase/firestore';
import 'firebase/firestore';
import * as firebase from "firebase/app";
import { getFirestore, getDocs, collection,query,where,orderBy,limit} from 'firebase/firestore/lite';

import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";




const config = {
  apiKey: "AIzaSyDI1jsBfenO_I0mTTNne23KEQoKTyL1CSs",
  authDomain: "arctic-acolyte-182915.firebaseapp.com",
  databaseURL: "https://arctic-acolyte-182915-default-rtdb.firebaseio.com",
  projectId: "arctic-acolyte-182915",
  storageBucket: "arctic-acolyte-182915.appspot.com",
  messagingSenderId: "1037225641803",
  appId: "1:1037225641803:web:9dc87ff62483a4aeadcace",
  measurementId: "G-3D56KWT3L5"}

const firebaseApp = firebase.initializeApp(config);
const db = getFirestore(firebaseApp);


export default {
  components: {
      BCarousel,
    BCarouselSlide,
    Modal,
  },
    data() {
       // firstname:"lindo";
        
    return {
        email:"",
        password :"",
        searchString:"",
      allSearch:[],
      allSearch2:[],
      allSearch3:[],
      premiunAllSearch:[],
      premiunAllSearch2:[],
       premiunAllSearch3:[],
            allSearch4:[],
            allSearch5:[],
            allSearch6:[],
            allSearch7:[],
            allSearch8:[],
             allSearch9:[],
             allSearch10:[],

      search2:[],
        search:"",
        firstname:"",
        Middlename:"",
        Nickname:"",
        Lastname:"",
        Address:"",
        DateOfBirth:"",
        DateOfDeath:"",
        PlaceOfDeath:"",
        MaritalStatus:"",
        Occupation:"",

        firstname2:"",
        Middlename2:"",
        Nickname2:"",
        Lastname2:"",
        Address2:"",
        DateOfBirth2:"",
        DateOfDeath2:"",
        PlaceOfDeath2:"",
        MaritalStatus2:"",
        Occupation2:"",

        firstname3:"",
        Middlename3:"",
        Nickname3:"",
        Lastname3:"",
        Address3:"",
        DateOfBirth3:"",
        DateOfDeath3:"",
        PlaceOfDeath3:"",
        MaritalStatus3:"",
        Occupation3:"",

         firstname4:"",
        Middlename4:"",
        Nickname4:"",
        Lastname4:"",
        Address4:"",
        DateOfBirth4:"",
        DateOfDeath4:"",
        PlaceOfDeath4:"",
        MaritalStatus4:"",
        Occupation4:"",
        picture4:"",

            firstname5:"",
        Middlename5:"",
        Nickname5:"",
        Lastname5:"",
        Address5:"",
        DateOfBirth5:"",
        DateOfDeath5:"",
        PlaceOfDeath5:"",
        MaritalStatus5:"",
        Occupation5:"",
        picture5:"",

              firstname6:"",
        Middlename6:"",
        Nickname6:"",
        Lastname6:"",
        Address6:"",
        DateOfBirth6:"",
        DateOfDeath6:"",
        PlaceOfDeath6:"",
        MaritalStatus6:"",
        Occupation6:"",
        picture6:"",


               firstname7:"",
        Middlename7:"",
        Nickname7:"",
        Lastname7:"",
        Address7:"",
        DateOfBirth7:"",
        DateOfDeath7:"",
        PlaceOfDeath7:"",
        MaritalStatus7:"",
        Occupation7:"",
        picture7:"",

                     firstname8:"",
        Middlename8:"",
        Nickname8:"",
        Lastname8:"",
        Address8:"",
        DateOfBirth8:"",
        DateOfDeath8:"",
        PlaceOfDeath8:"",
        MaritalStatus8:"",
        Occupation8:"",
        picture8:"",

                          firstname9:"",
        Middlename9:"",
        Nickname9:"",
        Lastname9:"",
        Address9:"",
        DateOfBirth9:"",
        DateOfDeath9:"",
        PlaceOfDeath9:"",
        MaritalStatus9:"",
        Occupation9:"",
        picture9:"",


        
         firstname10:"",
        Middlename10:"",
        Nickname10:"",
        Lastname10:"",
        Address10:"",
        DateOfBirth10:"",
        DateOfDeath10:"",
        PlaceOfDeath10:"",
        MaritalStatus10:"",
        Occupation10:"",
        picture10:"",



        Premiumfirstname:"",
        PremiumMiddlename:"",
        PremiumNickname:"",
        PremiumLastname:"",
        PremiumAddress:"",
        PremiumDateOfBirth:"",
        PremiumDateOfDeath:"",
        PremiumPlaceOfDeath:"",
        PremiumMaritalStatus:"",
        PremiumOccupation:"",
        Premiumpicture:"",


    Premiumfirstname2:"",
        PremiumMiddlename2:"",
        PremiumNickname2:"",
        PremiumLastname2:"",
        PremiumAddress2:"",
        PremiumDateOfBirth2:"",
        PremiumDateOfDeath2:"",
        PremiumPlaceOfDeath2:"",
        PremiumMaritalStatus2:"",
        PremiumOccupation2:"",
        Premiumpicture2:"",

         Premiumfirstname3:"",
        PremiumMiddlename3:"",
        PremiumNickname3:"",
        PremiumLastname3:"",
        PremiumAddress3:"",
        PremiumDateOfBirth3:"",
        PremiumDateOfDeath3:"",
        PremiumPlaceOfDeath3:"",
        PremiumMaritalStatus3:"",
        PremiumOccupation3:"",
        Premiumpicture3:"",

        picture:"",
        
     
      modals: {
        modal1: false,
        modal2: false,
        modal3: false
      }
    };
  },
  methods : {
         greet: function (event) {},

async  ninethCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(9));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch10 = doc.data();
       //this.search9 = JSON.stringify(this.allSearch10)
       this.firstname10 = this.allSearch10.firstname;
    this.Middlename10 = this.allSearch10.Middlename;
       this.Nickname10 = this.allSearch10.Nickname;
       this.Lastname10 = this.allSearch10.Lastname;
        this.Address10 =this.allSearch10.Address;"",
        this.DateOfBirth10 =this.allSearch10.DateOfBirth;
        this.DateOfDeath10 =this.allSearch10.DateOfDeath;
        this.PlaceOfDeath10 =this.allSearch10.PlaceOfDeath;
        this.MaritalStatus10 =this.allSearch10.MaritalStatus;
        this.Occupation10 =this.allSearch10.Occupation;
       this.picture10 = this.allSearch10.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch6.Middlename);
       //alert(this.picture6)
      });
      
      },


 async  eigthCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(8));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch9 = doc.data();
       //this.search9 = JSON.stringify(this.allSearch9)
       this.firstname9 = this.allSearch9.firstname;
    this.Middlename9 = this.allSearch9.Middlename;
       this.Nickname9 = this.allSearch9.Nickname;
       this.Lastname9 = this.allSearch9.Lastname;
        this.Address9 =this.allSearch9Address;"",
        this.DateOfBirth9 =this.allSearch9.DateOfBirth;
        this.DateOfDeath9 =this.allSearch9.DateOfDeath;
        this.PlaceOfDeath9 =this.allSearch9.PlaceOfDeath;
        this.MaritalStatus9 =this.allSearch9.MaritalStatus;
        this.Occupation9 =this.allSearch9.Occupation;
       this.picture9 = this.allSearch9.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch6.Middlename);
       //alert(this.picture6)
      });
      
      },

      async  sixthCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(6));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch7 = doc.data();
       //this.search2 = JSON.stringify(this.allSearch7)
       this.firstname7 = this.allSearch7.firstname;
    this.Middlename7 = this.allSearch7.Middlename;
       this.Nickname7 = this.allSearch7.Nickname;
       this.Lastname7 = this.allSearch7.Lastname;
        this.Address7 =this.allSearch7.Address;"",
        this.DateOfBirth7 =this.allSearch7.DateOfBirth;
        this.DateOfDeath7 =this.allSearch7.DateOfDeath;
        this.PlaceOfDeath7 =this.allSearch7.PlaceOfDeath;
        this.MaritalStatus7 =this.allSearch7.MaritalStatus;
        this.Occupation7 =this.allSearch7.Occupation;
       this.picture7 = this.allSearch7.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch6.Middlename);
       //alert(this.picture6)
      });
      
      },



 async  seventhCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(7));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch8 = doc.data();
       //this.search2 = JSON.stringify(this.allSearch8)
       this.firstname8 = this.allSearch8.firstname;
    this.Middlename8 = this.allSearch8.Middlename;
       this.Nickname8 = this.allSearch8.Nickname;
       this.Lastname8 = this.allSearch8.Lastname;
        this.Address8 =this.allSearch8.Address;"",
        this.DateOfBirth8 =this.allSearch8.DateOfBirth;
        this.DateOfDeath8 =this.allSearch8.DateOfDeath;
        this.PlaceOfDeath8 =this.allSearch8.PlaceOfDeath;
        this.MaritalStatus8 =this.allSearch8.MaritalStatus;
        this.Occupation8 =this.allSearch8.Occupation;
       this.picture8 = this.allSearch8.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch6.Middlename);
       //alert(this.picture6)
      });
      
      },

                   async  fifthCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(5));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch6 = doc.data();
       //this.search2 = JSON.stringify(this.allSearch6)
       this.firstname6 = this.allSearch6.firstname;
    this.Middlename6 = this.allSearch6.Middlename;
       this.Nickname6 = this.allSearch6.Nickname;
       this.Lastname6 = this.allSearch6.Lastname;
        this.Address6 =this.allSearch6.Address;"",
        this.DateOfBirth6 =this.allSearch6.DateOfBirth;
        this.DateOfDeath6 =this.allSearch6.DateOfDeath;
        this.PlaceOfDeath6 =this.allSearch6.PlaceOfDeath;
        this.MaritalStatus6 =this.allSearch6.MaritalStatus;
        this.Occupation6 =this.allSearch6.Occupation;
       this.picture6 = this.allSearch6.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch6.Middlename);
       alert(this.picture6)
      });
      
      },
      
           async  fouthCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(4));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch5 = doc.data();
       //this.search2 = JSON.stringify(this.allSearch5)
       var firstname5 = this.allSearch5.firstname;
    this.Middlename5 = this.allSearch5.Middlename;
       this.Nickname5 = this.allSearch5.Nickname;
       this.Lastname5 = this.allSearch5.Lastname;
        this.Address5 =this.allSearch5.Address;"",
        this.DateOfBirth5 =this.allSearch5.DateOfBirth;
        this.DateOfDeath5 =this.allSearch5.DateOfDeath;
        this.PlaceOfDeath5 =this.allSearch5.PlaceOfDeath;
        this.MaritalStatus5 =this.allSearch5.MaritalStatus;
        this.Occupation5 =this.allSearch5.Occupation;
       this.picture5 = this.allSearch5.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch5.Middlename);
      // alert(this.picture5)
      });
      
      },

          async  thirdCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(3));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch4 = doc.data();
       //this.search2 = JSON.stringify(this.allSearch4)
       var firstname4 = this.allSearch4.firstname;
    this.Middlename4 = this.allSearch4.Middlename;
       this.Nickname4 = this.allSearch4.Nickname;
       this.Lastname4 = this.allSearch4.Lastname;
        this.Address4 =this.allSearch4.Address;"",
        this.DateOfBirth4 =this.allSearch4.DateOfBirth;
        this.DateOfDeath4 =this.allSearch4.DateOfDeath;
        this.PlaceOfDeath4 =this.allSearch4.PlaceOfDeath;
        this.MaritalStatus4 =this.allSearch4.MaritalStatus;
        this.Occupation4 =this.allSearch4.Occupation;
       this.picture4 = this.allSearch4.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch3.Middlename);
       //alert(this.Middlename4)
      });
      
      },
         async  secondCard(){

            const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(2));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch3 = doc.data();
       this.search2 = JSON.stringify(this.allSearch3)
       var firstname3 = this.allSearch3.firstname;
    this.Middlename3 = this.allSearch3.Middlename;
       this.Nickname3 = this.allSearch3.Nickname;
       this.Lastname3 = this.allSearch3.Lastname;
        this.Address3 =this.allSearch3.Address;"",
        this.DateOfBirth3 =this.allSearch3.DateOfBirth;
        this.DateOfDeath3 =this.allSearch3.DateOfDeath;
        this.PlaceOfDeath3 =this.allSearch3.PlaceOfDeath;
        this.MaritalStatus3 =this.allSearch3.MaritalStatus;
        this.Occupation3 =this.allSearch3.Occupation;
       this.picture3 = this.allSearch3.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch3.Middlename);
       //alert(this.Middlename3)
      });
       
      },
     
     async  premium(){

            const q = query(collection(db, "premium"),orderBy("id", "desc"), limit(1));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.premiunAllSearch = doc.data();
       this.search = JSON.stringify(this.premiunAllSearch)
       var firstname = this.premiunAllSearch.firstname;
    this.Middlename = this.premiunAllSearch.Middlename;
       this.Nickname = this.premiunAllSearch.Nickname;
       this.Lastname = this.premiunAllSearch.Lastname;
        this.Address =this.premiunAllSearch.Address;"",
        this.DateOfBirth =this.premiunAllSearch.DateOfBirth;
        this.DateOfDeath =this.premiunAllSearch.DateOfDeath;
        this.PlaceOfDeath=this.premiunAllSearch.PlaceOfDeath;
        this.MaritalStatus =this.premiunAllSearch.MaritalStatus;
        this.Occupation3 =this.premiunAllSearch.Occupation;
       this.Premiumpicture = this.premiunAllSearch.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.premiunAllSearch.Middlename);
       //alert(this.premiunAllSearch.Middlename)
      });
       
      },
 async  premium2(){

            const q = query(collection(db, "premium"),orderBy("id", "desc"), limit(2));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.premiunAllSearch2 = doc.data();
       this.search = JSON.stringify(this.premiunAllSearch2)
       var firstname = this.premiunAllSearch2.firstname;
    this.Middlename = this.premiunAllSearch2.Middlename;
       this.Nickname = this.premiunAllSearch2.Nickname;
       this.Lastname = this.premiunAllSearch2.Lastname;
        this.Address =this.premiunAllSearch2.Address;"",
        this.DateOfBirth =this.premiunAllSearch2.DateOfBirth;
        this.DateOfDeath =this.premiunAllSearch2.DateOfDeath;
        this.PlaceOfDeath=this.premiunAllSearch2.PlaceOfDeath;
        this.MaritalStatus =this.premiunAllSearch2.MaritalStatus;
        this.Occupation3 =this.premiunAllSearch2.Occupation;
       this.Premiumpicture2 = this.premiunAllSearch2.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.Premiumpicture2);
       //alert(this.Premiumpicture2)
      });
       
      },

       async  premium3(){

            const q = query(collection(db, "premium"),orderBy("id", "desc"), limit(3));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.premiunAllSearch3 = doc.data();
       this.search = JSON.stringify(this.premiunAllSearch3)
       var firstname = this.premiunAllSearch3.firstname;
    this.Middlename = this.premiunAllSearch3.Middlename;
       this.Nickname = this.premiunAllSearch3.Nickname;
       this.Lastname = this.premiunAllSearch3.Lastname;
        this.Address =this.premiunAllSearch3.Address;"",
        this.DateOfBirth =this.premiunAllSearch3.DateOfBirth;
        this.DateOfDeath =this.premiunAllSearch3.DateOfDeath;
        this.PlaceOfDeath=this.premiunAllSearch3.PlaceOfDeath;
        this.MaritalStatus =this.premiunAllSearch3.MaritalStatus;
        this.Occupation3 =this.premiunAllSearch3.Occupation;
       this.Premiumpicture3 = this.premiunAllSearch3.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.Premiumpicture2);
       //alert(this.Premiumpicture2)
      });
       
      },
  

  async  submitName(){
       alert(this.searchString);
       const q = query(collection(db, "deceased"), where("firstname", "==", this.searchString));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch = doc.data();
       this.search2 = JSON.stringify(this.allSearch)
       var firstname = this.allSearch.firstname;
    this.Middlename = this.allSearch.Middlename;
       this.Nickname = this.allSearch.Nickname;
       this.Lastname = this.allSearch.Lastname;
        this.Address=this.allSearch.Address;"",
        this.DateOfBirth=this.allSearch.DateOfBirth;
        this.DateOfDeath=this.allSearch.DateOfDeath;
        this.PlaceOfDeath=this.allSearch.PlaceOfDeath;
        this.MaritalStatus=this.allSearch.MaritalStatus;
        this.Occupation=this.allSearch.Occupation;
       this.picture = this.allSearch.picture;

       //var middlename 
       console.log(doc.id, " => ", this.allSearch.Middlename);

      });
    },
    Register (){
        //this.email = email;
alert(JSON.stringify(this.email))
const auth = getAuth();
createUserWithEmailAndPassword(auth, this.email, this.password)
  .then((userCredential) => {
    // Signed in 
    const user = userCredential.user;
    alert("usercreated")
    // ...
  })
  .catch((error) => {
    const errorCode = error.code;
    const errorMessage = error.message;
    alert(error.message)
    // ..
  });
   },
   signIn(){alert("signIn")
   
   }


  },
 async beforeMount(){
    
        const q = query(collection(db, "deceased"),orderBy("id", "desc"), limit(1));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
        // doc.data() is never undefined for query doc snapshots
        
       this.allSearch2 = doc.data();
       this.search2 = JSON.stringify(this.allSearch2)
       var firstname2 = this.allSearch2.firstname;
    this.Middlename2 = this.allSearch2.Middlename;
       this.Nickname2 = this.allSearch2.Nickname;
       this.Lastname2 = this.allSearch2.Lastname;
        this.Address2 =this.allSearch2.Address;"",
        this.DateOfBirth2 =this.allSearch2.DateOfBirth;
        this.DateOfDeath2 =this.allSearch2.DateOfDeath;
        this.PlaceOfDeath2 =this.allSearch2.PlaceOfDeath;
        this.MaritalStatus2 =this.allSearch2.MaritalStatus;
        this.Occupation2 =this.allSearch2.Occupation;
       this.picture2 = this.allSearch2.picture;
       //var middlename 
       //console.log(doc.id, " => ", this.allSearch2.Middlename);
       console.log(JSON.stringify(doc.id.length-1))
       this.secondCard();
       this.thirdCard();
       this.fouthCard();
       this.fifthCard();
       this.sixthCard();
       this.seventhCard();
       this.eigthCard();
       this.ninethCard();
this.premium();
this.premium2();
this.premium3();
      });
      
 },
};
</script>
