<template>
    <div class="modal-backdrop" @click="closeCB_Modal">
        <div class="modal">
          <header class="modal-header">
            <slot name="header">Tem certeza de que deseja excluir este livro?</slot>
            <button type="button" class="btn-close" @click="close">X</button>
          </header>
    
          <section class="modal-body">
            <slot name="body">
              <form id="bookForm" role="form" method="DELETE" >
                <footer class="modal-footer">
                  <input type="submit" class="button_form delete_button" @click.prevent="deleteBook" value="Excluir"/>
                  <input type="submit" class="button_form cancel_button" @click.prevent="close" value="Cancelar"/>
                </footer>
              </form>
            </slot>
           </section>
        </div>
      </div>
  
</template>

<style scoped>

.button_form {
  justify-content: center;
  background-color: #ff0000;
  border-radius: 20px;
  color: white;
  width: 100%;
  height: 50px;
  cursor: pointer;
}

.delete_button {
    background-color: #ff3c3c;
  }

.delete_button:hover {
  background-color: #ff3c3c;
}

.cancel_button {
    background-color: #69aa00;
  }

.cancel_button:hover {
    background-color: rgb(0, 255, 0);
  }

.modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    
  }

  .modal {
    background: #FFFFFF;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    flex-direction: column;
    width: 60vw;
    height: 60vh;
    display: flex;
  }

  .modal input {
    display: flex;
    align-items: center;
    width: 98%;
    height: 40px;
    border-radius: 10px;
    padding-left: 20px;
    font-size: 12pt;
  }

  .modal-header,
  .modal-footer {
    font-size: 30pt;
    padding: 15px;
    display: flex;
  }

  .modal-header {
    position: relative;
    border-bottom: 1px solid #eeeeee;
    color: #000000;
    height: 200px;
    justify-content: center;
    background-color: rgb(255, 224, 48);
  }

  .modal-footer {
    border-top: 1px solid #eeeeee;
    flex-direction: column;
    justify-content: flex-end;
  }

  .modal-body {
    position: relative;
    padding: 20px 10px;
  }

  .btn-close {
    position: absolute;
    top: 0;
    right: 0;
    border: none;
    font-size: 20px;
    padding: 10px;
    cursor: pointer;
    font-weight: bold;
    color: #4AAE9B;
    background: transparent;
  }

</style>

<script>
export default {
  name: "DeleteBookModal",
  data() {
    return {
        id:0,
        };
    }, 
  methods: {
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
      
    async deleteBook() {

        let id = this.id;

      console.log(id);

      const dataJson = JSON.stringify(data);

      const req = await fetch(`http://localhost:8080/book/delete/${id}`, {
        method: "POST",
        headers: { "Content-Type" : "application/json" },
        body: dataJson
      });

      const res = await req;


      console.log(res);

      if (res.status != 201) {
        alert("Erro: o livro não pode ser criado.")
      } else {
        alert("Livro adicionado!");
      }
      window.location.reload()
      
      },

      close() {
        this.$emit('close');
      }

      }
    }
</script>