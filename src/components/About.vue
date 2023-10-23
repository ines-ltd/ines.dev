<template>
  <section id="about">
    <div class="container">
      <p class="material-icons">waving_hand</p>
      <p>ines.dev is a small team of seasoned engineers</p>
      <p class="material-icons">favorite</p>
      <p>We develop software and data solutions that people love</p>
      <p class="material-icons">mail</p>
      <p>
        <a href="mailto:sh@ines.dev" subject="Enquiry">sh@ines.dev</a>
      </p>
    </div>
  </section>
</template>

<style scoped>
#about {
  background: linear-gradient(hsl(180, 100%, 15.1%), hsl(180, 100%, 25%));
  display: grid;
  place-content: center;
  text-align: center;
}

.container {
  border-radius: 10px;
  border: solid 2px var(--c-text);
  padding: 3rem;
  box-shadow: 0px 0px 100px var(--c-text);
  background-color: var(--c-background);
}

p {
  max-width: 15rem;
}
</style>
