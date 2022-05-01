<style>
html {
  background: #f4f4f4;
}
</style>

<style scoped>
#container {
  font-family: sans-serif;
  display: flex;
}

#contained {
  width: 95%;
  margin: auto;
}

#name {
  font-size: 1.3em;
}

a {
  text-decoration: none;
  color: #007bff;
}

a:hover {
  color: darkblue;
}
</style>

<template>
  <div id="container">
    <div id="contained">
      <p id="name">Joey Sawaya</p>
      <p>
        Welcome to my new website. I thought my old one wasn't that great,
        <br />but if you're interested in seeing the old source code you can
        find it
        <a href="https://github.com/josephsawaya/portfolio">here</a>
      </p>
      <p>
        You can find my current work
        <a href="https://github.com/josephsawaya?tab=repositories">here</a>
      </p>
      <p>
        I've been working as an intern at Red Hat since May 2021, and worked on
        various projects:
      </p>
      <ul>
        <li v-for="(project, index) in projects" :key="index">
          <a v-bind:href="project['url']">{{ project["name"] }}</a>
          and what
          <a v-bind:href="project['url'] + query"> I worked on</a>
        </li>
      </ul>
      <p>Other than that I don't have much going on for now.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        { name: "Ceph", url: "https://github.com/ceph/ceph" },
        { name: "Rook", url: "https://github.com/rook/rook" },
        { name: "Harpoon", url: "https://github.com/redhat-et/harpoon" },
      ],
      query: "/pulls?q=author%3Ajosephsawaya+",
    };
  },
};
</script>
