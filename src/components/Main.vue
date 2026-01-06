<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import Markdown from './sections/Markdown.vue'
import BibTeX from './sections/BibTeX.vue'
import Table from './sections/Table.vue'

export default {
  components: {
    Title,
    Abstract,
    Markdown,
    BibTeX,
    Table,
  }
}
</script>

<template>
  <Title/>
  <Abstract/>
  <Markdown/>
  <Table/>
  <BibTeX/>
</template>