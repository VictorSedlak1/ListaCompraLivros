<script setup>
    import { carrinho, removerItemCarrinho, atualizaQuantidadeItem } from '@/_data/carrinho.js'
    function formatarPreco(preco) {
  return 'R$ ' + preco.toFixed(2).replace('.', ',')
}

</script>
<template>

    <div class="carrinho">
      <h2>Meu carrinho</h2>
      <div class="wrap-carrinho">
        <p v-if="carrinho.itens.length === 0">Seu carrinho está vazio</p>
        <div v-else>
          <div class="item-carrinho" v-for="(item, index) in carrinho.itens" :key="index">
            <div class="info-livro">
              <div class="imagem-livro">
                <img :src="item.img" class="icon-capa-livro" />
              </div>
              <div class="detalhes-livro">
                <div>
                  <p>{{ item.title }}</p>
                  <p class="info-livro-preco">{{ formatarPreco(item.price) }}/un</p>
                </div>
                <div>
                  <p>
                    Quantidade:
                    <input
                      type="number"
                      v-model="item.quantidade"
                      @change="atualizaQuantidadeItem(item)"
                      min="1"
                    />
                  </p>
                  <button @click="removerItemCarrinho(item)">&#128465;</button>
                  <p>Total: {{ formatarPreco(item.total) }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <p class="carrinho-total">Total: {{ formatarPreco(carrinho.total) }}</p>
      </div>
    </div>
</template>