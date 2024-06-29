<script setup>
const items = [
  {
    avatar: 'josh.png',
    title: 'Joshua Haines',
    role: 'CEO & Data Lead',
    skills: ['Reporting', 'Databases', 'Machine Learning'],
    description: [
      'Joshua has an extensive track record developing comprehensive data solutions for businesses. His innovative and bespoke strategies boost efficiency, steer critical decisions, and foster a data-driven culture.',
      'Having transformed the data culture at businesses such as BT Openreach and Voneus, Joshua has a proven track record of helping businesses leverage their data to understand problems, achieve goals and beat targets.'
    ],
    email: 'jh@ines.dev',
    mobile: '07777777777'
  },
  {
    avatar: 'simon.jpeg',
    title: 'Simon Haines',
    role: 'Software Engineering Lead',
    skills: ['Web design', 'Mobile apps', 'APIs', 'AI'],
    description: [
      'Simon is a talented developer with decades of experience building software people love to use. Businesses thrive when they have the tools they need, and this is exactly what Simon delivers.',
      'Give your business the edge with personalised dashboards, role-based access, real-time notifications, streamlined workflows, AI powered recommendations, and more.'
    ],
    email: 'sh@ines.dev',
    mobile: '07777777777'
  }
]
</script>

<template>
  <section id="team" class="team">
    <h2>Team</h2>
    <p class="byline">
      An agile team of seasoned experts, based in the UK, ready to build exactly
      what you need.
    </p>
    <div class="wrapper">
      <div v-for="item in items" :key="item.title" class="card">
        <div class="avatar">
          <img class="avatar-image" :src="'/' + item.avatar" alt="" />
        </div>
        <div class="title">{{ item.title }}</div>
        <div class="role">{{ item.role }}</div>
        <div class="skills">
          <div v-for="skill in item.skills" :key="skill" class="skill">
            {{ skill }}
          </div>
        </div>
        <div class="content">
          <p v-for="para in item.description">{{ para }}</p>
        </div>
        <div class="contact">
          <ul>
            <li>
              <span class="material-icons">email</span>
              <a :href="`mailto:${item.email}`">{{ item.email }}</a>
            </li>
            <li>
              <span class="material-icons">phone</span>
              <a :href="`tel:+44${item.mobile.slice(1)}`">{{ item.mobile }}</a>
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
  flex-wrap: wrap;
  gap: 2rem;
  justify-content: center;
}

.card {
  background-color: var(--c-background-2);
  max-width: 480px;
  border-radius: 8px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  box-sizing: border-box;
}

.avatar {
  margin: auto;
  border-radius: 50%;
  overflow: hidden;
  width: 120px;
}

.avatar-image {
  width: 100%;
  aspect-ratio: 1/1;
}

.title {
  text-align: center;
  font-weight: 500;
  font-size: 24px;
}

.role {
  text-align: center;
  font-weight: 500;
}

.skills {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 1rem;
  justify-content: center;
}

.skill {
  background-color: var(--c-aqua);
  color: var(--c-text-inverse);
  font-size: 14px;
  font-weight: 500;
  padding: 6px 12px;
  border-radius: 30px;
  width: auto;
}

.contact ul {
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.contact li {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

li .material-icons {
  color: var(--c-aqua);
  font-size: 20px;
}
</style>
