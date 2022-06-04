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
  width: 80%;
  margin: auto;
}

#cardContainer {
  display: flex;
  height: 20%;
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
      <p id="name">Joseph Sawaya</p>
      <p>
        Welcome to my website.<br/><br/>
        I'm a soon to be fourth year Computer Engineering student at the University of Toronto.<br/><br/>
        Since May 2021, I have been doing a 16-month internship at Red Hat as an open source software developer intern.<br/>
      </p>
      <p>
        These are the various projects I have contributed to for my internship:
      </p>
      <ul>
        <li v-for="(project, index) in projects" :key="index">
          <a v-bind:href="project['url']">{{ project["name"] }}</a>
          and
          <a v-bind:href="project['url'] + query"> my contribution</a>
        </li>
      </ul>
      <p>
        I also do open-source development for fun outside of work here are some other projects I have worked on:
      </p>
      <div id="cardContainer">
        <card v-for="(project, index) in ownprojects" :key="index" :name="project['name']" :url="project['url']" :para="project['para']"/>
      </div>
      <p>
        My biggest interests related to software include cloud-native development and distributed systems, but in general I like anything software related.<br/><br/>
        Outside of work, I enjoy playing soccer, trying out new food, and reading books, specifically those about productivity and self-improvement.<br/>
      </p>
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
        { name: "FetchIt", url: "https://github.com/containers/fetchit" },
      ],
      query: "/pulls?q=author%3Ajosephsawaya+",
      ownprojects: [
        { 
          name: "Discord soundboard bot",
          url: "https://github.com/josephsawaya/better-disc-sound-bot",
          para: "A Discord bot that lets user upload sounds and play them on command. Made in python using discord.py."
        },
      ],
    };
  },
  head() {
    return {
      title: "Joseph Sawaya",
    };
  },
};
</script>
