<template>
  <div class="user__card">
    <h1>БАБКИ</h1>
    <div class="main-info">
      <img
        class="card__image"
        src="../assets/1603344816_1-p-kris-khemsvort-2.jpg"
      />
      <div class="info">
        <h2>
          {{ getFullNameAuthor }}
        </h2>
        <strong>Бизнес-коуч</strong>
        <ul>
          <li>
            Учу людей делать РЕАЛЬНЫЕ бабки, на себя просто не хватило времени
            X(
          </li>
          <li>Не знаю, что такое "Успешный Успех", но знаю, что нужно ТЕБЕ!</li>
          <li>Пообещал, что побреюсь, когда кого нибудь ОБМАНУ.</li>
        </ul>
      </div>
    </div>
    <p>Участников: {{ users.length }}</p>
    <ul>
      <li v-for="(user, index) in users" :key="index">
        {{ `${index + 1} ${getFullName(user)}` }}
      </li>
    </ul>
   <button type="button" @click="currentPage--">пред.</button>
   <button v-for="page in pages" :key="page" type="button" @click="currentPage = page">{{ page }}</button>
   <button type="button" @click="currentPage++">след.</button>
    <p>Cтраница {{ currentPage }} из {{ pages }}</p>
  </div>
</template>

<script>
export default {
  name: "profileCard",
  data() {
    return {
      firstName: 'Игнатий',
      secondName: 'Иларионович',
      lastName: 'Богатов',
      users: [
        {
          firstName: 'Игнатий',
          secondName: 'Иларионович',
          lastName: 'Богатов'
        },
        {
          firstName: 'Игнатий',
          secondName: 'Иларионович',
          lastName: 'Богатов'
        },
        {
          firstName: 'Игнатий',
          secondName: 'Иларионович',
          lastName: 'Богатов'
        }
      ],
      pages: 3,
      currentPage: 1
   }
  },
  computed: {
    getFullNameAuthor() {
        return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
    }
  },
  methods: {
      getFullName(user) {
          return `${user.firstName} ${user.secondName} ${user.lastName}`
      },
      loadUsers(page) {
        if(this.currentPage > 3) {
          this.currentPage = 1
        } else if(this.currentPage < 1) {
          this.currentPage = 3
        }

        console.log(`Загрузка пользователя: страница ${page}`)
      }
        
  },
  watch: {
    currentPage(page) {
      this.loadUsers(page)
    }
  }
}
</script>

<style>
.user__card {
  padding: 15px;
  border: 1px solid #555;
}

.card__image {
  height: 500px;
  object-fit: cover;
  margin-right: 20px;
}

ul {
  list-style: none;
  padding: 0;
}

.main-info {
  display: flex;
  line-height: 2.1em;
}
button{
  width: 40px;
}
</style>