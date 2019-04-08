<template>
  <v-timeline>
    <v-timeline-item
      v-for="(year, i) in years"
      :key="i"
      :color="year.color"
      small
    >
      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold ${year.color}--text`"
          v-text="year.year"
        ></span>
      </template>
      <div class="py-3">
        <h2 :class="`headline font-weight-light mb-3 ${year.color}--text`">{{year.title}}</h2>
        <div>
          {{year.contents}}
        </div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>


<script>
  export default {
    data: () => ({
      years: [
        {
          color: 'cyan',
          year: '2003',
          title: '명지전문대학(전기과)',
          contents: '전기 전공과목과, c++, 데이터통신 관련 지식을 습득'
        },
        {
          color: 'green',
          year: '2008',
          title: '유진로봇 지나월드(코스탁 상장사)',
          contents: '영업직무를 맡아 매출,재고 관리와 ERP, 회계업무, 직영점 관리 등을 습득 '
        },
        {
          color: 'pink',
          year: '2010',
          title: '리레코코리아(프랑스회사 사무용품 취급)',
          contents: '법인영업팀 마포지역 담당하여, 신규 거래처 발굴 및 고객관리 컨설턴트 수행'
        },
        {
          color: 'amber',
          year: '2011',
          title: '캐논코리아 비즈니스 솔루션',
          contents: '총무팀에서 구매업무 및 사옥(캐논타워) 관리 → 서비스지원팀에서 스캐너장비 기술 엔지니어로 영업지원 및 클레임 처리 수행'
        },
        {
          color: 'orange',
          year: '2016',
          title: '한국무역협회 IT마스터',
          contents: '일본 취업 과정(JAVA개발자 양성) 수료 / 정보처리산업기사 취득'
        },
        {
          color: 'deep-orange',
          year: '2018',
          title: '테크와이드(IOT 스타트업)',
          contents: '온도/진동 감지 센서 제작(하드웨어) 및 솔루션(웹/앱) 개발 및 서포트 엔지니어 수행'
        },
        {
          color: 'brown',
          year: '2019',
          title: '꾹앤락(쇼핑몰)',
          contents: '제조, 재고 및 사이트 관리 수행'
        }
      ]
    })
  }
</script>