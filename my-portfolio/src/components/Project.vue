<template>
<v-container
grid-list-lg
>
  <v-layout
  row
  wrap
    >
    <v-flex xs6
      v-for="(project, index) in projects" :key="index"
      v-model="projects"
    >
    <v-hover>
      <v-card
      slot-scope="{ hover }"
      :class="`elevation-${hover ? 12 : 2}`"
      >
        <v-img
         @click="detailPj(project)"
          class="pink--text"
          height="400px"
          :src=project.titleImage
        >
        <!--
          <v-expand-transition>
          <div
            v-if="hover"
            class="d-flex transition-fast-in-fast-out light-blue lighten-5 v-card--reveal display-3 white--text"
            style="height: 100%;"
          >
            click!.!
          </div>
        </v-expand-transition>
         -->
          <v-container>
            <v-layout>
              <v-flex>
                <span class="headline">{{ project.title }}</span>
              </v-flex>
            </v-layout>
          </v-container>

        </v-img>
        <v-card-title>
          <div>
            <span class="blue--text">{{ project.contents }}</span><br>
            <span>Whitehaven Beach</span><br>
            <span>Whitsunday Island, Whitsunday Islands</span>
          </div>
        </v-card-title>

        <v-card-title>
            <v-chip
              v-for="skill in project.skills"
              :key="skill"
            >
              {{ skill }}
            </v-chip>
        </v-card-title>
<!--
        <v-card-actions>
          <v-btn flat color="orange">Share</v-btn>
          <v-btn flat color="orange">Explore</v-btn>
        </v-card-actions> -->
      </v-card>
    </v-hover>
    </v-flex>
  </v-layout>

 <!-- <v-carousel>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel> -->
<!-- full-height -->
   <v-dialog
   v-model="dialog"
   @keyup.esc="close"
   max-width="1050"
   delimiter-icon
      >

      <v-card
        black

      max-width="1050"
      >
        <v-carousel
        height="770"
        :cycle="false"  >
    <v-carousel-item

      v-for="(item,i) in items"
      :key="i"
    >
     <v-img
     max-width="1050"
      :src="item.src"
     >
     </v-img>

    </v-carousel-item>

  </v-carousel>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>
export default {
  data () {
      return {
        reviews: 413,
        value: 4.5,
        projects: [
          {
            _id: 1,
            title: '혼자하는 일본어 회화',
            contents: '음성인식 + 인공지능(심심이 급)',
            detail: '음성인식Api + 일본어 형태소분석기Api 회화공부 App',
            motive: '시간, 장소, 언제어디서나, 외국어 대화를 하고자 함',
            titleImage: 'pj1.jpg',
            skills: [
              'java',
              'Struts2',
              'Google음성API',
              'ResponsiveVoiceAPI',
              'Kuromoji Api',
              'Bootstrap',
              'Jquery',
              'oracleDB',
              'myBtis',
              ],
              pjsrc: 'doc'
          },

          {
            _id: 2,
            title: '라이센스 발급 페이지',
            contents: '고객데이터로 base64 암호화하여 라이센스 발급페이지',
            detail: '음성인식Api + 일본어 형태소분석기Api 회화공부 App',
            motive: '시간, 장소, 언제어디서나, 외국어 대화를 하고자 함',
            titleImage: 'pj3.jpg',
            skills: [
              'JAVA',
              'SpringBoot',
              'MySQL',
              'MyBatis',
              'JSTL',
              'EL',
              'Base64 incoding'
            ]
          },
          {
            _id: 3,
            title: 'story board',
            contents: 'vue + firebase 활용 url게시판',
            detail: '음성인식Api + 일본어 형태소분석기Api 회화공부 App',
            motive: '시간, 장소, 언제어디서나, 외국어 대화를 하고자 함',
            titleImage: 'pj4.jpg',
            skills: [
              'vue.js',
              'vuex',
              'firebase',
              'vueFire',
              'vuexFire',
              'Bulma'
            ]
          },
           {
            _id: 4,
            title: '중화요리 레스토랑 홈페이지',
            contents: '프론트앤드 기술을 활용하여, 반응형 웹 구현',
            detail: '음성인식Api + 일본어 형태소분석기Api 회화공부 App',
            motive: '시간, 장소, 언제어디서나, 외국어 대화를 하고자 함',
            titleImage: 'pj2.jpg',
            skills: [
              'JavaScript',
              'HTML',
              'CSS3',
              'jQuery',
              'ajax',
              'node.js'
            ]
          },
        ],
            items: [
          // {

          //   src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          // },
          // {
          //   src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          // },
          // {
          //   src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          // },
          // {
          //   src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          // }
        ],
        // images: {
        //   pront: [
        //     {
        //       src: [
        //         '/pjImgs/doc/img1.png',
        //         '/pjImgs/doc/img2.png',
        //         '/pjImgs/doc/img3.png',
        //         '/pjImgs/doc/img4.png'
        //       ],


        //     }
        //   ]
        // },
         dialog: false,
      }
  },
   methods: {
    detailPj(check){
       console.log(check);

      if(check._id === 1) {
       this.items = [
        { src: '/pjImages/doc/img1.png' },
        { src: '/pjImages/doc/img2.png' },
        { src: '/pjImages/doc/img3.png' },
        { src: '/pjImages/doc/img4.png' },
        ]
      }
      if(check._id === 2) {
       this.items = [
        { src: '/pjImages/iot/img1.png' },
        { src: '/pjImages/iot/img2.png' },
        { src: '/pjImages/iot/img3.png' },
        { src: '/pjImages/iot/img4.png' },
        { src: '/pjImages/iot/img5.png' },
        { src: '/pjImages/iot/img6.png' },

        ]
      }

      if(check._id === 3) {
       this.items = [
        { src: '/pjImages/doc/img1.png' },
        { src: '/pjImages/doc/img2.png' },
        { src: '/pjImages/doc/img3.png' },
        { src: '/pjImages/doc/img4.png' },
        { src: '/pjImages/pront/img1.png' },
        ]
      }

      if(check._id === 4) {
       this.items = [
        { src: '/pjImages/pront/img2.png' },
        { src: '/pjImages/pront/img3.png' },
        { src: '/pjImages/pront/img4.png' },
        { src: '/pjImages/pront/img5.png' },
        ]
      }

       this.dialog = true
     }
  }


}
</script>

<style>



</style>