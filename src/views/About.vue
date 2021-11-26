<template>
  <div class="about"> 
    <div v-for="item in items" :key="item.id">
      <div v-if="item.id == catId">
        <img alt="Vue logo" :src="require(`../assets/${item.link}.jpg`)">
      </div>
    </div>
    <div class="comment">
      <span>Комментарии:</span>
      <textarea v-model="message"></textarea>
      <button @click="add">Добавить</button>
      <p v-for="comment in comments" :key="comment">
        {{ comment }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      catId: this.$route.params.id,
      items: [
        {id: 1, link: 'cat1', like: false},
        {id: 2, link: 'cat2', like: false},
        {id: 3, link: 'cat3', like: false},
        {id: 4, link: 'cat4', like: false},
        {id: 5, link: 'cat5', like: false},
        {id: 6, link: 'cat1', like: false},
        {id: 7, link: 'cat2', like: false},
        {id: 8, link: 'cat3', like: false},
        {id: 9, link: 'cat4', like: false},
        {id: 10, link: 'cat5', like: false},
        {id: 11, link: 'cat1', like: false},
        {id: 12, link: 'cat2', like: false},
        {id: 13, link: 'cat3', like: false},
        {id: 14, link: 'cat4', like: false},
        {id: 15, link: 'cat5', like: false},
        {id: 16, link: 'cat1', like: false},
        {id: 17, link: 'cat2', like: false},
        {id: 18, link: 'cat3', like: false},
        {id: 19, link: 'cat4', like: false},
        {id: 20, link: 'cat5', like: false}
      ],
      message: '',
      comments: ['Здорово', 'класс']
    }
  },

  methods:{
    add(){
      this.comments.push(this.message)
      this.message = ''
    }
  },

}
</script>

<style>
  .about {
    width: 50%;
  }
  .about img {
    width: 100%;
    border-radius: 15px;
  }
  .comment {
    padding-top: 50px;
  }
  span {
    display: block;
    padding-bottom: 10px;
    font-size: 30px;
  }
  textarea {
    resize: none;
    width: 50%;
    height: 140px;
    font-size: 20px;
  }
  button {
    display: block;
  }
</style>