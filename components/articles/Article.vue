<template lang="pug">
  .card.shadow.bg-body.rounded
    .card-header {{article.title}}
    .actions
        button.btn.btn-danger.btn-sm(@click.prevent="deleteArticle") Delete
    .card-body
      p.card-text {{ isDetails ? article.content : article.content}}
      
</template>

<script>
export default {
  methods: {
    async deleteArticle() {
      let res = await this.$axios.delete(`/api/note/${this.article.id}`, {})
      if (res.data !== null && res.status == 200) {
        this.isDetails ? this.$router.push('/') : this.$nuxt.refresh()
      } else {
        this.$router.push('/?status=deleteerror')
      }      
    }
  },
  props: {
    isDetails: {
      type: Boolean,
      default: false,
    },
    article: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.btn{
  margin: 2px 2px 2px 2px;
}
.actions button {
  float: right;
  margin: 10px 5px 0px 5px;
}
</style>