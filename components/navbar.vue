<template>
  <div class="navbar flex sb">
    <div class="hidden filter">

    </div>
    <a href="/">
      <img src="@/assets/imgs/logo.svg" alt="">
    </a>
    <ul class="flex sa mainNav">
      <li v-on:click="closeMenu" class="crossBtn absolute">
        <img src="@/assets/imgs/icon-close-menu.svg" alt="">
      </li>
      <li v-if="column.lines" class="navBtn menu" v-for="column in columns">
        <div  class="relative">
          <p>{{ column.nom }}
            <i class="fa-solid fa-angle-down dropClosed"></i>
            <i class="fa-solid fa-angle-up dropOpen"></i>
          </p>
          <div class="dropdown absolute" >
            <ul>
              <li v-for="line in column.lines" >
                <a :href="line.href" class="flex"><img class="ddIcon" v-if="line.icon" :src="require(`~/assets/imgs/`+line.icon)" alt=""> <p>{{line.nom}}</p></a>
              </li>
            </ul>
          </div>
        </div>
      </li>
      <li v-else class="navBtn">
        <div>
          <a :href="column.href"><p>{{ column.nom }}</p></a>
        </div>
      </li>

      <li class="loginRegBurger navBtn">
        <a class=""  href="/login"><p>Login</p></a>
      </li>
      <li class="loginRegBurger navBtn">
        <a class="" href="/register"><p>Register</p></a>
      </li>

    </ul>

    <div class="flex rightBtns">
      <a class="navbarRightBtn"  href="/login"><p>Login</p></a>
      <a class="navbarRightBtn" href="/register"><p>Register</p></a>
    </div>

    <div v-on:click="openMenu" class="burger_menu">
      <img src="@/assets/imgs/icon-menu.svg" alt="">
    </div>

  </div>
</template>

<script>
export default {
  name: "navbar",
  data() {
    return{
      columns: [
        {nom: 'Features', lines:[
            {nom:'Todo list',href:'todo',icon:'icon-todo.svg'},
            {nom:'Calendar',href:'calendar',icon:'icon-calendar.svg'},
            {nom:'Reminders',href:'reminders',icon:'icon-reminders.svg'},
            {nom:'Planning',href:'planning',icon:'icon-planning.svg'}
          ]
        },

        {nom: 'Company', lines:[
            {nom:'History',href:'history'},
            {nom:'Our team',href:'team'},
          ]
        },
        {nom: 'Careers', href: 'careers'},
        {nom: 'About', href: 'about'},
      ],
      isHovering: false
    }
  },
  methods: {
    openMenu() {
      console.log('click')
      const menuScreen = document.querySelector('.mainNav')
      const filter = document.querySelector('.filter')
      menuScreen.style.display = 'flex'
      filter.style.display = 'block'
    },
    closeMenu() {
      console.log('click')
      const menuScreen = document.querySelector('.mainNav')
      const filter = document.querySelector('.filter')
      menuScreen.style.display = 'none'
      filter.style.display = 'none'
    }
  }
}
</script>

<style scoped>
.navbar {
  padding: 40px;
  color: var(--mediumGray);
}

.navbar img {
  vertical-align:middle
}
.navbar p:hover {
  color: var(--almostBlack);
}
.crossBtn {
  display: none;
  height: 30px;
  width:30px;
  margin: 10px;
  justify-content: right;
  right: 60px;
  cursor: pointer;
}
.dropdown {
  display: none;
  top: 25px;
  left: 50%;
  transform: translate(-50%, 0);
  box-shadow: -6px 6px 14px -1px rgba(0,0,0,0.27);
  background-color: var(--almostWhite);
  padding: 5px 20px;
  width: 200px;
  border-radius: 8px;
}
.dropdown .ddIcon {
  height: 20px;
  width: 20px;
  margin-right: 10px;
}
.dropOpen {
  display: none;
}

li.menu:nth-of-type(2) div .dropdown {
  left: 0;
}
li.menu:nth-of-type(3) div .dropdown {
  left: 100%;
}

li:hover .dropdown {
  display: block;
}
li:hover .dropOpen {
  display: inline;
}
li:hover .dropClosed {
  display: none;
}

.navbarRightBtn, .navBtn {
  padding: 0 30px;
  text-align: center;
}
.navbarRightBtn:nth-of-type(2) {
  outline: solid 2px var(--mediumGray);
  border-radius: 10px;
}
.navbarRightBtn:nth-of-type(2):hover {
  outline: solid 2px var(--almostBlack);
}
.loginRegBurger {
  display: none;
  text-align: center!important;
  margin-top: 20px;
}
.loginRegBurger:last-of-type p {
  outline: solid 2px var(--mediumGray);
  border-radius: 10px;
  padding: 10px 30px;
  display: inline;

}
/*Burger menu*/

.burger_menu {
  display: none;
  cursor: pointer;
}
@media screen and (max-width: 975px) {
  .filter {
    margin: -40px;
    height: 100vh;
    width: 40vw;
    position: fixed;
    display: block;
    background-color: rgba(0,0,0,0.5);
  }
  .filter, .mainNav {
    display: none;
  }
  .burger_menu {
    display: block;
  }
  .crossBtn {
    display: block;
  }
  .loginRegBurger {
    display: inline-block;
    padding: 0;
  }

  .rightBtns {
    display: none;
  }
  .mainNav {
    padding-top: 25px;
    position: fixed;
    background-color: var(--almostWhite);
    height: 100vh;
    width: 80vw;
    margin: -40px -40px -40px 20vw;
    flex-direction: column;
    justify-content: normal;
  }
  .mainNav * {
    margin-bottom: 5px;
  }
  .mainNav>li:nth-child(2) {
    margin-top: 50px;
  }

  .dropdown {
    position: relative;
    top: 0;
    box-shadow: none;
    left: 0!important;
    transform: none;
  }
  .navbarRightBtn, .navBtn {
    text-align: left;

  }
}




</style>
