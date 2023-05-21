<template>
    <section class="items">
      <h1 class="myBooks">Meus livros</h1>
      <div class="noBooks" v-if="books == 0">
            <h1>Você não tem livros...</h1>
            <img src="../../public/images/sad-face.png"/>
          </div>
      <div v-else class="row">
        <div class="col2">
          
          <div  class="items2" v-for="book in books" :key="book.id">
            <div class="card">
              <img v-bind:src="book.image">
              <h2>{{book.name}}</h2>
              <p>{{book.author}}</p>
              <p class="price" v-if="book.price > 0">R$ {{ book.price }}</p>
              <p class="price" v-else>Para doação</p>
              <button type="button" class="button_form edit_button">Editar</button>
              <button type="button" class="button_form delete_button" @click.prevent="deleteBook(book.id, book.name)">Deletar</button>
            </div>
          </div>
        </div>
      </div>
      <button type="button" class="addBook" @click.prevent="CB_ModalVisible = true">Adicionar livro</button>
      <CreateBookModal 
      v-if="CB_ModalVisible"
      @close="closeCB_Modal"
      />
    </section>
    
    

</template>

<script>

import CreateBookModal from '../components/Modals/CreateBookModal.vue';

export default {
    name: "books",

    components: {
      CreateBookModal
    },
    data() {
      return {
        CB_ModalVisible: false,
        books: null
      }
    },
    
    methods:{
      async getBooks() {
        const API_URL = "http://localhost:8080/";
        const req = await fetch(API_URL + 'book');
        const data = await req.json();

        console.log(data);

        if (data == []) {
          this.books = 0;
        } else {
          this.books=data;
        }
      },

      async deleteBook(id, name) {

        if(!confirm(`Deseja mesmo deletar o livro ${name}?`)){
        return;
      }
        const API_URL = "http://localhost:8080/";

        const req = await fetch(API_URL + `book/delete/${id}`, {
          method: 'DELETE',
          headers: { 
            "Content-Type" : "application/json" 
          },
        }
      );

      const res = await req;
      console.log(res);

      alert("Livro deletado!");
      
      window.location.reload()
    
      },

      showCB_Modal() {
        this.CB_ModalVisible = true;
      },

      closeCB_Modal() {
        this.CB_ModalVisible = false;
        window.location.reload()
      }
    },
    mounted() {
      this.getBooks();
      
    }
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;1,500;1,700;1,900&display=swap');

.button_form {
  margin-right: 20px;
  text-align: center;
  border-radius: 20px;
  color: white;
  width: 80px;
  max-width: 80px;
  height: 50px;
  cursor: pointer;
}

.delete_button {
    background-color: #ff3c3c;
  }

.delete_button:hover {
  background-color: #ff9a9a;
}

.edit_button {
    background-color: #0600c2;
  }

.edit_button:hover {
    background-color: #5a55ff;
  }

.myBooks {
  width: 100%;
  color: rgb(0, 0, 0);
  background-color: rgb(255, 224, 48);
}

.noBooks {
  display:flex;
  align-items: center;
  flex-direction: column;
}

.addBook {
  border: 1px solid black;
  background-color: rgb(8, 158, 0);
  margin-top: 50px;
  color: white;
  cursor: pointer;
  width: 200px;
  height: 50px;
  font-size: 20px;
  border-radius: 20px;
  text-decoration: none;
  font-family: 'Montserrat';
}

.addBook:hover {
  background-color: rgb(0, 255, 55);
}

section {
  margin:0;
  padding: 0;
  font-family: "Montserrat";
  background-color: whitesmoke;
  overflow-x: hidden;
  scroll-behavior: none;
  scroll-snap-type: none;
}

.items {
  margin-top: 0;
}
-webkit-scrollbar-track { background-color: #ffffff; } ::-webkit-scrollbar { width: 6px; background: #6184bb; } 

::-webkit-scrollbar-thumb { background: #1B3764; }

.items {
  margin: 7% 10% 10% 10%;
}

.row {
  display: flex;
  flex-direction: row;
}

.col {
  width: 10%;
  margin-right: 40px;
  background: whitesmoke;
  padding: 30px;
  position: fixed;
  left: 0px;
  top: 100px;
}

.col2 {
  padding-left: 100px;
}

section h1 {
  font-size: 50px;
  text-align: center;
}

.header-img {
  width: 100%;
  height: 20em;
  object-fit: cover;
}

img {
  border-radius: 10px;
}

.card {
  border-radius: 5%;
  text-align: center;
  max-width: 300px;
  width: 300px;
  height: 700px;
  padding: 10px;
  max-height: 700px;
  background-color: #b8b8b8;
  margin-right: 20px;

}

.card>h3 {
  margin: 0;
  padding-top: 10px;
}

.card>p {
  margin: 0;
  padding: 10px;
  font-size: 15px;
}

.price {
  color: grey;
  font-size: 20px;
}

.items2 {
  display: inline-block;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}


.card>img {
  max-height: 400px;
  object-fit: cover;
  max-width: 250px;
  overflow: hidden;

}

input {
  margin-bottom: 10px;
}

@media (max-width: 1400px) {
  .card {
    max-width: 250px;
  }
}

@media (max-width: 768px) {
  .row {
    flex-direction: column;
  }

  .items {
    margin: 0;
    padding: 0;
  }
  .col2 {
    padding: 0;
  }
}
</style>