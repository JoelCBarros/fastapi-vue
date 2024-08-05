<template>
  <section>
    <div v-if="showMessage" class="alert alert-danger" role="alert">{{ message }}</div>
    <form @submit.prevent="submit">
      <div class="mb-3">
        <label for="username" class="form-label">Username:</label>
        <input required type="text" name="username" v-model="form.username" class="form-control" />
      </div>
      <div class="mb-3">
        <label for="password" class="form-label">Password:</label>
        <input  required type="password" name="password" v-model="form.password" class="form-control" />
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </section>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  name: 'Login',
  data() {
    return {
      form: {
        username: '',
        password:'',
      },
      message: '',
      showMessage: false,
    };
  },
  methods: {
    ...mapActions(['logIn']),
    async submit() {
      const User = new FormData();
      User.append('username', this.form.username);
      User.append('password', this.form.password);
      try {
        await this.logIn(User)
        this.$router.push('/dashboard');
      } catch (error) {
        console.error(error);
        this.message = 'Usuario ou Senha inválidos!';
        this.showMessage = true;
      }
    }
  }
}

</script>

