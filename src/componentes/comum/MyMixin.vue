<script>
import gql from "graphql-tag"

export default {
  methods: {
    obterPerfis() {
      this.$api
        .query({
          query: gql`
            {
              perfis {
                id
                rotulo
              }
            }
          `
        })
        .then(resultado => {
          this.perfis = resultado.data.perfis
          this.erros = null
        })
        .catch(e => {
          this.erros = e
        })
    }
  }
}
</script>

<style></style>
