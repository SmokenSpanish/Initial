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
    <p>Участников: 0</p>
    <ul>
        <li v-for="{users, index} in users" :key="index">
        {{ getFullNameUser(users) }}
        </li>
    </ul>
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
            firstName: 'Иван',
            secondName: 'Иванович',
            lastName: 'Иванов'
          },
          {
            firstName: 'Иван',
            secondName: 'Иванович',
            lastName: 'Иванов'
          },
          {
            firstName: 'Иван',
            secondName: 'Иванович',
            lastName: 'Иванов'
          },
      ]
    };
  },
  computed: {
    getFullNameAuthor() {
        return `${this.firstName} ${this.secondName} ${this.lastName}`.toUpperCase()
    }
  },
  methods: {
      getFullNameUser(user) {
          return user.secondName
      }
  }
};
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
</style>