<script setup>
import Login from './components/Login.vue'

</script>


<template>
  <header>
    <title> Página de Login </title>
  </header>

  <main>
    <Login/>
  </main>
</template>

<script>
import {Cytomine, User, ProjectCollection} from "cytomine-client"; // required only if used as an NPM module
// Initialize connection (replace CYTOMINE_URL by an appropriate value, e.g. "http://demo.cytomine.coop")
let cytomine = new Cytomine("http://cytominedev");

// Login into Cytomine
await cytomine.login("admin", "admin123"); // or await Cytomine.instance.login("username", "password");

// Fetch the connected user, and log "Hello " followed by its username in the console
let user = await User.fetchCurrent();
console.log("Hello " + user.username);

// Fetch the projects available to the current user and log their names in the console
let projects = await ProjectCollection.fetchAll();
console.log("You have access to these projects:");
for(let project of projects) {
     console.log(project.name);
}

</script>

<style scoped>

body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
