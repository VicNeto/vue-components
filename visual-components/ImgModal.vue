<template>
  <div class="container">
    <div class="columns">
      <div 
        v-for="(item,i) in imgItems" 
        :key="i" 
        class="column" 
      >
        <figure class="image is-300x300 has-image-centered" @click="toggleModal(i)">
          <a>
            <img :src="item.image" >
          </a>
        </figure>   
        <p class="title is-5 has-text-centered">{{item.name}}</p> 
        <div class="modal" :class="classModal(i)">
          <div class="modal-background" @click="closeModal"></div>
          <div class="modal-card">
            <header class="modal-card-head">
              <p class="modal-card-title">{{item.title}}</p>
              <button 
                class="delete" 
                aria-label="close" 
                @click="closeModal"
              >
              </button>
            </header>
            <section class="modal-card-body">
              <!-- Content ... -->
              <p class="content has-text-justified">
              {{item.text}}
              </p>
              <ul>
                <li v-for="(elem,i) in item.listItems" :key="i">{{elem}}</li>
              </ul>
            </section>
            <footer class="modal-card-foot">
              <button class="button is-success" @click="closeModal">{{item.buttonLabel}}</button>
            </footer>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
var root = document.getElementsByTagName('html')[0];

export default {
  name: 'ImgModal',
  props: [
    'imgItems'
  ],
  data() {
    return {
      activeModal: null,
    }
  },
  methods: {
    toggleModal: function(i) {
      this.activeModal = i;
      root.classList.add('is-clipped');
    },
    closeModal: function() {
      this.activeModal = null;
      root.classList.remove('is-clipped');
    },
    classModal: function(i) {
      return this.activeModal === i ? 'is-active' : ''
    },
  }
}
</script>

<style scoped>
.has-image-centered {
  margin-left: auto;
  margin-right: auto;
}
</style>
