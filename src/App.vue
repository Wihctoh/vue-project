<script>
export default {
  data() {
    return {
      formData: {
        fio: '',
        email: '',
        password: ''
      }
    }
  },
  methods: {
    sendData() {
      try {
        if (!this.formData.fio || !this.formData.email || !this.formData.password)
          throw new Error('Заполните все поля')

        alert('Успешная регистрация')
      } catch (error) {
        alert(error.message)
      }
    }
  }
}
</script>

<template>
  <div class="flex justify-center m-auto w-4/5">
    <div class="flex items-center flex-col gap-4">
      <h1>Добро пожаловать</h1>

      <input
        v-model="formData.fio"
        type="text"
        placeholder="Введите ФИО"
        class="rounded-3xl pl-2 py-1 outline-none"
      />
      <input
        v-model="formData.email"
        type="text"
        placeholder="Введите email"
        class="rounded-3xl pl-2 py-1 outline-none"
      />
      <input
        v-model="formData.password"
        type="password"
        placeholder="Введите пароль"
        class="rounded-3xl pl-2 py-1 outline-none"
      />

      <button @click="sendData" class="bg-blue-500 rounded-3xl max-w-64 w-full">
        Зарегистрироваться
      </button>
    </div>
  </div>
</template>
