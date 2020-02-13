<template>
  <div class="background">  
    <nav>
      <ul>
        <li         
          v-for="link in links" 
          :key="link.id"
        >
          <n-link :to="link.uri">
            {{ link.title }}
          </n-link>
        </li>
      </ul>
      <button 
        class="button--green" 
        @click="greet"
      >
        Hello
      </button>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  data: () => {
    return {
      counter: 0,
      links: [
        {
          id: 1,
          title: 'Home Page',
          uri: '/'
        },
        {
          id: 2,
          title: 'About Page',
          uri: '/about'
        }
      ]
    }
  },
  methods: {
    greet: function() {
      console.log('hello')
    }
  }
}
</script>

<style>
.background {
  position: relative;
}

.background::after {
  content: '';
  position: absolute;
  background-image: linear-gradient(
    to right top,
    rgba(102, 204, 204, 0.25),
    rgba(249, 85, 132, 0.25),
    rgba(248, 155, 14, 0.25)
  );
  background-color: rgb(30, 39, 45);
  height: 100vh;
  z-index: -2;
  position: absolute;
  width: 100vw;
}

ul {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  align-items: center;
  padding: 0;
  position: fixed;
  height: 100px;
  width: 100vw;
  background: #000;
}

li {
  display: flex;
  justify-content: center;
}

li a {
  color: #fff;
}

.button--green {
  position: absolute;
  top: 50%;
  left: 50%;
}
</style>
