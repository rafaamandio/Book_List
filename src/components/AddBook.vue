<script setup>
import { reactive } from "vue";

const newBook = reactive({
  title: "",
  cover: "",
  isRead: false,
  isbn: "",
  author: "",
});

</script>

<template>
  <div>
    <h1>📖 Adicionar Livro</h1>

    <div class="header-btns">
      <button class="btn" @click="$emit('closeAddBook')">Fechar x</button>
    </div>

    <form class="add-form">
      <div class="form-control">
        <label>Título</label>
        <input 
          type="text" 
          name="text" 
          placeholder="Adicione o título" 
          v-model="newBook.title"
          required
        />
      </div>
      <div class="form-control">
        <label>Capa</label>
        <input
          type="text"
          name="cover"
          placeholder="Adicione o link da imagem de capa"
          v-model="newBook.cover"
          required
        />
      </div>
      <div class="form-control">
        <label>Autor</label>
        <input 
          type="text" 
          name="author" 
          placeholder="Adicione o autor"
          v-model="newBook.author" 
          required
          />
      </div>
      <div class="form-control">
        <label>ISBN#</label>
        <input 
          type="text" 
          name="isbn" 
          placeholder="Adicione o ISBN"
          v-model="newBook.isbn" 
          required
          />
      </div>
      <div class="form-control form-control-check">
        <input 
          type="checkbox" 
          name="readIt" 
          id="readIt"
          v-model="newBook.isRead" 
          required
          />
        <label for="readIt">Já li o livro</label>
      </div>

      <button @click.prevent="$emit('addBook', newBook)" type="submit" class="btn btn-block">Salvar livro</button>
    </form>
  </div>
</template>