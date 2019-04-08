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
       height='100%'
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
            <h3><span class="headline">{{ project.contents }}</span></h3><br>
           <div v-if="project._id===3">
            <a href="https://lioncho-33050.firebaseapp.com" target="_blank">Demo</a></div><br>
            <span>- 제작동기: {{ project.motive }}</span><br>
            <span>- 특징: {{ project.detail }}</span>
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
      </v-card>
    </v-hover>
    </v-flex>
  </v-layout>
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
            contents: '음성인식 + 인공지능',
            detail: '사람음성 -> 문자변환 -> 분석 -> 응답 알고리즘 -> 음성 출력 과정을 앱으로 제작하면 좋겠다고 생각했고, 과거 심심이란 프로그램과 시리 등과 같은 인공지능을 모티브로 제작하였습니다.' ,
            motive: '혼자서도 할 수 있는 회화 앱이 필요해었습니다.',
            titleImage: 'pj1.jpg',
            skills: [
              'JAVA',
              'Struts2',
              'Google음성API',
              'ResponsiveVoiceAPI',
              'Kuromoji Api',
              'Bootstrap',
              'jQuery',
              'oracleDB',
              'myBtis',
              ],
              pjsrc: 'doc'
          },
          {
            _id: 2,
            title: '라이센스 발급 페이지',
            contents: '고객의 base64 암호화 라이센스 발급페이지',
            detail: '관리자의 오프라인 pc에서 생성자에 고객데이터를 넣어 라이센스를 발급하는 과정을 개선해야했고, 현장에서도 전체 라이선스를 파악 해야 했습니다. ',
            motive: '엑셀로 고객라이선스 관리하던 중, 웹 페이지에서 관리 필요성 증가   ',
            titleImage: 'pj3.jpg',
            skills: [
              'JAVA',
              'SpringBoot',
              'MySQL',
              'MyBatis',
              'JSTL',
              'EL',
              'Base64'
            ]
          },
          {
            _id: 3,
            title: 'story board',
            contents: 'vue.js + firebase 활용 url게시판',
            detail: '백앤드 없이, 구글 계정 로그인, 사용자정보, 데이터 저장 기능 구현 가능',
            motive: 'firebase의 auth, cloud, hosting 기능 학습',
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
            detail: '캘린더형태의 예약 화면보다 특별한 예약 기능을 만들고 싶었습니다.',
            motive: '프론트앤드 학습내용 리뷰차원에서 미니프로젝트 진행하였습니다.',
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
         items: [],
         dialog: false,
      }
  },
   methods: {
    detailPj(check){
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
        { src: '/pjImages/firebase/img1.png' },
        { src: '/pjImages/firebase/img2.png' },
        { src: '/pjImages/firebase/img3.png' },
        { src: '/pjImages/firebase/img4.png' },
        { src: '/pjImages/firebase/img5.png' },
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
.v-btn .v-btn__content .v-icon {
    color: red;
}
</style>