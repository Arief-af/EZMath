<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="nav">
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
          icon="menu"
        />

        <q-toolbar-title @click="introM" style="cursor : pointer; ">
         EZMath
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-2"
    >
      <q-list>
        <q-item-label header>Bangun Datar</q-item-label>
         <div class="line" style="width: 100%; height: 2px; background: black; opacity: 10%;"></div> <br>

        <q-item clickable tag="a" target="_blank" rel="noopener" @click="Segitiga">
          <q-item-section avatar>
            <img src="~assets/img/sg.png" style="max-width: 20px">
          </q-item-section>
          <q-item-section>
            <q-item-label>Segitiga</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable tag="a" target="_blank" rel="noopener" @click="Lingkaran">
          <q-item-section avatar>
            <img src="~assets/img/circle.png" style="max-width: 20px">
          </q-item-section>
          <q-item-section>
            <q-item-label>Lingkaran</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable tag="a" target="_blank" rel="noopener" @click="Kotak">
          <q-item-section avatar>
            <img src="~assets/img/kotak.png" style="max-width: 20px">
          </q-item-section>
          <q-item-section>
            <q-item-label>Persegi Empat</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable tag="a" target="_blank" rel="noopener" @click="PersegiPanjang">
          <q-item-section avatar>
            <img src="~assets/img/pp.png" style="max-width: 20px">
          </q-item-section>
          <q-item-section>
            <q-item-label>Persegi Panjang</q-item-label>
          </q-item-section>
        </q-item>

          <br>
          <q-item-label header>Bangun Ruang</q-item-label>
         <div class="line" style="width: 100%; height: 2px; background: black; opacity: 10%;"></div>

         <q-item clickable tag="a" target="_blank" rel="noopener">
           <q-item-section avatar>
           <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAABiElEQVRIS+1UQU7DMBAcB8lXeAK8oHAkQiL8oMuhFrfyAvhB2xfQHwAnFC5uX0CQkHttXwBPaK+VmiA3Drhg122lSBzwLVl7Z2d2ZxlqPqzm/PibALFMC5u5IuEtdCcGtQP4+pZIeTDH/EaR6FV3tmJQJQDQBHCskxRgGUOR5cgfI0TS/O8pEl0d3xggls9toLgDcBCYvAkHTzKi6S8An7Ym+X2ZmA0jLPpvdJXprzP5lOSIdLXnJn6tqPXglMgFYGR5LytnK49tJrFMNUgHwJSDHzkZuKh/P2RDRS2t/fJUxdgjGstUs9JMNu9BLNMxgEaE/KKSxQdg5HoBMFYkTlZ64Ne/NNVPM7kYuIC/pqh2AN/o+SRy3T+VaZMB2gsTRWLpk6APrOkYKBK0zgPBJq8Z0w8A+wC69hrwjOmMgx/ubDS9GlCgO7psvVZGW2Cvw1Ak5eoAjUgMtt5Fxs19w8Sl1KwA2nbyjXpgZzKuvjXLrmFiEwADDt6vZLHfBJscWGzB8D9AUKJPGUDQGRhYmEgAAAAASUVORK5CYII="/>
          </q-item-section>
          <q-item-section>
            <q-item-label>Coming soon</q-item-label>
          </q-item-section>
        </q-item>

        <q-item class="absolute-bottom">
           <q-item-section avatar>
           <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAABLklEQVRIS8WUsVHDMBSGP6dQS0aACRJKXMEGUYOPDiZgBJwJOCagThplhBScab1BGMG0KSJOIHPYsfV8wU7USvq/9/T0/xEDr2hgfToBYrOcgn0Cpr6gHKJ5pm9zqUARcGUWswhMk5AF/a6TVQgSBFwbM96y3QDjFpFCoS7WWhdtkCAgVH0pOGJ386bv1gcBYrNIAff2oTXPdOLONa7TduBn8AGctRT4qVDnB8/AiQ76i8qqf3xACjvvg5H7/2kvPpCMJO2LRpMEpP1WgB/wIzD7ExF1PfdUK4V6aRt0IyA2y3uwzwEH10GFhYem2NgDePFXqfWu2VQBdMgeibuXTRVAx2iQIJXoqAPc0CaSgrCfZzq5LM/UAfaf4t/XM5386h4X0Ef1dY3TObmvbr4ABPhtGXLu2BcAAAAASUVORK5CYII="/>
          </q-item-section>
          <q-item-section>
            <q-item-label >Created by Ariefafn</q-item-label>
          </q-item-section>
        </q-item>
        
      </q-list>
    </q-drawer>

    <q-page-container class="fixed-center" style="z-index: 999 !important">

        <!-- intro -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card card one" v-show="intro">
          <q-card-section>
            <center>
            <div class="text-h6 sec">Hallo, Welcome to</div>
            <div class="text-h4 main">EZMath 
               <q-btn color="primary" label="go" @click="leftDrawerOpen = !leftDrawerOpen" /></div> <br>
           
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>
    

        <!-- input luas segitiga -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="sg">
          <q-card-section>
            <center>
              <p>Segitiga</p>

             <div class="q-pa-md">
              <q-btn-toggle
                v-model="sgPil"
                toggle-color="primary"
                :options="[
                  {label: 'Luas', value: 'sgLuas'},
                  {label: 'Keliling', value: 'sgKel'},
                ]"
              />
            </div>
            
            <div class="luas" v-if="sgPil == 'sgLuas'">
              <q-input v-model="segitiga.alas" type="text" label="Alas" />
              <q-input v-model="segitiga.tinggi" type="text" label="Tinggi" /> <br>
              <q-btn color="primary" label="Hitung" @click="SegitigaLuas" />  
            </div> 
            <div class="keliling" v-else>
              <q-input v-model="segitiga.s1" type="text" label="sisi 1" />
              <q-input v-model="segitiga.s2" type="text" label="sisi 2" />
              <q-input v-model="segitiga.s3" type="text" label="sisi 3" /> <br>
              <q-btn color="primary" label="Hitung" @click="SegitigaKeliling" /> 
            </div>
            
            <q-btn-group spread>
             
            </q-btn-group>
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

        <!-- hasil luas segitiga -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="sgResultL">
          <q-card-section>
            <center>
              <p>Luas Segitiga</p>
              <p>Rumus : Alas x Tinggi x 1/2 <br>
              <hr>
              Diketahui : <br>
              Alas = {{segitiga.alas}} <br>
              Tinggi = {{segitiga.tinggi}} <br>
              <hr>
              Hasil = {{segitiga.alas}} x {{segitiga.tinggi}} x 1/2 = {{segitiga.resultL}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="SegitigaBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

         <!-- hasil keliling segitiga -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="sgResultK">
          <q-card-section>
            <center>
              <p>Keliling Segitiga</p>
              <p>Rumus : s1 + s2 + s3 <br>
              <hr>
              Diketahui : <br>
              Sisi 1 = {{segitiga.s1}} <br>
              sisi 2 = {{segitiga.s2}} <br>
              sisi 3 = {{segitiga.s3}} <br>
              <hr>
              Hasil = {{segitiga.s1}} + {{segitiga.s2}} + {{segitiga.s3}} = {{segitiga.resultK}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="SegitigaBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

         <!-- input Kotak -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="kt">
          <q-card-section>
            <center>
              <p>Persegi</p>                       
              <q-input v-model="kotak.sisi" type="text" label="sisi" /> <br>
            <q-btn-group spread>
              <q-btn color="primary" label="Luas" @click="KotakLuas" />  
              <q-btn color="primary" label="Keliling" @click="KotakKeliling" />  
            </q-btn-group>
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

        <!-- Result Luas Persegi -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="ktResultL">
          <q-card-section>
           <center>
              <p>Luas Kotak</p>
              <p>Rumus : sisi x sisi <br>
              <hr>
              Diketahui : <br>
              Sisi = {{kotak.sisi}} <br>
              <hr>
              Hasil = {{kotak.sisi}} x {{ kotak.sisi }} = {{kotak.resultL}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="KotakBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

         <!-- Result Keliling Persegi -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="ktResultK">
          <q-card-section>
           <center>
              <p>Keliling Kotak</p>
              <p>Rumus : 4 x sisi <br>
              <hr>
              Diketahui : <br>
              Sisi = {{kotak.sisi}} <br>
              <hr>
              Hasil = 4 x {{kotak.sisi}} = {{kotak.resultK}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="KotakBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

         <!-- input Persegi panjang-->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="pp">
          <q-card-section>
            <center>
              <p>Persegi Panjang</p>                       
              <q-input v-model="persegiPanjang.panjang" type="text" label="panjang" /> 
              <q-input v-model="persegiPanjang.lebar" type="text" label="lebar" /> <br>
            <q-btn-group spread>
              <q-btn color="primary" label="Luas" @click="PersegiPanjangLuas" />  
              <q-btn color="primary" label="Keliling" @click="PersegiPanjangKeliling" />  
            </q-btn-group>
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

        <!-- Result Luas Persegi panjang -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="ppResultL">
          <q-card-section>
           <center>
              <p>Luas Persegi Panjang</p>
              <p>Rumus : Panjang x Lebar <br>
              <hr>
              Diketahui : <br>
              Panjang = {{persegiPanjang.panjang}} <br>
              lebar = {{persegiPanjang.lebar}} <br>
              <hr>
              Hasil = {{persegiPanjang.panjang}} x {{ persegiPanjang.lebar }} = {{persegiPanjang.resultL}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="PersegiPanjangBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

         <!-- Result Keliling Persegi panjang -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="ppResultK">
          <q-card-section>
           <center>
              <p>Keliling Persegi Panjang</p>
              <p>Rumus : 2 x Panjang + 2 x Lebar <br>
              <hr>
              Diketahui : <br>
              Panjang = {{persegiPanjang.panjang}} <br>
              lebar = {{persegiPanjang.lebar}} <br>
              <hr>
              Hasil = ( 2 x {{persegiPanjang.panjang}} ) + ( 2 x {{ persegiPanjang.lebar }} ) = {{persegiPanjang.resultK}}
              <br> <br>  
        
              <q-btn color="primary" label="kembali" @click="PersegiPanjangBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

        
         <!-- input lingkaran-->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="ln">
          <q-card-section>
            <center>
              <p>lingkaran</p> 
                <q-toggle
                  v-model="lingkaran.use"
                  checked-icon="check"
                  color="primary"
                  label="Use diameter"
                  unchecked-icon="clear"
                />                      
              <q-input v-if="lingkaran.use == true" v-model="lingkaran.diameter" type="text" label="Diameter" /> 
               <q-input v-else v-model="lingkaran.jari" type="text" label="jari jari" /> <br>
            <q-btn-group spread>
              <q-btn color="primary" label="Luas" @click="LingkaranLuas" />  
              <!-- <q-btn color="primary" label="Keliling" @click="LingkaranKeliling" />   -->
            </q-btn-group>
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>

        <!-- Result Luas Lingkaran -->
        <q-intersection
          transition="slide-right"
        >
        <q-card class="my-card content one" v-show="lnResultL">
          <q-card-section>
           <center>
             <div v-if="lingkaran.use == true">
                <p>Luas lingkaran</p>
                <p>Rumus : 3.14 x Jari-jari x Jari-jari <br>
                <hr>
                Diketahui : <br>
                Diameter = {{lingkaran.diameter}} <br>
                Jari-jari = diameter/2 = {{lingkaran.diameter/2}} <br>
                <hr>
                Hasil = 3.14 x {{lingkaran.diameter/2}} x {{lingkaran.diameter/2}} = {{lingkaran.resultL}}
                <br> <br>  
             </div>
             <div v-else>
                <p>Luas lingkaran</p>
                <p>Rumus : 3.14 x Jari-jari x Jari-jari <br>
                <hr>
                Diketahui : <br>
                Diameter = jari-jari x 2 = {{lingkaran.jari*2}} <br>
                Jari-jari = {{lingkaran.jari}} <br>
                <hr>
                Hasil = 3.14 x {{lingkaran.jari}} x {{lingkaran.jari}} = {{lingkaran.resultL}}
                <br> <br>  
             </div>
             
        
              <q-btn color="primary" label="kembali" @click="LingkaranBack" />  
          
            </center>
          </q-card-section>
        </q-card>
        </q-intersection>
        
    </q-page-container>
    
    <div class="footer">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="white" fill-opacity="1" d="M0,160L80,186.7C160,213,320,267,480,250.7C640,235,800,149,960,117.3C1120,85,1280,107,1360,117.3L1440,128L1440,320L1360,320C1280,320,1120,320,960,320C800,320,640,320,480,320C320,320,160,320,80,320L0,320Z"></path></svg>
    </div>

  </q-layout>
</template>

<script>
export default {
  methods: {
    
    SegitigaBack(){
      this.sgResultL = false,
      this.sgResultK = false,
      this.sg = true,
      this.segitiga = {}
    },

    Segitiga(){
      this.intro = false,
      this.sgLuas = false,
      this.sg = true,
      this.sgResultL = false,
      this.sgResultK = false,
      this.kt = false,
      this.ktResultL = false,
      this.ktResultK = false,
      this.pp = false,
      this.ppResultL = false,
      this.ppResultK = false,
      this.leftDrawerOpen = false,
      this.ln = false,
      this.lnResultL = false,
      this.lnResultK = false
    },

    SegitigaLuas(){
      this.segitiga.resultL = this.segitiga.alas * this.segitiga.tinggi * 0.5
      this.sg = false,
      this.sgResultL = true
    },

    SegitigaKeliling(){
      this.segitiga.resultK = Number(this.segitiga.s1) + Number(this.segitiga.s2) + Number(this.segitiga.s3)
      this.sg = false
      this.sgResultK = true
    },

    introM() {
      this.intro = true,
      this.sgLuas = false,
      this.sg = false,
      this.sgResultL = false,
      this.sgResultK = false,
      this.kt = false,
      this.ktResultL = false,
      this.ktResultK = false,
      this.pp = false,
      this.ppResultL = false,
      this.ppResultK = false
      this.ln = false,
      this.lnResultL = false,
      this.lnResultK = false
    },

    Kotak(){
      this.sgResultL = false,
      this.sgResultK = false,
      this.sg = false,
      this.kotak = {},
      this.kt = true,
      this.intro = false,
      this.leftDrawerOpen = false,
      this.ppResultL = false,
      this.ppResultK = false,
      this.pp = false,
      this.ln = false,
      this.lnResultL = false,
      this.lnResultK = false
    },

    KotakLuas(){
      this.kotak.resultL = this.kotak.sisi * this.kotak.sisi
      this.ktResultL = true
      this.kt = false
    },

    KotakKeliling(){
      this.kotak.resultK = 4 * this.kotak.sisi
      this.ktResultK = true
      this.kt = false
    },

    KotakBack(){
      this.ktResultL = false,
      this.ktResultK = false,
      this.kt = true,
      this.kotak = {}
    },
    PersegiPanjang(){
      this.sgResultL = false,
      this.sgResultK = false,
      this.sg = false,
      this.kotak = {},
      this.kt = false,
      this.ktResultL = false,
      this.ktResultK = false,
      this.intro = false,
      this.pp = true,
      this.leftDrawerOpen = false,
      this.ln = false,
      this.lnResultL = false,
      this.lnResultK = false
    },

    PersegiPanjangLuas(){
      this.persegiPanjang.resultL = this.persegiPanjang.panjang * this.persegiPanjang.lebar
      this.ppResultL = true
      this.pp = false
    },

    PersegiPanjangKeliling(){
      this.persegiPanjang.resultK = 2*this.persegiPanjang.panjang + 2*this.persegiPanjang.lebar
      this.ppResultK = true
      this.pp = false
    },

    PersegiPanjangBack(){
      this.ppResultL = false,
      this.ppResultK = false,
      this.pp = true,
      this.persegiPanjang = {}
    },

    Lingkaran(){
      this.sgResultL = false,
      this.sgResultK = false,
      this.sg = false,
      this.kotak = {},
      this.kt = false,
      this.ktResultL = false,
      this.ktResultK = false,
      this.intro = false,
      this.pp = false,
      this.leftDrawerOpen = false,
      this.ln = true
    },

    LingkaranLuas(){
      if (this.lingkaran.use == true) {
        this.lingkaran.resultL = 3.14*this.lingkaran.diameter/2*this.lingkaran.diameter/2
      }else{
        this.lingkaran.resultL = 3.14*this.lingkaran.jari*this.lingkaran.jari
      }
      this.lnResultL = true
      this.ln = false
    },

    LingkaranBack(){
      this.lnResultL = false,
      this.lnResultK = false,
      this.ln = true,
      this.lingkaran = {}
    },

    LingkaranKeliling(){
      if (this.lingkaran.use == false) {
        this.lingkaran.resultL = 3.14*this.lingkaran.diameter/2*this.lingkaran.diameter/2
      }else{
        this.lingkaran.resultL = 3.14*this.lingkaran.jari*this.lingkaran.jari
      }
      this.lnResultL = false
      this.lnResultK = true
      this.ln = false
    },
  },
  
  name: 'MyLayout',
  data () {
    return {
        intro : true,
        text: '',
        leftDrawerOpen: false,
        // segitiga
        sgPil: 'sgLuas',
        sg : false,
        sgResultL : false,
        sgResultK: false,
        segitiga: [
          {
            alas: '',
            tinggi: '',
            resultL: '',
            s1: '',
            s2: '',
            s3: '',
            resultK: ''
          }
        ],
        // kotak
        kt : false,
        ktResultL: false,
        ktResultK: false,
        kotak: [
          {
            sisi : '',
            resultL: '',
            resultK: ''
          }
        ],
        // persegi panjang
        pp : false,
        ppResultL: false,
        ppResultK: false,
        persegiPanjang: [
          {
            panjang : '',
            lebar: '',
            resultL: '',
            resultK: ''
          }
        ],
        // lingkaran
        ln : false,
        lingkaran: [
          {
            use: false,
            jari: '',
            diameter: '',
            diameterInput: false
          }
        ]
    }
  }
}
</script>

<style>

.content{
  border-radius: 59% 70% 10% 40%;
  min-width: 300px;
  padding: 20px;
}

.footer{
  position: fixed;
  bottom: 0px;
  width: 100%;
  z-index: -1;
  margin-bottom: -5px;
}
.nav{
  background: white;
  color: #3AAFA9;
  height: 64px;
}

body{
  background: #3AAFA9;
}

.card{
  min-width: 300px;
  height: 200px;
  background: rgb(255, 255, 255);
  border-radius: 10% 30% 50% 70%;
  align-items: center;
  display: flex;
  justify-content: center;
}

.main{
  color: #3AAFA9;
  font-weight: bold;
}

.sec{
  color: #1A2025;
}

.one{
  animation: fade 0.5s;
}

@keyframes fade {
  from {opacity: 0%;}
  to {opacity: 100%}
}
</style>
