<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Figures from './sections/Figures.vue'
import Markdown from './sections/Markdown.vue'
import BibTeX from './sections/BibTeX.vue'
import Table from './sections/Table.vue'

export default {
  components: {
    Title,
    Abstract,
    Figures,
    Markdown,
    BibTeX,
    Table,
  }
}
</script>

<template>
  <Title/>
  <Abstract/>
  <Figures/>
  <Markdown/>
  <Table/>
  <BibTeX/>
</template>