<template>
  <GeneratePage/>
</template>

<script lang='ts'>
import { Component, Vue } from 'nuxt-property-decorator'
import GeneratePage from '~/views/GeneratePage.vue'

@Component({
  components: { GeneratePage }
})
export default class IndexPage extends Vue {}
</script>
