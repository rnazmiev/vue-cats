<template>
  <div class="wrapper">
    <div class="item" 
         v-for="item in items" 
         :key="item.id"
         @click="$router.push({ name: 'about', params: { id: item.id } })">
      <img alt="Vue logo" :src="require(`../assets/${item.link}.jpg`)">
      <div class="icon-box" @click.stop="addLike(item)">
        <svg  viewBox="0 0 14 12" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path :class="{liked:item.like}" d="M10.5 0.000120477C12.5988 0.0108192 13.9898 1.78957 14 3.98706C14 8.01306 7.00002 12 7.00002 12C7.00002 12 0 7.95444 0 3.98706C0 1.78515 1.39688 0.000120477 3.5 0.000120477C4.78739 -0.0103912 5.83333 0.6 7.00002 1.79813C8.16667 0.6 9.21432 -0.00313402 10.5 0.000120477Z" fill="#000"/>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
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
      ]
    }
  },
  methods: {
    addLike(i) {
      i.like = !i.like
    }
  }
}
</script>

<style>
  .wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  .item {
    position: relative;
    border: 1px solid #ccc;
    padding: 3px;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0px 10px 10px 0px;
    width: 100%;
    max-width: 300px;
  }
  .item .icon-box {
    position: absolute;
    bottom: 10px;
    right: 10px;
    display: flex;
    align-items: center;
    padding: 5px;
    cursor: pointer;
  }
  .icon-box svg {
    width: 30px;
  }
  .icon-box svg .liked {
    fill: #42b983;
  }
  .item img {
    width: 100%;
    border-radius: 15px;
  }
</style>
