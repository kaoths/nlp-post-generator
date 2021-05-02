<template>
<!--  <v-container fluid>-->
<dvi class="d-flex flex-column">
  <v-textarea
    solo
    label="Input title"
    v-model='inputText'
  />
  <v-btn @click='perform'>Generate</v-btn>
  <v-textarea
    solo
    label='Generated text shown here'
    v-model="generatedText"

  />
</dvi>

<!--  </v-container>-->
</template>

<script lang='ts'>
import { Component, Vue } from 'nuxt-property-decorator'

@Component
export default class GeneratePage extends Vue {
  private inputText = ''
  private generatedText = ''
  async perform() {
    const { data } = await this.$axios.get('https://jsonplaceholder.typicode.com/posts/11')
    this.generatedText = data.body
  }
}
</script>

<style scoped>

</style>
