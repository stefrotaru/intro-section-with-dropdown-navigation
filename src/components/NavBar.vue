<template>
  <div class="navbar">
    <a href="#" class="navbar__logo">
      <img src="../assets/logo.svg" alt="">
    </a>

    <a href="#menu" class="navbar__menu-btn" @click="showMobileMenu = !showMobileMenu">
      <img src="../assets/icon-menu.svg" alt="">
    </a>

    <div class="paths-wrapper" id="menu" v-show="showMobileMenu">
      <div class="navbar__paths">
        <div class="navbar__paths__features dropdown">
          <button class="dropdown__btn">
            Features
            <i class="fa-caret-down"></i>
          </button>
          <div class="dropdown__content">
            <a href="#">Todo List</a>
            <a href="#">Calendar</a>
            <a href="#">Reminders</a>
            <a href="#">Planning</a>
          </div>
        </div>
        <div class="navbar__paths__company dropdown">
          <button class="dropdown__btn">
            Company
            <i class="fa-caret-down"></i>
          </button>
          <div class="dropdown__content">
            <a href="#">History</a>
            <a href="#">Our Team</a>
            <a href="#">Blog</a>
          </div>
        </div>
        <a href="#">Careers</a>
        <a href="#">About</a>
      </div>

      <div class="navbar__register">
        <button class="login-btn btn">Login</button>
        <button class="register-btn btn">Register</button>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      showMobileMenu: true,
      windowWidth: window.innerWidth
    }
  },

  methods: {  
    onResize() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth > 960) {
        this.showMobileMenu = true
      } else {
        this.showMobileMenu = false
      }
    }
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    })
  },

  beforeUnmount() { 
    window.removeEventListener('resize', this.onResize); 
    window.removeEventListener('scroll', this.onScrollFunction);
  },
}
</script>

<style scoped>
.navbar {
  width: 100%;
  padding: 1.5rem 2rem;
  overflow: hidden;

  display: flex;
  align-items: center;
}
.navbar__logo {
  position: relative;
  top: .3rem;
}

.navbar__menu-btn {
  position: absolute;
  right: 4rem;
  z-index: 3;

  display: none;
}
.paths-wrapper {
  display: flex;
  flex: auto;
}
.navbar__paths {
  padding-inline-start: 3.5rem;

  display: flex;
  gap: 3rem;
  align-items: center;
}
.navbar__paths > a {
  text-decoration: none;
  color: hsl(0, 0%, 41%);
  margin: 0;
  font-size: 16px;
  border: none;
  outline: none;
  align-self: center;
}
.dropdown {
  overflow: hidden;
}

.dropdown .dropdown__btn, .btn {
  font-size: 16px;
  color: hsl(0, 0%, 41%);
  border: none;
  outline: none;
  background-color: inherit;
  cursor: pointer;
  font-family: inherit;
  margin: 0;
}

.dropdown__content {
  display: none;
  position: absolute;
  border-radius: 10px;
  top: 4.5rem;
  background-color: #f9f9f9;
  width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown__content a {
  float: none;
  color: hsl(0, 0%, 41%);
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}
.navbar__paths__features .dropdown__content a:nth-child(1)::before {
  content: url(../assets/icon-todo.svg);
  padding: .5rem;
  position: relative;
  top: .1rem;
}
.navbar__paths__features .dropdown__content a:nth-child(2)::before {
  content: url(../assets/icon-calendar.svg);
  padding: .5rem;
  position: relative;
  top: .1rem;
}
.navbar__paths__features .dropdown__content a:nth-child(3)::before {
  content: url(../assets/icon-reminders.svg);
  padding: .5rem;
  position: relative;
  top: .1rem;
}
.navbar__paths__features .dropdown__content a:nth-child(4)::before {
  content: url(../assets/icon-planning.svg);
  padding: .5rem;
  position: relative;
  top: .1rem;
}
.dropdown__content a:hover {
  color: hsl(0, 0%, 8%);
}
.dropdown:hover .dropdown__content {
  display: block;
}
.navbar__register {
  margin-left: auto;

  display: flex;
  gap: 3rem;
}
.register-btn {
  border: .1rem solid hsl(0, 0%, 41%);
  border-radius: .75rem;
  padding: .7rem 1.2rem;
}
.register-btn:hover {
  border: .15rem solid hsl(0, 0%, 8%);;
}
.navbar__paths > a:hover, .dropdown__btn:hover, .btn:hover {
  color: hsl(0, 0%, 8%);
}

i {
  content: url(../assets/icon-arrow-down.svg);
  position: relative;
  bottom: 2px;
}
.dropdown:hover i {
  content: url(../assets/icon-arrow-up.svg);
}

@media (max-width: 960px) {
  .navbar {
    padding: 1rem 1rem
  }
  .navbar__menu-btn {
    right: 1rem;
  }
  .paths-wrapper {
    width: 250px;
    height: 100vh;
    padding-block-start: 5rem;
    padding-inline: 1.5rem;
    position: absolute;
    right: 0;
    top: 0;
    z-index: 2;

    flex-direction: column;
    background-color: hsl(0, 0%, 98%);
  }

  .navbar__menu-btn {
    display: block;
  }

  .navbar__paths {
    padding-inline-start: unset;

    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1.5rem;
  }
  .navbar__paths > a {
    align-self: flex-start;
  }

  .navbar__register {
    margin-block-start: 3rem;
    margin-left: unset;

    align-self: center;
    flex-direction: column;
    gap: .9rem;
  }
  .dropdown__content {
    position: relative;
    border-radius: 10px;
    top: 1rem;
    background-color: transparent;
    width: unset;
    box-shadow: unset;
    z-index: 1;
  }
  .register-btn {
    padding: .6rem 4rem;
  }
}
</style>
