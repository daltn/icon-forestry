<template>
  <Layout>
    <div class="container">
      <section>
        <h1 class="title">CAPABILITIES</h1>
        <ul class="grid-two">
          <li class="services" v-for="(paragraph, serviceName) in services" :key="serviceName">
            <h3>
              <g-link :to="formatUrl(serviceName)">
                {{
                formatServiceName(serviceName)
                }}
              </g-link>
            </h3>
            <p>{{ paragraph }}</p>
          </li>
        </ul>
      </section>
    </div>
  </Layout>
</template>

<script>
import formatServiceName from "@/components/utility-funcs/formatServiceName.js";
import formatUrl from "@/components/utility-funcs/formatUrl.js";

export default {
  data() {
    return {
      services: require("../../data/capabilities.json")
    };
  },
  methods: {
    formatServiceName,
    formatUrl
  }
};
</script>

<style scoped>
li {
  margin: 0rem;
  padding-left: 0.5rem;
}
h2 {
  margin: 2rem 0;
}
.grid-four {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 4rem;
  list-style: none;
  padding: 0;
}
.grid-two {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 3rem;
  list-style: none;
  padding: 0;
}
label {
  position: relative;
  bottom: -8px;
  color: var(--color-highlight);
  background-color: var(--color-base);
  border-bottom: 1px solid var(--color-base);
  padding-right: 1rem;
  font-size: 0.8rem;
  font-weight: bold;
  letter-spacing: 0.5px;
}
.small-title {
  color: var(--color-highlight);
  padding-top: 4rem;
}
h3 {
  width: 100%;
  font-size: 3rem;
  border-top: 1px solid var(--color-highlight);
  padding-top: 32px;
  margin-bottom: 1rem;
}
h2 {
  margin-top: 10px;
}
.about-text {
  margin: 0 auto;
  max-width: 100%;
  margin-bottom: 5%;
  font-size: 1.2rem;
}
.title {
  letter-spacing: 2px;
  font-weight: 700;
  padding: 0;
  margin: 4rem 0 2rem;
}
.pink {
  color: var(--color-highlight);
}
img {
  margin-bottom: 1rem;
}
a {
  text-decoration: none;
  transition: all 500ms ease-in;
}
a:hover {
  text-decoration: underline;
  transition: all 500ms ease-in;
}

.services p {
  font-size: 1.2rem;
}

@media (max-width: 800px) {
  .title {
    font-size: 2rem;
  }
  .grid-four {
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 4rem;
  }
  .grid-two {
    grid-template-columns: 1fr;
  }
  .services {
    width: 90%;
  }
  .services p {
    font-size: 1rem;
  }
  .services h3 {
    font-size: 2.5rem;
  }
}
</style>
