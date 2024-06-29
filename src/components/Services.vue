<script setup>
const items = [
  {
    icon: 'analytics',
    title: 'Data Analysis',
    items: [
      'Data cleaning and pre-processing',
      'Exploratory data analysis',
      'Statistical analysis',
      'Data visualisation'
    ]
  },
  {
    icon: 'dataset',
    title: 'Data Engineering',
    items: [
      'Data warehousing',
      'ETL processes',
      'Database management',
      'Data pipeline automation'
    ]
  },
  {
    icon: 'science',
    title: 'Data science',
    items: [
      'Predictive modelling',
      'Machine learning',
      'AI and advanced analytics',
      'Business intelligence'
    ]
  },
  {
    icon: 'code',
    title: 'Software engineering',
    items: ['Web design', 'Mobile apps', 'Custom software', 'AI integration']
  }
]
</script>

<template>
  <section id="services" class="services">
    <h2>Services</h2>
    <p class="byline">
      Whatever your data and software needs, we'll work with you to create a
      robust, scalable and accurate solution.
    </p>
    <div class="wrapper">
      <div
        v-for="item in items"
        :key="item.title"
        class="card animate__animated animate__bounce"
      >
        <div class="card-icon">
          <span class="material-icons">{{ item.icon }}</span>
        </div>
        <div class="card-title">{{ item.title }}</div>
        <div class="card-content">
          <ul>
            <li v-for="subitem in item.items" :key="subitem">
              <span class="material-icons">check</span> {{ subitem }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
h2 {
  font-size: 40px;
  margin-bottom: 16px;
}

.byline {
  color: var(--c-text-2);
  font-weight: bold;
  margin-bottom: 32px;
}

.wrapper {
  display: flex;
  align-items: start;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.card {
  box-sizing: border-box;
  width: 280px;
  border-radius: 8px;
  background-color: var(--c-background-2);
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 1rem;
}

.card-icon .material-icons {
  font-size: 48px;
  color: var(--c-aqua);
}

.card-title {
  font-size: 22px;
  font-weight: 500;
}

.card-content ul {
  padding: 0;
  margin: 0;
}

.card-content li {
  padding: 0;
  margin-bottom: 1rem;
  list-style: none;
  display: flex;
  align-items: center;
  gap: 1rem;
}

li .material-icons {
  font-size: 20px;
}
</style>
