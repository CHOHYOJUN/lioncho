<template>
  <v-container grid-list-md>
    <v-layout
     align-center
    row wrap>
        <v-flex
        xs12
        sm12
        md12
        text-xs-center
        layout
        align-center
        justify-center
      >
        <v-avatar
          size="250"
          class="grey lighten-4"
        >
          <img src="lioncho.jpg" alt="avatar">
        </v-avatar>
      </v-flex>
      <v-flex>

      <v-tabs
        fixed-tabs
        v-model="currentItem"
        color="grey lighten-4"
        slider-color="primary"
        slot="extension"
      >
        <v-tab
          v-for="tabitem in tabItems"
          :key="tabitem"
          :href="'#tab-' + tabitem"
        >
          <h3>{{ tabitem }}</h3>
        </v-tab>
      </v-tabs>

    <v-tabs-items v-model="currentItem">
      <v-tab-item
        v-for="(tabitem, index) in tabItems"
        :key="tabitem"
        :value="'tab-' + tabitem"
      >
        <v-card flat>
          <v-card-text>
            <h1>{{ tabitem }}</h1>
            <template v-if="index===0">
              <MySkill></MySkill>
            </template>
            <template v-if="index===1">
              <MyCore></MyCore>
            </template>
            <template v-if="index===2">
              <Company></Company>
            </template>
            <template v-if="index===3">
              <Etc></Etc>
            </template>
          </v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import MySkill from '@/components/MySkill'
import Company from '@/components/Company'
import Etc from '@/components/Etc'
import MyCore from '@/components/MyCore'

export default {
    data: () => ({
      currentItem: 'tab-Web',
      tabItems: [
        '보유기술', '핵심역량', '경력', '현재 사이트'
      ],
      text: [
        true,
        false,
        '3',
        '4'
      ]
    }),
    components: {
      MySkill, Company, Etc, MyCore
    },
    methods: {

    }
}
</script>
