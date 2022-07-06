<template>
    <section class="section section-shaped section-lg my-0">
        <div class="shape shape-style-1 bg-gradient-default">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
        <div class="container pt-lg-md">
            <div class="row justify-content-center">
                <div class="col-lg-5">
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
                                <small>Or sign up with credentials</small>
                            </div>
                                  <div class="file-upload">
    <input type="file" @change="onFileChange" class="btn btn-success btn-block btn-lg"/>
    <div v-if="progress" class="progess-bar" :style="{'width': progress}">{{progress}}</div>
    <button @click="onUploadFile"  class="btn btn-success btn-block btn-lg">Upload file</button>
  </div>
                            <form role="form">
                                <base-input alternative
                                            class="mb-3"
                                            placeholder="text"
                                            addon-left-icon="ni ni-hat-3"
                                            v-model="text">
                                </base-input>
                                 <base-input alternative
                                            class="mb-3"
                                            placeholder="firstname"
                                            addon-left-icon="ni ni-hat-3"   v-model="firstname">
                                </base-input>
                                <base-input alternative
                                            class="mb-3"
                                            placeholder="Middlename"
                                            addon-left-icon="ni ni-email-83" id="Middlename" v-model="Middlename">

                                </base-input>
                                     <base-input alternative
                                            type="text"
                                            placeholder="Nickname"
                                            addon-left-icon="ni ni-lock-circle-open" id="Nickname" v-model="Nickname">
                                </base-input>
                                    <base-input alternative
                                            type="text"
                                            placeholder="Lastname"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="Lastname">
                                </base-input>
                                <base-input alternative
                                            type="text"
                                            placeholder="Address"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="Address">
                                </base-input>
                                <base-input alternative
                                            type="text"
                                            placeholder="Date of birth"
                                            addon-left-icon="ni ni-lock-circle-open"v-model="dob">
                                </base-input>
                                <base-input alternative
                                            type="text3"
                                            placeholder="Date of death"
                                            addon-left-icon="ni ni-lock-circle-open"v-model="dod">
                                </base-input>
                                <base-input alternative
                                            type="text"
                                            placeholder="Place of death"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="pod">
                                </base-input>
                                <base-input alternative
                                            type="text"
                                            placeholder="Marital status"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="maritalStatus">
                                </base-input>
    
                                  <base-input alternative
                                            type="text"
                                            placeholder="Number of children"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="numChidlren">
                                </base-input>
                      <base-input alternative
                                            type="text"
                                            placeholder="Occupation"
                                            addon-left-icon="ni ni-lock-circle-open" v-model="occupation">
                                </base-input>
                                <base-input alternative
                                            class="mb-3"
                                            placeholder="Email"
                                            addon-left-icon="ni ni-email-83">
                                </base-input>
                                <base-input alternative
                                            type="password"
                                            placeholder="Password"
                                            addon-left-icon="ni ni-lock-circle-open">
                                </base-input>
                                
                                <div class="text-muted font-italic">
                                    <small>password strength:
                                        <span class="text-success font-weight-700">strong</span>
                                    </small>
                                </div>
                                <base-checkbox>
                                    <span>I agree with the
                                        <a href="#">Privacy Policy</a>
                                    </span>
                                </base-checkbox>
                                <select  v-model="selected" class="form-control">
  <option v-for="option in options" v-bind:value="option.value">
    {{ option.text }}
  </option>
</select>

<select v-model="selected2"  :hidden="selected !== 'C'">
  <option v-for="option2 in district" v-bind:value="option2.value">
    {{ option2.text }}
  </option>
</select>
<select v-model="selected2"  :hidden="selected !== 'B'">
  <option v-for="option2 in FS_District" v-bind:value="option2.value">
    {{ option2.text }}
  </option>
</select>



<select v-model="selected4"  :hidden="selected !== 'A'">
  <option v-for="option4 in EC_District" v-bind:value="option4.value">
    {{ option4.text }}
  </option>
  
</select>

<select v-model="selected3"  :hidden="  selected !=='C' || selected2 !== 'A' ">
  <option v-for="option3 in CityOfJohannesburg" v-bind:value="option3.value">
    {{ option3.text }}
  </option>
</select>

<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_A' ">
  <option v-for="option5 in Buffalo_City_Metropolitan" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_B' ">
  <option v-for="option5 in Nelson_Mandela_Bay_Metropolitan" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_C' ">
  <option v-for="option5 in Alfred_Nzo_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_D' ">
  <option v-for="option5 in Amathole_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_E' ">
  <option v-for="option5 in Chris_Hani_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_F' ">
  <option v-for="option5 in Joe_Gqabi_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_G' ">
  <option v-for="option5 in OR_Tambo_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='A' || selected4 !== 'EC_H' ">
  <option v-for="option5 in Sarah_Baartman_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='C' || selected2 !== 'GA' ">
  <option v-for="option5 in CityOfJohannesburg" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='C' || selected2 !== 'GB' ">
  <option v-for="option5 in City_of_Tswane" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='C' || selected2 !== 'GC' ">
  <option v-for="option5 in Sedibeng_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='C' || selected2 !== 'GD' ">
  <option v-for="option5 in Metsweding_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='C' || selected2 !== 'GE' ">
  <option v-for="option5 in West_Rand_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='B' || selected2 !== 'FS_A' ">
  <option v-for="option5 in Fezile_Dabi_District_Municipality" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='B' || selected2 !== 'FS_B' ">
  <option v-for="option5 in Lejweleputswa_District_Municipality" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='B' || selected2 !== 'FS_C' ">
  <option v-for="option5 in Mangaung_Metropolitan_Municipality" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='B' || selected2 !== 'FS_D' ">
  <option v-for="option5 in Thabo_Mofutsanyana_District_Municipality" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected2"  :hidden="selected !== 'D'">
  <option v-for="option2 in KZN_District" v-bind:value="option2.value">
    {{ option2.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_K' ">
  <option v-for="option5 in Zululand_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_J' ">
  <option v-for="option5 in uThukela_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_I' ">
  <option v-for="option5 in uMzinyathi_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_H' ">
  <option v-for="option5 in uMkhanyakude_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_G' ">
  <option v-for="option5 in uMgungundlovu_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_F' ">
  <option v-for="option5 in Ugu_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_E' ">
  <option v-for="option5 in King_Cetshwayo_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_D' ">
  <option v-for="option5 in iLembe_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_C' ">
  <option v-for="option5 in Harry_Gwala_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_B' ">
  <option v-for="option5 in Amajuba_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='D' || selected2 !== 'KD_A' ">
  <option v-for="option5 in eThekwini_Metropolitan" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>

<select v-model="selected2"  :hidden="selected !== 'E'">
  <option v-for="option2 in Limpopo" v-bind:value="option2.value">
    {{ option2.text }}
  </option>
</select>

<select v-model="selected5"  :hidden="selected !=='E' || selected2 !== 'L_A' ">
  <option v-for="option5 in Capricorn_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>

<select v-model="selected5"  :hidden="selected !=='E' || selected2 !== 'L_B' ">
  <option v-for="option5 in Mopani_District" v-bind:value="option5.value">
    {{ option5.text }}
  </option>
</select>

<select v-model="selected5"  :hidden="selected !=='E' || selected2 !== 'L_C' ">
  <option v-for="option5 in Sekhukhune_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>
</select>

<select v-model="selected5"  :hidden="selected !=='E' || selected2 !== 'L_D' ">
  <option v-for="option5 in Vhembe_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='E' || selected2 !== 'L_E' ">
  <option v-for="option5 in Waterberg_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>
</select>
<select v-model="selected2"  :hidden="selected !== 'F'">
  <option v-for="option2 in Mpumalanga" v-bind:value="option2.value">
    {{ option2.text }}
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='F' || selected2 !== 'M_A' ">
  <option v-for="option5 in Ehlanzeni_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option> 
</select>
<select v-model="selected5"  :hidden="selected !=='F' || selected2 !== 'M_B' ">
  <option v-for="option5 in Gert_Sibande_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option> 
</select>
<select v-model="selected5"  :hidden="selected !=='F' || selected2 !== 'M_C' ">
  <option v-for="option5 in Nkangala_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option> 
</select>
<select v-model="selected2"  :hidden="selected !== 'G'">
  <option v-for="option2 in North_West" v-bind:value="option2.value">
    {{ option2.text }}  
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='G' || selected2 !== 'NW_A' ">
  <option v-for="option5 in Bojanala_Platinum_District" v-bind:value="option5.value">
    {{ option5.text }}   
  </option> 
</select>
<select v-model="selected5"  :hidden="selected !=='G' || selected2 !== 'NW_B' ">
  <option v-for="option5 in Dr_Kenneth_Kaunda_District" v-bind:value="option5.value">
    {{ option5.text }}   
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='G' || selected2 !== 'NW_C' ">
  <option v-for="option5 in Dr_Ruth_Segomotsi_Mompati_District" v-bind:value="option5.value">
    {{ option5.text }}   
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='G' || selected2 !== 'NW_D' ">
  <option v-for="option5 in Ngaka_Modiri_Molema_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>   
</select>
<select v-model="selected2"  :hidden="selected !== 'H'">
  <option v-for="option2 in Northern_Cape" v-bind:value="option2.value">
    {{ option2.text }}  
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='H' || selected2 !== 'NC_A' ">
  <option v-for="option5 in Frances_Baard_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='H' || selected2 !== 'NC_B' ">
  <option v-for="option5 in John_Taolo_Gaetsewe_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='H' || selected2 !== 'NC_C' ">
  <option v-for="option5 in Namakwa_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='H' || selected2 !== 'NC_D' ">
  <option v-for="option5 in Pixley_Ka_Seme_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>    
</select>
<select v-model="selected5"  :hidden="selected !=='H' || selected2 !== 'NC_E' ">
  <option v-for="option5 in ZF_Mgcawu_District" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>    
</select>
<select v-model="selected2"  :hidden="selected !== 'I'">
  <option v-for="option2 in Western_Cape" v-bind:value="option2.value">
    {{ option2.text }} 
  </option>
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_A' ">
  <option v-for="option5 in City_of_Cape_Town_Metropolitan" v-bind:value="option5.value">
    {{ option5.text }}  
  </option>    
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_B' ">
  <option v-for="option5 in Cape_Winelands_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>    
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_C' ">
  <option v-for="option5 in  Central_Karoo_Distric" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_D' ">
  <option v-for="option5 in Garden_Route_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_E' ">
  <option v-for="option5 in Overberg_District" v-bind:value="option5.value">
    {{ option5.text }} 
  </option>   
</select>
<select v-model="selected5"  :hidden="selected !=='I' || selected2 !== 'WC_F' ">
  <option v-for="option5 in West_Coast_District" v-bind:value="option5.value">
    {{ option5.text }}   
  </option>   
</select>
                                <div class="text-center">
                                    <base-button type="primary" class="my-4" v-on:click="submitName">Create account</base-button>
                                </div>
                                
                            </form>
                        </template>
                    </card>
                </div>
                <div class="container">
   </div>    


            </div>
        </div>
    </section>
</template>
<script>
import Modal from "@/components/Modal.vue";

import { createApp } from 'vue'
//import App from './App.vue'
//import store from './store'
import axios from 'axios'
import VueAxios from 'vue-axios'
//import firebase from 'firebase'
//import { getStorage, ref } from "firebase/storage";

//import Modal from "@/components/Modal.vue";
import { initializeApp } from "firebase/app";
//import {db} from "../firebase";
import * as firebase from "firebase/app";
//import 'firebase/firestore';
//import { getStorage, uploadBytes } from "firebase/storage";
import { getStorage, ref, uploadBytes,uploadBytesResumable, getDownloadURL} from "firebase/storage";
//import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

//import firebase from "firebase/app";
//import { db } from 'firebase';

//import firebase from '../firebase'

//import 'firebase/storage';
  //import PictureInput from 'vue-picture-input';
//import VueGoogleAutocomplete from 'vue-google-autocomplete'

import {collection, getDocs,addDoc,query,where,  orderBy, limit } from 'firebase/firestore/lite';
//import { getFirestore, getDocs, collection,query,where} from 'firebase/firestore/lite';

import { doc, getDoc,getFirestore } from "firebase/firestore/lite";
//import { , addDoc } from "firebase/firestore"; 
//import {Storage} from '@google-cloud/storage';
import { Observable } from 'rxjs';
//import axios from 'axios';
//import VueAxios from 'vue-axios';
//import * as cors from 'cors';
//import { https } from 'firebase-functions'

//import firebase from 'firebase/app';
//import 'firebase/firestore';
//import "firebase/storage";
//import 'firebase/firestore';
import 'firebase/firestore';


//import { storage } from '../firebase';

//import { createUser } from '../firebase.js'
import { reactive } from 'vue'
//import firebase from 'firebase'
import {  onUnmounted } from 'vue'


// App.vue
import { inject } from 'vue'

//import firebase from "./firebaseInit";
const firebaseConfig = {
   apiKey: "AIzaSyDI1jsBfenO_I0mTTNne23KEQoKTyL1CSs",
  authDomain: "arctic-acolyte-182915.firebaseapp.com",
  databaseURL: "https://arctic-acolyte-182915-default-rtdb.firebaseio.com",
  projectId: "arctic-acolyte-182915",
  storageBucket: "arctic-acolyte-182915.appspot.com",
  messagingSenderId: "1037225641803",
  appId: "1:1037225641803:web:9dc87ff62483a4aeadcace",
  measurementId: "G-3D56KWT3L5"
};

const storage = getStorage();

// Create the file metadata
/** @type {any} */
const metadata = {
  contentType: 'image/jpeg'
};
const firebaseApp = firebase.initializeApp(firebaseConfig)
const db = getFirestore(firebaseApp);

//const firebaseApp = firebase.initializeApp(firebaseConfig);
//const db = firebase.firestore();



//const db = getFirestore(firebaseApp);
//const gcloud = require('google-cloud/storage');
//const db = new Database({ firebaseApp });
//const db = firebase.firestore();
// Required for side-effects
require("firebase/firestore");
//Vue.use(VueAxios, axios)

export default {
      components: {
     
  //  Modal,
  },
  data() {
      return {
        selectedFile: "",
      progress: 0,
        files: null,
          text:"",
                province:"",
                id:0,
               firstname:"",
               Middlename:"",
               Lastname:"",
               Nickname:"",
               Address:"",
               dob:"",
               dod:"",
               pod:"",
               maritalStatus:"",
               numChidlren:"",
               occupation:"",
               image:"",
               allSearch:[],


            province_name:[],
       selectedUser: '',
           selected: 'A',
            selected2: 'A',
            selected3: 'A',
            selected4: 'A',
            selected5: 'A',
    options: [
      { text: 'Eastern Cape', value: 'A' },
      { text: 'Free State', value: 'B' },
      { text: 'Gauteng', value: 'C' },
      { text: 'KwaZulu-Natal', value: 'D' },
      { text: 'Limpopo', value: 'E' },
      { text: 'Mpumalang', value: 'F' },
      { text: 'North West', value: 'G' },
      { text: 'Northern Cape', value: 'H' },
      { text: 'Western Cape', value: 'I' },
    ],
       Western_Cape: [
      { text: 'City of Cape Town Metropolitan', value: 'WC_A' },
      { text: 'Cape Winelands District', value: 'WC_B' },
      { text: 'Central Karoo District', value: 'WC_C' },
      { text: 'Garden Route District', value: 'WC_D' },
      { text: 'Overberg District', value: 'WC_E' },
      { text: 'West Coast District', value: 'WC_F' },
     
    ],
         West_Coast_District: [
      { text: 'Abbotsdale', value: 'WC_A' },
      { text: 'Aurora', value: 'WC_B' },
      { text: 'Bitterfontein', value: 'WC_C' },
      { text: 'Chatsworth', value: 'WC_D' },
      { text: 'Citrusdal', value: 'WC_E' },
      { text: 'Clanwilliam', value: 'WC_F' },
      { text: 'Darling', value: 'WC_F' },
      { text: 'Doring Bay', value: 'WC_F' },
      { text: 'Ebenhaezer', value: 'WC_F' },
      { text: 'Eendekuil', value: 'WC_F' },
      { text: 'Elands Bay', value: 'WC_F' },
      { text: 'Graafwater', value: 'WC_F' },
      { text: 'Grotto Bay', value: 'WC_F' },
      { text: 'Hopefield', value: 'WC_F' },
      { text: 'Jacobs Bay', value: 'WC_F' },
      { text: 'Kalbaskraal', value: 'WC_F' },
      { text: 'Klawer', value: 'WC_F' },
      { text: 'Kliprand', value: 'WC_F' },
      { text: 'Koekenaa', value: 'WC_F' },
      { text: 'Koringberg', value: 'WC_F' },
      { text: 'Lamberts Bay', value: 'WC_F' },
      { text: 'Langebaan', value: 'WC_F' },
      { text: 'Lutzville', value: 'WC_F' },
      { text: 'Malmesbury', value: 'WC_F' },
      { text: 'Molsvlei', value: 'WC_F' },
      { text: 'Moorreesburg', value: 'WC_F' },
      { text: 'Nuwerus', value: 'WC_F' },
      { text: 'Paternoster', value: 'WC_F' },
      { text: 'Piketberg', value: 'WC_F' },
      { text: 'Porterville', value: 'WC_F' },
      { text: 'Putsekloof', value: 'WC_F' },
      { text: 'Redelinghuys', value: 'WC_F' },
      { text: 'Riebeeck Kasteel', value: 'WC_F' },
      { text: 'Riebeeck West', value: 'WC_F' },
      { text: 'Rietpoort', value: 'WC_F' },
      { text: 'Riverlands', value: 'WC_F' },
      { text: 'Saldanha', value: 'WC_F' },
      { text: 'St Helena Bay', value: 'WC_F' },
      { text: 'Stofkraal', value: 'WC_F' },
      { text: 'Strandfontein', value: 'WC_F' },
      { text: 'Vanrhynsdorp', value: 'WC_F' },
      { text: 'Velddrif', value: 'WC_F' },
      { text: 'Vredenburg', value: 'WC_F' },
      { text: 'Vredendal', value: 'WC_F' },
      { text: 'Wupperthal', value: 'WC_F' },
      { text: 'Yzerfontein', value: 'WC_F' },
     ],

           Overberg_District: [
      { text: 'Agulhas', value: 'WC_A' },
      { text: 'Arniston', value: 'WC_B' },
      { text: 'Barrydale', value: 'WC_C' },
      { text: 'Bettys Bay', value: 'WC_D' },
      { text: 'Birkenhead', value: 'WC_E' },
      { text: 'Bot River', value: 'WC_F' },
      { text: 'Bredasdorp', value: 'WC_E' },
      { text: 'Buffeljagsrivier', value: 'WC_E' },
      { text: 'Caledon/Myddleton', value: 'WC_E' },
      { text: 'De Kelders', value: 'WC_E' },
      { text: 'Elim', value: 'WC_E' },
      { text: 'Fishershaven', value: 'WC_E' },
      { text: 'Franskraal', value: 'WC_E' },
      { text: 'Gans Bay', value: 'WC_E' },
      { text: 'Genadendal', value: 'WC_E' },
      { text: 'Grabouw', value: 'WC_E' },
      { text: 'Greyton', value: 'WC_E' },
      { text: 'Hawston', value: 'WC_E' },
      { text: 'Hermanus', value: 'WC_E' },
      { text: 'Infanta', value: 'WC_E' },
      { text: 'Kleinmond', value: 'WC_E' },
      { text: 'Klipdale', value: 'WC_E' },
      { text: 'Malagas', value: 'WC_E' },
      { text: 'Napier', value: 'WC_E' },
      { text: 'Onrus', value: 'WC_E' },
      { text: 'Pearly Beach', value: 'WC_E' },
      { text: 'Pringle Bay', value: 'WC_E' },
      { text: 'Protem', value: 'WC_E' },
      { text: 'Riviersonderend', value: 'WC_E' },
      { text: 'Rooi-Els', value: 'WC_E' },
      { text: 'Sand Bay', value: 'WC_E' },
      { text: 'Stanford', value: 'WC_E' },
      { text: 'Struis Bay', value: 'WC_E' },
      { text: 'Suiderstrand', value: 'WC_E' },
      { text: 'Suurbraak', value: 'WC_E' },
      { text: 'Swellendam', value: 'WC_E' },
      { text: 'Theewaterskloof', value: 'WC_E' },
      { text: 'Van Dyks Bay', value: 'WC_E' },
      { text: 'Vermont', value: 'WC_E' },
      { text: 'Villiersdorp', value: 'WC_E' },
   ],
         Garden_Route_District: [
      { text: 'Albertinia', value: 'A' },
      { text: 'Boggoms Bay', value: 'B' },
      { text: 'Brandwag', value: 'C' },
      { text: 'Brenton', value: 'D' },
      { text: 'Brenton-on-Sea', value: 'E' },
      { text: 'Buffels Bay', value: 'F' },
      { text: 'Calitzdorp', value: 'F' },
      { text: 'De Rust', value: 'F' },
      { text: 'Dysselsdorp', value: 'F' },
      { text: 'Friemersheim', value: 'F' },
      { text: 'George', value: 'F' },
      { text: 'Gouritsmond', value: 'F' },
      { text: 'Great Brak River', value: 'F' },
      { text: 'Haarlemxx', value: 'F' },
      { text: 'Heidelberg', value: 'F' },
      { text: 'Herbertsdale', value: 'F' },
      { text: 'Herolds Bay', value: 'F' },
      { text: 'Jongensfontein', value: 'F' },
      { text: 'Keurboomstrand', value: 'F' },
      { text: 'Knoetzie', value: 'F' },
      { text: 'Knysna', value: 'F' },
      { text: 'Krantshoek', value: 'F' },
      { text: 'Kurland', value: 'F' },
      { text: 'Kwanokuthula', value: 'F' },
      { text: 'Ladismith', value: 'F' },
      { text: 'Mossel Bay', value: 'F' },
      { text: 'Mossel Bay', value: 'F' },
      { text: 'Natures Valley', value: 'F' },
      { text: 'Oudtshoorn', value: 'F' },
      { text: 'Plettenberg Bay', value: 'F' },
      { text: 'Rheenendal', value: 'F' },
      { text: 'Riversdale', value: 'F' },
      { text: 'Sedgefield', value: 'F' },
      { text: 'Slangrivier', value: 'F' },
      { text: 'Still Bay', value: 'F' },
      { text: 'Uniondale', value: 'F' },
      { text: 'Vanwyksdorp', value: 'F' },
      { text: 'Victoria Bay', value: 'F' },
      { text: 'Wilderness', value: 'F' },
      { text: 'Witsand', value: 'F' },
      { text: 'Wittedrift', value: 'F' },
      { text: 'Zoar', value: 'F' },
  

      
     
    ],
         Central_Karoo_Distric: [
      { text: 'Beaufort West', value: 'A' },
      { text: 'Klaarstroom', value: 'B' },
      { text: 'Laingsburg', value: 'C' },
      { text: 'Leeu Gamka', value: 'D' },
      { text: 'Matjiesfontein', value: 'E' },
      { text: 'Merweville', value: 'F' },
     { text: 'Murraysburg', value: 'F' },
     { text: 'Nelspoort', value: 'F' },
     { text: 'Prince Albert', value: 'F' },
     { text: 'Welgemoed', value: 'F' },
    ],
          Cape_Winelands_District: [
      { text: 'Ashton', value: 'A' },
      { text: 'Bonnievale', value: 'B' },
      { text: 'Ceres', value: 'C' },
      { text: 'De Doorns', value: 'D' },
      { text: 'Franschhoek', value: 'E' },
      { text: 'Gouda', value: 'F' },
      { text: 'Klapmuts', value: 'F' },
      { text: 'McGregor', value: 'F' },
      { text: 'Montagu', value: 'F' },
      { text: 'Op-Die-Berg', value: 'F' },
      { text: 'Paarl', value: 'F' },
      { text: 'Pniel', value: 'F' },
      { text: 'Prince Alfred Hamlet', value: 'F' },
      { text: 'Rawsonville', value: 'F' },
      { text: 'Robertson', value: 'F' },
      { text: 'Saron', value: 'F' },
      { text: 'Stellenbosch', value: 'F' },
      { text: 'Stellenbosch Farms', value: 'F' },
      { text: 'Touws River', value: 'F' },
      { text: 'Tulbagh', value: 'F' },
      { text: 'Wellington', value: 'F' },
      { text: 'Wolseley', value: 'F' },
      { text: 'Worcester', value: 'F' },
     
    ],
        City_of_Cape_Town_Metropolitan: [
      { text: 'Athlone', value: 'A' },
      { text: 'Atlantis', value: 'B' },
      { text: 'Belhar', value: 'C' },
      { text: 'Bellville', value: 'D' },
      { text: 'Blackheath', value: 'E' },
      { text: 'Blouberg', value: 'F' },
      { text: 'Blue Downs', value: 'F' },
      { text: 'Brackenfell', value: 'F' },
      { text: 'Cape Point', value: 'F' },
      { text: 'Cape Town', value: 'F' },
      { text: 'Delft', value: 'F' },
      { text: 'Durbanville', value: 'F' },
      { text: 'Elsies Rivier', value: 'F' },
      { text: 'Fish Hoek', value: 'F' },
      { text: 'Goodwood', value: 'F' },
      { text: 'Gordons Bay', value: 'F' },
      { text: 'Grassy Park', value: 'F' },
      { text: 'Guguletu', value: 'F' },
      { text: 'Hout Bay', value: 'F' },
      { text: 'Khayelitsha', value: 'F' },
      { text: 'Kommetjie', value: 'F' },
      { text: 'Kraaifontein', value: 'F' },
      { text: 'Kuils River', value: 'F' },
      { text: 'Langa', value: 'F' },
      { text: 'Macassar', value: 'F' },
      { text: 'Matroosfontein', value: 'F' },
      { text: 'Melkbosstrand', value: 'F' },
      { text: 'Milnerton', value: 'F' },
      { text: 'Mitchells Plain', value: 'F' },
      { text: 'Muizenberg', value: 'F' },
      { text: 'Noordhoek', value: 'F' },
      { text: 'Nyanga', value: 'F' },
      { text: 'Parow', value: 'F' },
      { text: 'Philadelphia', value: 'F' },
      { text: 'Philippi', value: 'F' },
      { text: 'Robben Island', value: 'F' },
     { text: 'Scarborough', value: 'F' },
     { text: 'Simons Town', value: 'F' },
     { text: 'Sir Lowrys Pass', value: 'F' },
     { text: 'Somerset West', value: 'F' },
     { text: 'Southern Suburbs', value: 'F' },
     { text: 'Strand', value: 'F' },
     { text: 'Table View', value: 'F' },
 
    ],
     Northern_Cape: [
      { text: 'Frances Baard District', value: 'NC_A' },
      { text: 'John Taolo Gaetsewe District', value: 'NC_B' },
      { text: 'Namakwa District', value: 'NC_C' },
      { text: 'Pixley Ka Seme District', value: 'NC_D' },
      { text: 'ZF Mgcawu District', value: 'NC_E' },
     
    ],
         ZF_Mgcawu_District: [
      { text: 'Beeshoek', value: 'A' },
      { text: 'Brandboom', value: 'B' },
      { text: 'Danielskuil', value: 'C' },
      { text: 'Eksteenskuil', value: 'D' },
      { text: 'Groblershoop', value: 'E' },
      { text: 'Kakamas', value: 'E' },
      { text: 'Keimoes', value: 'E' },
      { text: 'Kenhardt', value: 'E' },
      { text: 'Lime Acres', value: 'E' },
      { text: 'Mier', value: 'E' },
      { text: 'Postmasburg', value: 'E' },
      { text: 'Rietfontein', value: 'E' },
      { text: 'Upington', value: 'E' },

    ],
       Pixley_Ka_Seme_District: [
      { text: 'Britstown', value: 'A' },
      { text: 'Campbell', value: 'B' },
      { text: 'Carnarvon', value: 'C' },
      { text: 'Colesberg', value: 'D' },
      { text: 'Copperton', value: 'E' },
      { text: 'De Aar', value: 'E' },
      { text: 'Douglas', value: 'E' },
      { text: 'Griekwastad', value: 'E' },
      { text: 'Hanover', value: 'E' },
      { text: 'Hopetown', value: 'E' },
      { text: 'Hutchinson', value: 'E' },
      { text: 'Loxton', value: 'E' },
      { text: 'Marydale', value: 'E' },
      { text: 'Niekerkshoop', value: 'E' },
      { text: 'Norvalspont', value: 'E' },
      { text: 'Noupoort', value: 'E' },
      { text: 'Petrusville', value: 'E' },
      { text: 'Philipstown', value: 'E' },
      { text: 'Prieska', value: 'E' },
      { text: 'Richmond', value: 'E' },
      { text: 'Schmidtsdrif', value: 'E' },
      { text: 'Strydenburg', value: 'E' },
      { text: 'Van der Kloof', value: 'E' },
      { text: 'Vanwyksvlei', value: 'E' },
      { text: 'Victoria West', value: 'E' },
      { text: 'Vosburg', value: 'E' },
  
     
    ],
        Namakwa_District: [
      { text: 'Aggeneys', value: 'A' },
      { text: 'Alexander Bay', value: 'B' },
      { text: 'Brandvlei', value: 'C' },
      { text: 'Bulletrap', value: 'D' },
      { text: 'Calvinia', value: 'E' },
      { text: 'Carolusberg', value: 'E' },
      { text: 'Concordia', value: 'E' },
      { text: 'Eksteensfontein', value: 'E' },
      { text: 'Frasersburg', value: 'E' },
      { text: 'Garies', value: 'E' },
      { text: 'Hondeklip Bay,', value: 'E' },
      { text: 'Kamieskroon', value: 'E' },
      { text: 'Kleinzee', value: 'E' },
      { text: 'Koingnaas', value: 'E' },
      { text: 'Komaggas', value: 'E' },
      { text: 'Kuboes', value: 'E' },
      { text: 'Leliefontein/Kamiesberg', value: 'E' },
      { text: 'Loeriesfontein', value: 'E' },
      { text: 'Middelposx', value: 'E' },
      { text: 'Nababeep', value: 'E' },
      { text: 'Nieuwoudtville', value: 'E' },
      { text: 'OKiep', value: 'E' },
      { text: 'Onderste Doorns', value: 'E' },
      { text: 'Pella', value: 'E' },
      { text: 'Pofadder', value: 'E' },
      { text: 'Port Nolloth', value: 'E' },
      { text: 'Richtersveld', value: 'E' },
      { text: 'Sanddrift', value: 'E' },
      { text: 'Springbok', value: 'E' },
      { text: 'Steinkopf', value: 'E' },
      { text: 'Sutherland', value: 'E' },
      { text: 'Williston', value: 'E' },

     
    ],
      John_Taolo_Gaetsewe_District: [
      { text: 'Bankhara-Bodulong', value: 'A' },
      { text: 'Deben', value: 'B' },
      { text: 'Hotazel', value: 'C' },
      { text: 'Kathu', value: 'D' },
      { text: 'Kuruman', value: 'E' },
      { text: 'Mothibistad', value: 'E' },
      { text: 'Olifantshoek', value: 'E' },
      { text: 'Santoy', value: 'E' },
      { text: 'Van Zylsrus', value: 'E' },
    
     
    ],
         Frances_Baard_District: [
      { text: 'Barkly West', value: 'A' },
      { text: 'Delportshoop', value: 'B' },
      { text: 'Hartswater', value: 'C' },
      { text: 'Jan Kempdorp', value: 'D' },
      { text: 'Kimberley', value: 'E' },
      { text: 'Pampierstat', value: 'E' },
      { text: 'Ritchie', value: 'E' },
      { text: 'Warrenton', value: 'E' },
      { text: 'Windsorton', value: 'E' },
  
    ],
       North_West: [
      { text: 'Bojanala Platinum District', value: 'NW_A' },
      { text: 'Dr Kenneth Kaunda District', value: 'NW_B' },
      { text: 'Dr Ruth Segomotsi Mompati District', value: 'NW_C' },
      { text: 'Ngaka Modiri Molema District', value: 'NW_D' },
      
    ],
         Ngaka_Modiri_Molema_District: [
      { text: 'Biesiesvlei', value: 'A' },
      { text: 'Coligny', value: 'B' },
      { text: 'Delareyville', value: 'C' },
      { text: 'Disaneng', value: 'D' },
      { text: 'Groot Marico', value: 'D' },
      { text: 'Kraaipan', value: 'D' },
      { text: 'Lichtenburg', value: 'D' },
      { text: 'Madibogo', value: 'D' },
      { text: 'Mahikeng', value: 'D' },
      { text: 'Mmabatho', value: 'D' },
      { text: 'Ottosdal', value: 'D' },
      { text: 'Ottoshoop', value: 'D' },
      { text: 'Sannieshof', value: 'D' },
      { text: 'Setlagole', value: 'D' },
      { text: 'Zeerust', value: 'D' },
    
      
    ],
       Dr_Ruth_Segomotsi_Mompati_District: [
      { text: 'Amalia', value: 'A' },
      { text: 'Bloemhof', value: 'B' },
      { text: 'Christiana', value: 'C' },
      { text: 'Piet Plessis', value: 'D' },
      { text: 'Pomfret', value: 'C' },
      { text: 'Pudimoe', value: 'C' },
      { text: 'Reivilo', value: 'C' },
      { text: 'Schweizer-Reneke', value: 'C' },
      { text: 'Stella', value: 'C' },
      { text: 'Taung', value: 'C' },
      { text: 'Vryburg', value: 'C' },
  ],
      Dr_Kenneth_Kaunda_District: [
      { text: 'Hartbeesfontein', value: 'A' },
      { text: 'Klerksdorp', value: 'B' },
      { text: 'Leeudoringstad', value: 'C' },
      { text: 'Makwassie', value: 'D' },
      { text: 'Orkney', value: 'D' },
      { text: 'Potchefstroom', value: 'D' },
      { text: 'Stilfontein', value: 'D' },
      { text: 'Ventersdorp', value: 'D' },
      { text: 'Witpoort', value: 'D' },
      { text: 'Wolmaransstad', value: 'D' },
      
    ],
          Bojanala_Platinum_District: [
      { text: 'Brits', value: 'A' },
      { text: 'Derby', value: 'B' },
      { text: 'Hartbeesfontein-A', value: 'C' },
      { text: 'Hartbeespoort', value: 'D' },
      { text: 'Koster', value: 'D' },
      { text: 'Madikwe', value: 'D' },
      { text: 'Marikana', value: 'D' },
      { text: 'Mooinooi', value: 'D' },
      { text: 'Phatsima', value: 'D' },
      { text: 'Rustenburg', value: 'D' },
      { text: 'Swartruggens', value: 'D' },
      { text: 'Tlhabane', value: 'D' },
    
      
    ],
        Mpumalanga: [
      { text: 'Ehlanzeni District', value: 'M_A' },
      { text: 'Gert Sibande District', value: 'M_B' },
      { text: 'Nkangala District', value: 'M_C' },
   
    ],
          Nkangala_District: [
      { text: 'Delmas', value: 'A' },
      { text: 'Dullstroom', value: 'B' },
      { text: 'Emgwenya (Waterval Boven)', value: 'C' },
      { text: 'Hendrina', value: 'B' },
      { text: 'Kriel', value: 'B' },
      { text: 'KwaMhlanga', value: 'B' },
      { text: 'Mdala Nature Reserve', value: 'B' },
      { text: 'Middelburg', value: 'B' },
      { text: 'Ogies', value: 'B' },
      { text: 'Phola', value: 'B' },
      { text: 'Pullens Hope', value: 'B' },
      { text: 'Rietkuil', value: 'B' },
      { text: 'eMakhazeni', value: 'B' },
      { text: 'eMalahleni', value: 'B' },
      { text: 'eNtokozweni (Machadodorp)', value: 'B' },

   
    ],
            Gert_Sibande_District: [
      { text: 'Amersfoort', value: 'A' },
      { text: 'Amsterdam', value: 'B' },
      { text: 'Balfour', value: 'C' },
      { text: 'Bethal', value: 'C' },
      { text: 'Breyten', value: 'C' },
      { text: 'Carolina', value: 'C' },
      { text: 'Charl Cilliers', value: 'C' },
      { text: 'Chrissiesmeer', value: 'C' },
      { text: 'Davel', value: 'C' },
      { text: 'Ekulindeni', value: 'C' },
      { text: 'Embalenhle', value: 'C' },
      { text: 'Empuluzi', value: 'C' },
      { text: 'Ermelo', value: 'C' },
      { text: 'Evander', value: 'C' },
      { text: 'Greylingstad', value: 'C' },
      { text: 'Grootvlei', value: 'C' },
      { text: 'Kinross', value: 'C' },
      { text: 'Leandra', value: 'C' },
      { text: 'Lothair', value: 'C' },
      { text: 'Perdekop', value: 'C' },
      { text: 'Secunda', value: 'C' },
      { text: 'Standerton', value: 'C' },
      { text: 'Trichardt', value: 'C' },
      { text: 'Volksrust', value: 'C' },
      { text: 'Wakkerstroom', value: 'C' },
      { text: 'eManzana', value: 'C' },
      { text: 'eMkhondo (Piet Retief)', value: 'C' },
      
    ],
       Ehlanzeni_District: [
      { text: 'Barberton', value: 'A' },
      { text: 'Emoyeni', value: 'B' },
      { text: 'Entokozweni', value: 'C' },
      { text: 'Graskop', value: 'C' },
      { text: 'Hazyviewxxx', value: 'C' },
      { text: 'Kaapschehoop', value: 'C' },
      { text: 'Kabokweni', value: 'C' },
      { text: 'Kanyamazane', value: 'C' },
      { text: 'Komatipoort', value: 'C' },
      { text: 'Luphisi', value: 'C' },
      { text: 'Lydenburg', value: 'C' },
      { text: 'Malalane', value: 'C' },
      { text: 'Marloth Park', value: 'C' },
      { text: 'Mashishing', value: 'C' },
      { text: 'Matsulu', value: 'C' },
      { text: 'Mbombela', value: 'C' },
      { text: 'Mpakeni', value: 'C' },
      { text: 'Msogwaba', value: 'C' },
      { text: 'Ngodwana', value: 'C' },
      { text: 'Pilgrims Rest', value: 'C' },
      { text: 'Sabie', value: 'C' },
      { text: 'Sabie Park', value: 'C' },
      { text: 'Skukuza', value: 'C' },
      { text: 'Tekwane', value: 'C' },
      { text: 'White River', value: 'C' },
     
   
    ],

       Limpopo: [
      { text: 'Capricorn District', value: 'L_A' },
      { text: 'Mopani District', value: 'L_B' },
      { text: 'Sekhukhune District', value: 'L_C' },
      { text: 'Vhembe District', value: 'L_D' },
      { text: 'Waterberg District', value: 'L_E' },
    ],
          Waterberg_District: [
      { text: 'Amandelbult Mine Town', value: 'A' },
      { text: 'Bela-Bela', value: 'B' },
      { text: 'Lephalale', value: 'C' },
      { text: 'Modimolle', value: 'D' },
      { text: 'Mokopane (Potgietersrus)', value: 'E' },
    ],
          Vhembe_District: [
      { text: 'Makhado', value: 'A' },
      { text: 'Malamulele', value: 'B' },
      { text: 'Musina', value: 'C' },
      { text: 'Thohoyandou', value: 'D' },
    ],
         Sekhukhune_District: [
      { text: 'Burgersfort', value: 'A' },
      { text: 'Groblersdal', value: 'B' },
      { text: 'Marble Hall', value: 'C' },
      { text: 'Ohrigstad', value: 'D' },
      { text: 'Roossenekal', value: 'E' },
      { text: 'Schuinsdraai Nature Reserve', value: 'E' },
      { text: 'Steelpoort', value: 'E' },
    ],
     Mopani_District: [
      { text: 'Giyani', value: 'A' },
      { text: 'Gravelotte', value: 'B' },
      { text: 'Haenertsburg', value: 'C' },
      { text: 'Hoedspruit', value: 'D' },
      { text: 'Leydsdorp', value: 'E' },
      { text: 'Modjadjiskloof', value: 'E' },
            { text: 'Tzaneen', value: 'E' },

    ],
          Capricorn_District: [
      { text: 'Alldays', value: 'A' },
      { text: 'Dendron', value: 'B' },
      { text: 'Morebeng (Soekmekaar)', value: 'C' },
      { text: 'Polokwane', value: 'D' },
      { text: 'Senwabarwana (Bochum)', value: 'E' },
      { text: 'Zebediela', value: 'E' },
    ],
            KZN_District: [
      { text: 'eThekwini Metropolitan', value: 'KD_A' },
      { text: 'Amajuba District', value: 'KD_B' },
      { text: 'Harry Gwala District', value: 'KD_C' },
      { text: 'iLembe District', value: 'KD_D' },
      { text: 'King Cetshwayo District', value: 'KD_E' },
    { text: 'Ugu District', value: 'KD_F' },
    { text: 'uMgungundlovu District', value: 'KD_G' },
    { text: 'uMkhanyakude District', value: 'KD_H' },
    { text: 'uMzinyathi District', value: 'KD_I' },
    { text: 'uThukela District', value: 'KD_J' },
     { text: 'Zululand District', value: 'KD_K' },
     
    ],

                 Zululand_District: [
      { text: 'Louwsburg', value: 'ZD_A' },
      { text: 'Nongoma', value: 'ZD_B' },
      { text: 'Paulpietersburg', value: 'ZD_C' },
      { text: 'Pongola', value: 'ZD_D' },
      { text: 'Ulundi', value: 'ZD_E' },
    { text: 'Vryheid', value: 'ZD_E' },

     
    ],

             uThukela_District: [
      { text: 'Bergville', value: 'FS_A' },
      { text: 'Cathkin Park', value: 'FS_B' },
      { text: 'Colenso', value: 'FS_C' },
      { text: 'Estcourt', value: 'FS_D' },
      { text: 'Ladysmith', value: 'FS_E' },
    { text: 'Van Reenen', value: 'FS_E' },
    { text: 'Weenen', value: 'FS_E' },
    { text: 'Winterton', value: 'FS_E' },
  
     
    ],

             uMzinyathi_District: [
      { text: 'Dundee', value: 'FS_A' },
      { text: 'Glencoe', value: 'FS_B' },
      { text: 'Greytown', value: 'FS_C' },
      { text: 'Kranskop', value: 'FS_D' },
      { text: 'Nquthu', value: 'FS_E' },
    { text: 'Pomeroy', value: 'FS_E' },
   
    ],
              uMkhanyakude_District: [
      { text: 'Hlabisa', value: 'FS_A' },
      { text: 'Hluhluwe', value: 'FS_B' },
      { text: 'Ingwavuma', value: 'FS_C' },
      { text: 'Jozini', value: 'FS_D' },
      { text: 'Mbazwana', value: 'FS_E' },
    { text: 'Mkuze', value: 'FS_E' },
    { text: 'Mtubatuba', value: 'FS_E' },
    { text: 'St Lucia', value: 'FS_E' },
 
     
    ],

                uMgungundlovu_District: [
      { text: 'Ashburton', value: 'FS_A' },
      { text: 'Camperdown', value: 'FS_B' },
      { text: 'Cool Air', value: 'FS_C' },
      { text: 'Dalton', value: 'FS_D' },
      { text: 'Hilton', value: 'FS_E' },
    { text: 'Howick', value: 'FS_E' },
    { text: 'Impendle', value: 'FS_E' },
    { text: 'Mooi River', value: 'FS_E' },
    { text: 'New Hanover', value: 'FS_E' },
    { text: 'Pietermaritzburg', value: 'FS_E' },
     { text: 'Richmond', value: 'FS_E' },
     { text: 'Wartburg', value: 'FS_E' },
     
    ],
                Ugu_District: [
      { text: 'Harding', value: 'FS_A' },
      { text: 'Hibberdene', value: 'FS_B' },
      { text: 'Margate', value: 'FS_C' },
      { text: 'Pennington', value: 'FS_D' },
      { text: 'Port Edward', value: 'FS_E' },
    { text: 'Port Shepstone', value: 'FS_E' },
    { text: 'Scottburgh/Umzinto North', value: 'FS_E' },
    { text: 'Southbroom', value: 'FS_E' },
  
    ],
             King_Cetshwayo_District  : [
      { text: 'Empangeni', value: 'FS_A' },
      { text: 'Eshowe', value: 'FS_B' },
      { text: 'KwaGingindlovu', value: 'FS_C' },
      { text: 'KwaMbonambi', value: 'FS_D' },
      { text: 'Melmoth', value: 'FS_E' },
    { text: 'Mtunzini', value: 'FS_E' },
    { text: 'Nkandla', value: 'FS_E' },
    { text: 'Ntambanana', value: 'FS_E' },
    { text: 'Richards Bay', value: 'FS_E' },

    ],

                iLembe_District: [
      { text: 'Dolphin Coast/Ballito', value: 'FS_A' },
      { text: 'Isithebe', value: 'FS_B' },
      { text: 'KwaDukuza', value: 'FS_C' },
      { text: 'Mandeni', value: 'FS_D' },
      { text: 'Ndwedwe', value: 'FS_E' },
    { text: 'Nkwazi/Zinkwazi Beach', value: 'FS_E' },
  
    ],
               Harry_Gwala_District: [
      { text: 'Creighton', value: 'FS_A' },
      { text: 'Himeville', value: 'FS_B' },
      { text: 'Ixopo', value: 'FS_C' },
      { text: 'Kokstad', value: 'FS_D' },
      { text: 'Underberg', value: 'FS_E' },
    { text: 'uMzimkhulu', value: 'FS_E' },
   ],
                Amajuba_District: [
      { text: 'Charlestown', value: 'FS_A' },
      { text: 'Dannhauser', value: 'FS_B' },
      { text: 'Hattingspruit', value: 'FS_C' },
      { text: 'Newcastle', value: 'FS_D' },
      { text: 'Utrecht', value: 'FS_E' },
  
    ],
               eThekwini_Metropolitan: [
      { text: 'Amalanga', value: 'FS_A' },
      { text: 'Amanzimtoti', value: 'FS_B' },
      { text: 'Amaotana', value: 'FS_C' },
      { text: 'Berea', value: 'FS_D' },
      { text: 'Blackburn', value: 'FS_E' },
    { text: 'Bluff', value: 'FS_E' },
    { text: 'Cato Ridge', value: 'FS_E' },
    { text: 'Cele/Vumengazi', value: 'FS_E' },
    { text: 'Chatsworth', value: 'FS_E' },
    { text: 'Cibane', value: 'FS_E' },
     { text: 'Clermont', value: 'FS_E' },
         { text: 'Clifton Canyon', value: 'FS_E' },
        { text: 'Craigieburn', value: 'FS_E' },
       { text: 'Dassenhoek', value: 'FS_E' },
           { text: 'Desainager', value: 'FS_E' },
        { text: 'Durban', value: 'FS_E' },
        { text: 'Durban International Airport', value: 'FS_E' },
        { text: 'Durban North', value: 'FS_E' },
        { text: 'Durban South', value: 'FS_E' },
        { text: 'Emalangeni', value: 'FS_E' },
        { text: 'Embo/Nksa Isimahla', value: 'FS_E' },
        { text: 'Emona', value: 'FS_E' },
        { text: 'Ethekwini', value: 'FS_E' },
        { text: 'Everton', value: 'FS_E' },
        { text: 'Ezembeni', value: 'FS_E' },
        { text: 'Folweni', value: 'FS_E' },
        { text: 'Gcumisa', value: 'FS_E' },
        { text: 'Genazzano', value: 'FS_E' },
        { text: 'Gillitts', value: 'FS_E' },
        { text: 'Glenashley', value: 'FS_E' },
        { text: 'Golokodo-Ensimbini', value: 'FS_E' },
        { text: 'Hambanathi', value: 'FS_E' },
        { text: 'Hillcrest', value: 'FS_E' },
        { text: 'Ilanga', value: 'FS_E' },
        { text: 'Ilfracombe', value: 'FS_E' },
        { text: 'Illovo North', value: 'FS_E' },
        { text: 'Illovo South', value: 'FS_E' },
        { text: 'Inanda', value: 'FS_E' },
        { text: 'Inchanga', value: 'FS_E' },
        { text: 'Iqadi', value: 'FS_E' },
        { text: 'Isipingo', value: 'FS_E' },
        { text: 'Isipingo Beach', value: 'FS_E' },
        { text: 'Kingsburgh', value: 'FS_E' },
        { text: 'Klaarwater', value: 'FS_E' },
        { text: 'Kloof', value: 'FS_E' },
        { text: 'KwaDabeka', value: 'FS_E' },
        { text: 'KwaMashu', value: 'FS_E' },
        { text: 'KwaNdengezi', value: 'FS_E' },
        { text: 'La Mercy', value: 'FS_E' },
        { text: 'Lotus Park,', value: 'FS_E' },
        { text: 'Luganda', value: 'FS_E' },
        { text: 'Luthuli/Umnini Trust', value: 'FS_E' },
        { text: 'Magabeni', value: 'FS_E' },
        { text: 'Malagazi', value: 'FS_E' },
        { text: 'Mangangeni/Vumazonke', value: 'FS_E' },
        { text: 'Maphephetha', value: 'FS_E' },
        { text: 'Mariannhill', value: 'FS_E' },
        { text: 'Mawotana', value: 'FS_E' },
        { text: 'Mawothi', value: 'FS_E' },
        { text: 'Molweni', value: 'FS_E' },
        { text: 'Mount Edgecombe', value: 'FS_E' },
        { text: 'Mount Moreland', value: 'FS_E' },
        { text: 'Mpolo', value: 'FS_E' },
        { text: 'Mpumalanga', value: 'FS_E' },
        { text: 'New Germany', value: 'FS_E' },
        { text: 'Newlands East', value: 'FS_E' },
        { text: 'Newlands West', value: 'FS_E' },
        { text: 'Ngcolosi', value: 'FS_E' },
        { text: 'Ngqungqulu', value: 'FS_E' },
        { text: 'Ntuzuma', value: 'FS_E' },
        { text: 'Roseneath', value: 'FS_E' },
        { text: 'Sapref', value: 'FS_E' },
        { text: 'Shallcross', value: 'FS_E' },
        { text: 'Sobonakhona', value: 'FS_E' },
        { text: 'Thoyana', value: 'FS_E' },
        { text: 'Tongaat', value: 'FS_E' },
        { text: 'Tongaat Beach', value: 'FS_E' },
        { text: 'Tshelimnyama', value: 'FS_E' },
        { text: 'UmgogintwiniUmbumbulu', value: 'FS_E' },
        { text: 'Umdloti', value: 'FS_E' },
        { text: 'Umgababa', value: 'FS_E' },
        { text: 'Umhlanga', value: 'FS_E' },
        { text: 'Umkomaas', value: 'FS_E' },
        { text: 'Umlazi', value: 'FS_E' },
        { text: 'Verulam', value: 'FS_E' },
        { text: 'Waterfall', value: 'FS_E' },
        { text: 'Westbrook', value: 'FS_E' },
        { text: 'Westville', value: 'FS_E' },
        { text: 'Ximba', value: 'FS_E' },
      

     
    ],
           FS_District: [
      { text: '	Fezile Dabi District Municipality', value: 'FS_A' },
      { text: 'Lejweleputswa District Municipality', value: 'FS_B' },
      { text: '	Mangaung Metropolitan Municipality', value: 'FS_C' },
      { text: 'Thabo Mofutsanyana District Municipality', value: 'FS_D' },
      { text: '	Xhariep District Municipality', value: 'FS_E' },
     
    ],
               Xhariep_District_Municipality: [
      { text: 'Bethulie', value: 'FS_A' },
      { text: 'Edenburg', value: 'FS_B' },
      { text: 'Fauresmith', value: 'FS_C' },
      { text: 'Gariep Dam', value: 'FS_D' },
      { text: 'Jacobsdal', value: 'FS_E' },
      { text: 'Jagersfontein', value: 'FS_E' },
      { text: 'Koffiefontein', value: 'FS_E' },
      { text: 'Luckhoff', value: 'FS_E' },
      { text: 'Oppermansgronde', value: 'FS_E' },
      { text: 'Petrusburg', value: 'FS_E' },
      { text: 'Philippolis', value: 'FS_E' },
      { text: 'Reddersburg', value: 'FS_E' },
      { text: 'Rouxville', value: 'FS_E' },
      { text: 'Smithfield', value: 'FS_E' },
      { text: 'Springfontein', value: 'FS_E' },
      { text: 'Trompsburg', value: 'FS_E' },
      { text: 'Waterkloof', value: 'FS_E' },
       { text: 'Zastron', value: 'FS_E' },
     
    ],
              Thabo_Mofutsanyana_District_Municipality: [
      { text: 'Arlington', value: 'EC_A' },
      { text: 'Bethlehem', value: 'EC_B' },
      { text: 'Clarens', value: 'EC_C' },
      { text: 'Clocolan', value: 'EC_D' },
      { text: 'Excelsior', value: 'EC_E' },
      { text: 'Ficksburg', value: 'EC_E' },
      { text: 'Fouriesburg', value: 'EC_E' },
      { text: 'Golden Gate Highlands National Park', value: 'EC_E' },
      { text: 'Harrismith', value: 'EC_E' },
      { text: 'Hobhouse', value: 'EC_E' },
      { text: 'Kestell', value: 'EC_E' },
      { text: 'Ladybrand', value: 'EC_E' },
      { text: 'Lindley', value: 'EC_E' },
      { text: 'Marquard', value: 'EC_E' },
      { text: 'Memel', value: 'EC_E' },
      { text: 'Paul Roux', value: 'EC_E' },
      { text: 'Petrus Steyn', value: 'EC_E' },
      { text: 'Phuthaditjhaba', value: 'EC_E' },
      { text: 'Reitz', value: 'EC_E' },
      { text: 'Rosendal', value: 'EC_E' },
      { text: 'Senekal', value: 'EC_E' },
      { text: 'Thaba Patchoa', value: 'EC_E' },
      { text: 'Tweespruit', value: 'EC_E' },
      { text: 'Vrede', value: 'EC_E' },
      { text: 'Warden', value: 'EC_E' },
     
     
    ],
           Mangaung_Metropolitan_Municipality: [
      { text: 'Bloemfontein', value: 'EC_A' },
      { text: 'Botshabelo', value: 'EC_B' },
      { text: 'Dewetsdorp', value: 'EC_C' },
      { text: 'Mangaung', value: 'EC_D' },
      { text: 'Soutpan', value: 'EC_E' },
      { text: 'Thaba Nchu', value: 'EC_E' },
      { text: 'Van Stadensrus', value: 'EC_E' },
      { text: 'Wepener', value: 'EC_E' },

    ],
           Lejweleputswa_District_Municipality: [
      { text: 'Allanridge', value: 'EC_A' },
      { text: 'Boshof', value: 'EC_B' },
      { text: 'Bothaville', value: 'EC_C' },
      { text: 'Brandfort', value: 'EC_D' },
      { text: 'Bultfontein', value: 'EC_E' },
      { text: 'Dealesville', value: 'EC_E' },
      { text: 'Hennenman', value: 'EC_E' },
      { text: 'Hertzogville', value: 'EC_E' },
      { text: 'Hoopstad', value: 'EC_E' },
      { text: 'Odendaalsrus', value: 'EC_E' },
      { text: 'Soutpan', value: 'EC_E' },
      { text: 'Theunissen', value: 'EC_E' },
      { text: 'Ventersburg', value: 'EC_E' },
      { text: 'Verkeerdevlei', value: 'EC_E' },
      { text: 'Virginia', value: 'EC_E' },
      { text: 'Welkom', value: 'EC_E' },
      { text: 'Wesselsbron', value: 'EC_E' },
      { text: 'Winburg', value: 'EC_E' },
     
    ],
           Fezile_Dabi_District_Municipality: [
      { text: 'Cornelia', value: 'EC_A' },
      { text: 'Deneysville', value: 'EC_B' },
      { text: 'Edenville', value: 'EC_C' },
      { text: 'Frankfort', value: 'EC_D' },
      { text: 'Heilbron', value: 'EC_E' },
      { text: 'Koppies', value: 'EC_E' },
      { text: 'Kragbron', value: 'EC_E' },
      { text: 'Kroonstad', value: 'EC_E' },
      { text: 'Oranjeville', value: 'EC_E' },
      { text: 'Parys', value: 'EC_E' },
      { text: 'Renovaal', value: 'EC_E' },
      { text: 'Sasolburg', value: 'EC_E' },
      { text: 'Steynsrus', value: 'EC_E' },
      { text: 'Tweeling', value: 'EC_E' },
      { text: 'Vierfontein', value: 'EC_E' },
      { text: 'Viljoenskroon', value: 'EC_E' },
      { text: 'Villiers', value: 'EC_E' },
      { text: 'Vredefort', value: 'EC_E' },
  
     
    ],
       EC_District: [
      { text: 'Buffalo City Metropolitan', value: 'EC_A' },
      { text: 'Nelson Mandela Bay Metropolitan', value: 'EC_B' },
      { text: 'Alfred Nzo District', value: 'EC_C' },
      { text: 'Amathole District', value: 'EC_D' },
      { text: 'Chris Hani District', value: 'EC_E' },
      { text: 'Joe Gqabi District', value: 'EC_F' },
      { text: 'OR Tambo District', value: 'EC_G' },
      { text: 'Sarah Baartman District', value: 'EC_H' },
    ],

      Sarah_Baartman_District: [
      { text: 'Aberdeen', value: 'A' },
      { text: 'Addo', value: 'B' },
      { text: 'Adendorp', value: 'C' },
      { text: 'Alexandria', value: 'C' },
      { text: 'Alicedale', value: 'C' },
      { text: 'Bathurst', value: 'C' },
      { text: 'Boknes/Cannon Rocks', value: 'C' },
      { text: 'Cape St Francis', value: 'C' },
      { text: 'Clarkson', value: 'C' },
      { text: 'Cookhouse', value: 'C' },
      { text: 'Graaff-Reinet', value: 'C' },
      { text: 'Hankey', value: 'C' },
      { text: 'Humansdorp', value: 'C' },
      { text: 'Jansenville', value: 'C' },
      { text: 'Jeffreys Bay', value: 'C' },
      { text: 'Joubertina', value: 'C' },
      { text: 'Kareedouw', value: 'C' },
      { text: 'Kendrew', value: 'C' },
      { text: 'Kenton-on-Sea', value: 'C' },
      { text: 'Kirkwood', value: 'C' },
      { text: 'Klipplaat', value: 'C' },
      { text: 'Krakeel River', value: 'C' },
      { text: 'Loerie', value: 'C' },
      { text: 'Louterwater', value: 'C' },
      { text: 'Makhanda (Grahamstown)', value: 'C' },
      { text: 'Misgund', value: 'C' },
      { text: ' Nieu-Bethesda', value: 'C' },
      { text: 'Nompumelelo', value: 'C' },
      { text: 'Oyster Bay', value: 'C' },
      { text: 'Patensie', value: 'C' },
     { text: 'Paterson', value: 'C' },
      { text: 'Pearston', value: 'C' },
       { text: 'Petersburg', value: 'C' },
        { text: 'Port Alfred', value: 'C' },
         { text: 'Riebeek East', value: 'C' },
          { text: 'Rietbron', value: 'C' },
           { text: 'Sanddrif', value: 'C' },          
            { text: 'Seafield', value: 'C' },
             { text: 'Sidbury', value: 'C' },
              { text: 'Somerset East', value: 'C' },
                 { text: 'St Francis Bay', value: 'C' },

             { text: 'Steytlerville', value: 'C' },
             { text: 'Storms River', value: 'C' },
             { text: 'Thornhill', value: 'C' },
             { text: 'Waterford', value: 'C' },
             { text: 'Willowmore', value: 'C' },
             { text: 'Woodlands', value: 'C' },
             

              



    ],
         OR_Tambo_District: [
      { text: 'Flagstaff', value: 'A' },
      { text: 'Libode', value: 'B' },
      { text: 'Lusikisiki', value: 'C' },
      { text: 'Mqanduli', value: 'C' },
      { text: 'Mthatha (previously Umtata)', value: 'C' },
      { text: 'Ngqeleni', value: 'C' },
      { text: 'Port St Johns', value: 'C' },
      { text: 'Qumbu', value: 'C' },
      { text: 'Tsolo', value: 'C' },

    ],
          Joe_Gqabi_District: [
      { text: 'Aliwal North', value: 'A' },
      { text: 'Barkly East', value: 'B' },
      { text: 'Burgersdorp', value: 'C' },
      { text: 'Jamestown', value: 'C' },
      { text: 'Lady Grey', value: 'C' },
      { text: 'Maclear', value: 'C' },
      { text: 'Mount Fletcher', value: 'C' },
      { text: 'Oviston', value: 'C' },
      { text: 'Rhodes', value: 'C' },
      { text: 'Rossouw', value: 'C' },
      { text: 'Sterkspruit', value: 'C' },
      { text: 'Steynsburg', value: 'C' },
      { text: 'Ugie', value: 'C' },
      { text: 'Venterstad', value: 'C' },



    ],
           Chris_Hani_District: [
      { text: ' Cacadu (Lady Frere)', value: 'A' },
      { text: 'Cala', value: 'B' },
      { text: 'Cofimvaba', value: 'C' },
      { text: 'Cradock', value: 'C' },
      { text: 'Dordrecht', value: 'C' },
      { text: 'Engcobo', value: 'C' },
      { text: 'Hofmeyr', value: 'C' },
      { text: 'Indwe', value: 'C' },
      { text: 'Khowa (Elliot)', value: 'C' },
      { text: 'Komani (Queenstown)', value: 'C' },
      { text: 'Middelburg', value: 'C' },
      { text: 'Molteno', value: 'C' },
      { text: 'Mount Zebra National Park', value: 'C' },
      { text: 'Sada', value: 'C' },
      { text: 'Sterkstroom', value: 'C' },
      { text: 'Tarkastad', value: 'C' },
      { text: 'Tsomo', value: 'C' },
      { text: 'Whittlesea', value: 'C' },
     
    ],
           Amathole_District: [
      { text: 'Adelaide', value: 'A' },
      { text: 'Alice', value: 'B' },
      { text: 'Amatola Coastal', value: 'C' },
      { text: 'Bedford', value: 'C' },
      { text: 'Butterworth', value: 'C' },
      { text: 'Cathcart', value: 'C' },
      { text: 'Dutywa', value: 'C' },
      { text: 'Elliotdale', value: 'C' },
      { text: 'Fort Beaufort', value: 'C' },
      { text: 'Hamburg', value: 'C' },
      { text: 'Hogsback', value: 'C' },
      { text: 'Kei Mouth', value: 'C' },
      { text: 'Kei Road', value: 'C' },
      { text: 'Keiskammahoek', value: 'C' },
      { text: 'Kentani', value: 'C' },
      { text: 'Komga', value: 'C' },
      { text: 'Middeldrift', value: 'C' },
      { text: 'Morgan Bay', value: 'C' },
      { text: 'Ngqamakhwe', value: 'C' },
      { text: 'Peddie', value: 'C' },
      { text: 'Seymore', value: 'C' },
      { text: 'Stutterheim', value: 'C' },
      { text: 'Willowvale', value: 'C' },
    ],
           Alfred_Nzo_District: [
      { text: 'Bizana', value: 'A' },
      { text: 'Cedarville', value: 'B' },
      { text: 'KwaBhaca (Mount Frere)', value: 'C' },
      { text: 'Matatiele', value: 'C' },
      { text: 'Tabankulu', value: 'C' },
      { text: 'eMaxesibeni (Mount Ayliff)', value: 'C' },
     
    ],
         Nelson_Mandela_Bay_Metropolitan: [
      { text: 'Bethelsdorp', value: 'A' },
      { text: 'Bloemendal', value: 'B' },
      { text: 'Blue Horizon Bay', value: 'C' },
      { text: 'Clarendon Marine', value: 'C' },
      { text: 'Despatch', value: 'C' },
      { text: 'KwaNobuhle', value: 'C' },
      { text: 'Motherwell', value: 'C' },
      { text: 'Port Elizabeth', value: 'C' },
            { text: 'Summerstrand', value: 'C' },
      { text: 'Swartkops', value: 'C' },
      { text: 'Uitenhage', value: 'C' },

    ],
           Buffalo_City_Metropolitan: [
      { text: 'Beacon Bay', value: 'A' },
      { text: 'Berlin', value: 'B' },
      { text: 'Bisho', value: 'C' },
      { text: 'Breidbach', value: 'C' },
      { text: 'Dimbaza', value: 'C' },
      { text: 'East London', value: 'C' },
      { text: 'Kidds Beach', value: 'C' },
      { text: 'King Williams Town', value: 'C' },
      { text: 'Mdantsane', value: 'C' },
      { text: 'Phakamisa', value: 'C' },
      { text: 'Potsdam', value: 'C' },
      { text: 'Zwelitsha', value: 'C' },

    ],
      district: [
      { text: 'City of Johannesburg', value: 'GA' },
      { text: 'City of Tswane', value: 'GB' },
      { text: 'Sedibeng District', value: 'GC' },
      { text: 'Metsweding District', value: 'GD' },
      { text: 'West Rand District', value: 'GE' },
    
    ],
        West_Rand_District: [
      { text: 'Carletonville', value: 'A' },
      { text: 'Fochville', value: 'B' },
      { text: 'Krugersdorp', value: 'C' },
      { text: 'Magaliesburg', value: 'C' },
      { text: 'Muldersdrift', value: 'C' },
      { text: 'Randfontein', value: 'C' },
      { text: 'Wedela', value: 'C' },
      { text: 'Westonaria', value: 'C' },
    ],
        Metsweding_District: [
      { text: 'Kungwini Local Municipality', value: 'A' },
      { text: 'Nokeng tsa Taemane Local Municipality', value: 'B' },

    ],
      
      Sedibeng_District: [
      { text: 'De Deur/Walkerville', value: 'A' },
      { text: 'Devon', value: 'B' },
      { text: 'Eikenhof', value: 'C' },
      { text: 'Evaton', value: 'C' },
      { text: 'Heidelberg', value: 'C' },
      { text: 'Meyerton', value: 'C' },
      { text: 'Nigel', value: 'C' },
      { text: 'Sebokeng', value: 'C' },
      { text: 'Vaal Marina', value: 'C' },
      { text: ' Vaal Marina, Vaal Oewer', value: 'C' },
      { text: 'Vanderbijlpark', value: 'C' },
      { text: 'Vereeniging', value: 'C' },
      { text: 'Vischkuil', value: 'C' },
  
    
    ],
          City_of_Tswane: [
      { text: 'Akasia', value: 'A' },
      { text: 'Atteridgeville', value: 'B' },
      { text: 'Bronberg', value: 'C' },
      { text: 'Bronkhorstspruit', value: 'C' },
      { text: 'Centurion', value: 'C' },
      { text: 'Crocodile River', value: 'C' },
      { text: 'Cullinan/Rayton/Refilwe', value: 'C' },
      { text: 'Eersterust', value: 'C' },
      { text: 'Ekangala', value: 'C' },
      { text: 'Elands River', value: 'C' },
      { text: 'Ga-Rankuwa', value: 'C' },
      { text: 'Hammanskraal', value: 'C' },
      { text: 'Laudium', value: 'C' },
      { text: 'Mabopane', value: 'C' },
      { text: 'Mamelodi', value: 'C' },
      { text: 'Olievenhoutbosch', value: 'C' },
      { text: 'Pienaarsrivier', value: 'C' },
      { text: 'Pretoria', value: 'C' },
      { text: 'Soshanguve', value: 'C' },
      { text: 'Rethabiseng', value: 'C' },
      { text: 'Roodeplaat', value: 'C' },
      { text: 'Temba', value: 'C' },
      { text: 'Winterveld', value: 'C' },
      { text: 'Zithobeni', value: 'C' },
     

    
    ],
        CityOfJohannesburg: [
      { text: 'Alexandra', value: 'A' },
      { text: 'Lenasia', value: 'B' },
      { text: 'Midrand', value: 'C' },
      { text: 'Randburg', value: 'C' },
      { text: 'Roodepoort', value: 'C' },
      { text: 'Sandton', value: 'C' },
      { text: 'Soweto', value: 'C' },
      { text: 'Alberton', value: 'C' },
      { text: 'Boksburg', value: 'C' },
      { text: 'Brakpan', value: 'C' },
      { text: 'Daveyton', value: 'C' },
      { text: 'Devon', value: 'C' },
      { text: 'Duduza', value: 'C' },
      { text: 'Edenvale', value: 'C' },
      { text: 'Germiston', value: 'C' },
      { text: 'Impumelelo', value: 'C' },
      { text: 'Isando  ', value: 'C' },
      { text: 'Katlehong', value: 'C' },
      { text: 'Kempton Park', value: 'C' },
      { text: 'Kwathema', value: 'C' },
      { text: 'Reiger Park', value: 'C' },
      { text: 'Springs', value: 'C' },
      { text: 'Tembisa', value: 'C' },
      { text: 'Thokoza', value: 'C' },
      { text: 'Tsakane', value: 'C' },
      { text: 'Vosloorus', value: 'C' },
      { text: 'Wattville', value: 'C' },
     ],
        SedibengDistrict: [
      { text: 'City of Johannesburg', value: 'A' },
      { text: 'City of Tswane', value: 'B' },
      { text: 'Sedibeng District', value: 'C' },
      { text: 'Metsweding District', value: 'C' },
      { text: 'West Rand District', value: 'C' },
    
    ],
      }
  },
  methods:{
        onFileChange(e) {
      const selectedFile = e.target.files[0]; // accessing file
      this.selectedFile = selectedFile;
      this.progress = 0;
    },
        onUploadFile() {
          
      const formData = new FormData();
      formData.append("file", this.selectedFile); // appending file

      // sending file to backend
      // Upload file and metadata to the object 'images/mountains.jpg'
const storageRef = ref(storage, 'images/' + this.selectedFile.name);
//const uploadTask = uploadBytesResumable(storageRef, metadata);
const uploadTask = uploadBytesResumable(storageRef, this.selectedFile, metadata);

// Listen for state changes, errors, and completion of the upload.
uploadTask.on('state_changed',
  (snapshot) => {
    // Get task progress, including the number of bytes uploaded and the total number of bytes to be uploaded
    const progress = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
    console.log('Upload is ' + progress + '% done');
    alert('Upload is ' + progress + '% done');
    switch (snapshot.state) {
      case 'paused':
        console.log('Upload is paused');
        break;
      case 'running':
        console.log('Upload is running');
        break;
    }
  }, 
  (error) => {
    // A full list of error codes is available at
    // https://firebase.google.com/docs/storage/web/handle-errors
    switch (error.code) {
      case 'storage/unauthorized':
        // User doesn't have permission to access the object
        break;
      case 'storage/canceled':
        // User canceled the upload
        break;

      // ...

      case 'storage/unknown':
        // Unknown error occurred, inspect error.serverResponse
        break;
    }
  }, 
  () => {
    // Upload completed successfully, now we can get the download URL
    getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
      console.log('File available at', downloadURL);
      this.image = downloadURL;
    });
  }
);
    },
    uploadFile(){
 
     axios.get("http://localhost:4500/flower.jpeg")
            .then((resp) => {
             

                return this.image  = resp.data;
                console.log("here is the image");
            }).catch((err)=>{
                console.log(err)
            });z
    },

        
         async submitName(){
     this.id++
           //parseInt(this.id) = parseInt(this.id) + 1,
            // int docID = this.id + 1,
const docRef = await addDoc(collection(db, "premium"), {
 id: this.id,
  firstname: this.firstname,
  Middlename: this.Middlename,
  Nickname:this.Nickname,
  Lastname:this.Lastname,
  Address:this.Address,
  dob:this.dob,
  dod:this.dod,
  pod:this.pod,
  maritalStatus:this.maritalStatus,
  numChidlren:this.numChidlren,
  occupation:this.occupation,
  picture :this.image,
});
console.log("Document written with ID: ", docRef.id);
console.log("the total is",this.id)
alert("Obituary Added id ",this.id );
         },
   
    
  
      },
      async beforeMount(){
    
        const q = query(collection(db, "premium"),orderBy("id", "desc"), limit(1));
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
         //doc.data() is never undefined for query doc snapshots
        
       this.allSearch = doc.data();
    
       this.id = this.allSearch.id;
     
    
      });
          
 },
  
};
</script>
<style>
</style>
