<template>
  <div class="navbar flex sb">
    <ul class="flex sa">
      <li>
        <a href="/">
          <img src="@/assets/imgs/logo.svg" alt="">
        </a>
      </li>
      <li v-if="column.lines" class="navBtn menu" v-for="column in columns">
        <div  class="relative">
          <p>{{ column.nom }} <i class="fa-solid fa-angle-down"></i></p>
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


    </ul>

    <div class="flex">
      <a class="navbarRightBtn"  href="/login"><p>Login</p></a>
      <a class="navbarRightBtn" href="/register"><p>Register</p></a>
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
}

.menu:first-of-type div .dropdown {
  left: 0;
}
.menu:last-of-type div .dropdown {
  left: 100%;
}

li:hover .dropdown {
  display: block;
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
</style>
