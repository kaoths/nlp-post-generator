<template>
  <div class="d-flex flex-column">
    <v-textarea
      solo
      label="Input title"
      v-model='inputText'
    />
    <v-btn color='secondary' @click='generate' class='generate-btn'>Generate</v-btn>
    <v-textarea
      v-for='(text, idx) in generatedTexts' :key='idx'
      solo
      label='Generated text shown here'
      :value='text'
    />
  </div>
</template>

<script lang='ts'>
import { Component, Vue } from 'nuxt-property-decorator'

@Component
export default class GeneratePage extends Vue {
  private inputText = ''
  private generatedTexts: string[] = []
  async generate() {
    const { data } = await this.$axios.post('title_gen', {
      title: this.inputText
    })
    this.generatedTexts = data
  }
}
</script>

<style scoped>
.generate-btn {
  margin-bottom: 16px;
}
</style>
