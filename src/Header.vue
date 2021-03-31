<template>
  <div>
    <b-modal id="takip" centered hide-footer title="Bizi takip edin" header-text-variant="dark">
      <b-form @submit="onSubmit">
        <b-form-group>
          <b-input type="email" v-model="email" placeholder="Email: " required></b-input>
        </b-form-group>
        <b-form-group>

          <b-button type="submit" block variant="primary">Kaydol</b-button>
        </b-form-group>

      </b-form>

    </b-modal>
    <b-navbar fixed="top" toggleable="lg" type="dark" variant="dark">
      <b-container fluid="sm">
        <b-navbar-brand href="#">
          <i class="fas fa-dragon"></i> Dolphin Software
        </b-navbar-brand>
        <b-nav-toggle target="nav-collapse"></b-nav-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav class="ml-auto">
            <b-nav-item href="#">
              Home
            </b-nav-item>
            <b-nav-item href="#">
              About
            </b-nav-item>
            <b-nav-item href="#">
              Blog
            </b-nav-item>
            <b-nav-item href="#contact">
              Contact
            </b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
    <div class="bg-info text-center text-white py-2" style="margin-top: 56px">
      <a v-b-modal.takip href="#takip" class="text-decoration-none text-white">
        Ürün indirimleri için takipte kalın.
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return {
      email: '',
    }
  },
  methods: {
    onSubmit(event){
      alert(this.email)
    }
  },
  created() {
  }
}
</script>

<style scoped lang="scss">
.container {
  margin: 0;
  display: flex;
  justify-content: space-between;
}
</style>
