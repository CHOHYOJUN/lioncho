<template>
  <v-data-table
    :headers="headers"
    :items="skillList"
    hide-actions
    class="elevation-1"
    expand
  >
    <template
    v-slot:items="props"
    >
        <tr
        class="text-md-center"
        v-for="javaSkill in props.item.javaSkillList" :key="javaSkill">
        {{javaSkill}}
        </tr>
        <td
        >
            <tr
            v-for="jsSkill in props.item.jsSkillList" :key="jsSkill">{{jsSkill}}</tr>
        </td>
         <td>
            <tr
            v-for="dbSkill in props.item.dbSkillList" :key="dbSkill">{{dbSkill}}</tr>
        </td>

    </template>


  </v-data-table>
</template>

<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'JAVA',
            value: 'javaSkillList',
            align: 'center',
            sortable: false,
          },
          {
            text: 'JavaScript',
            value: 'jsSkillList',
            align: 'center',
            sortable: false,
          },
          {
            text: 'DB',
            value: 'dbSkillList',
            align: 'center',
            sortable: false,
          }
        ],
        skillList: [
            {
              javaSkillList: [
                'JSP','Spring','3'
              ],
              jsSkillList: [
                '4','5','6'
              ],
              dbSkillList: [
                '7','8','9'
              ]
            }
        ],
      }
    }
  }
</script>