<template>
  <v-container>
    <v-row>
      <v-col md="4">
        <OverviewPane></OverviewPane>
      </v-col>
      <v-col md="8">
        <TasksPane></TasksPane>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src
import OverviewPane from '@/components/OverviewPane.vue'
import TasksPane from '@/components/TasksPane.vue'

export default {
  name: 'root',
  mounted: async function () {
    await this.$store.dispatch('fetchCategories')
  },
  components: {
    OverviewPane,
    TasksPane
  }
}
</script>
