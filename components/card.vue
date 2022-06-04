<style scoped>
div {
  background-color: #f0f0f0;
  width: 20%;
  padding: 2%;
  transition: 0.4s;
  margin: 2% auto;
  align-self: center;
  border: thin solid #d0d0d0;
}

div:hover {
  transform: scale(1.01);
  box-shadow: 0 2px 5px 0 #d0d0d0;
}

h4 {
  margin: 4% 0;
}

a {
  text-decoration: none;
  color: #007bff;
  transition: 0.6s;
}

a:hover {
  color: darkblue;
}
</style>

<template>
  <div>
    <h4>{{name}}</h4>
    <a v-bind:href="url">Repo</a>
    <p>{{para}}</p>
  </div>
</template>

<script>
export default {
  props: ['name', 'url', 'para']
};
</script>
