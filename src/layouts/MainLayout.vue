<template>
  <div>
    <q-layout view="lHh lpr lFf">
      <q-header elevated style="background-color: black;height: 70px;" class="flex glossy">
        <q-toolbar>
          <!-- <q-btn flat round dense icon="menu" class="desktop-only" /> -->
          <q-avatar class="q-ml-md">
            <img
              src="https://static.gameloop.com/img/1326a436dede55f1adce87c24b8e4930.png?imageMogr2/thumbnail/172.8x172.8/format/webp">
          </q-avatar>
          <q-toolbar-title class="q-mt-sm">
            <img src="https://tamil.examsdaily.in/wp-content/uploads/2022/01/examsdaily-logo-png-300x82-1.png" height="40"
              width="160">
          </q-toolbar-title>
          <q-tabs v-model="tab" class="flex flex-between desktop-only q-mr-xl">
            <q-tab name="home" label="Home" />
            <q-tab name="about us" label="About Us" />
            <q-tab name="testimonals" label="Limitations" />
            <q-tab name="contact us" label="Contact Us" />
          </q-tabs>
          <q-btn flat round dense icon="menu" aria-label="Menu" @click="toggleRightDrawer" class="q-mr-sm mobile-only" />
        </q-toolbar>


      </q-header>

      <q-page-container>
        <RouterView />
      </q-page-container>
      <footer style="margin-top: 100px;background-color: black;" id="footer" class="q-pa-xl glossy aos-init aos-animate"
        data-aos="fade-up">
        <div class="container aos-init aos-animate" data-aos="fade-up">
          <div>
            <hr class="bg-warning no-border hr">
            <h1 class="text-center text-white aos-init aos-animate no-margin" data-aos="fade-up"
              style="font-weight: bolder;font-size: 6vw;line-height: 7vw;">Contact Us</h1>
          </div>
          <hr class="q-mt-xl no-border" style="height: 2px;background-color: rgb(162, 162, 162);">
          <div class="row q-mt-xl text-white q-pt-xl q-pb-xl q-gutter-md aos-init aos-animate" data-aos="fade-up">
            <div class="col-12 col-md q-mt-lg flex items-center aos-init aos-animate" data-aos="fade-up">
              <img src="https://examsdaily.in/wp-content/uploads/2020/12/examsdaily-new-png-png.png" height="90"
                width="360" class="footimg">
              <p style="color: rgb(162,162,162);font-weight: bold;line-height: 30px;">The automated
                process starts as soon as your clothes go into the machine.Discover tools and techniques to engage
                effectively with young people.</p>
            </div>
            <div class="col-12 col-md q-mt-lg flex column items-center aos-init aos-animate footmenu" data-aos="fade-up">
              <div>
                <h3><b>Menu</b></h3>
                <div class="q-mt-lg" style="line-height: 30px;font-weight: bold;">
                  <a href="#" class="foot">Home</a><br>
                  <a href="#" class="foot">About Us</a><br>
                  <a href="#" class="foot">Limitations</a><br>
                  <a href="#" class="foot">Gallery</a><br>
                  <a href="#" class="foot">Contact Us</a>
                </div>
              </div>
            </div>
            <div class="col-12 col-md q-mt-lg aos-init aos-animate" data-aos="fade-up">
              <h3><b>Support</b></h3>
              <div class="q-mt-lg" style="line-height: 30px;font-weight: bold;">
                <a href="#" class="foot">Telecommunication</a><br>
                <a href="#" class="foot">Programming</a><br>
                <a href="#" class="foot">Term and Conditions</a><br>
                <a href="#" class="foot">Privacy Policy</a><br>
                <a href="#" class="foot">Community</a>
              </div>
            </div>
            <div class="col-12 col-md q-mt-lg aos-init aos-animate" data-aos="fade-up" style="font-weight: 500;">
              <h3><b>Contact</b></h3>
              <div class="flex q-gutter-sm no-wrap">
                <img src="https://themewagon.github.io/course/images/placeholder.svg" height="25px" width="25px">
                <span style="word-spacing: 1px;text-wrap: nowrap;">Annai theresa Street, Kalavasal, Madurai-16.</span>
              </div>
              <div class="flex q-gutter-sm q-mt-md">
                <img src="https://themewagon.github.io/course/images/smartphone.svg" height="25px" width="25px">
                <num class="q-mt-sm">8055224403</num>
              </div>
              <a href="https://mail.google.com/chat/u/0/?hl=en#chat/dm/upUCg0AAAAE" target="_blank"
                class="flex q-gutter-sm q-mt-md mail" style="color: white;text-decoration: none;">
                <img src="https://themewagon.github.io/course/images/envelope.svg" height="25px" width="25px">
                <span class="q-mt-sm">contact@edextech.io</span>
              </a>
            </div>
          </div>
          <hr class="q-mt-xl no-border" style="height: 1px; background-color:  rgb(162, 162, 162);">
          <div class="row">
            <div class="col col-12 col-sm-7 text-white q-mt-lg">
              <p style="font-weight: bold;font-size: medium;word-spacing: 2px;">Copyright ©2024 All rights reserved | This
                template is made with <span>♥</span></p>
            </div>
            <div class="col col-12 col-sm-5 q-mt-lg">
              <div class="flex justify-end q-gutter-xl foottemplate">
                <a href="#" class="footicon">
                  <i class="bi bi-twitter"></i>
                </a>
                <a href="#" class="footicon">
                  <i class="bi bi-facebook"></i>
                </a>
                <a href="#" class="footicon">
                  <i class="bi bi-instagram"></i>
                </a>
                <a href="#" class="footicon">
                  <i class="bi bi-linkedin"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </footer>
      <q-drawer v-model="rightDrawerOpen" side="right" bordered>
        <q-list>
          <q-item-label header>
            <q-input v-model="search" filled type="search" label="Search..">
              <template v-slot:append>
                <q-icon name="search" style="margin-bottom: 25px;" />
              </template>
            </q-input>
          </q-item-label>

          <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />
        </q-list>
      </q-drawer>
    </q-layout>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
import AOS from 'aos';
import 'aos/dist/aos.css';

const linksList = [
  {
    title: 'Home',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'About Us',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Limitations',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Contact Us',
    caption: '@quasarframework',
    icon: 'record_voice_over',
    link: 'https://twitter.quasar.dev'
  },
  // {
  //   title: 'Facebook',
  //   caption: '@QuasarFramework',
  //   icon: 'public',
  //   link: 'https://facebook.quasar.dev'
  // },
  // {
  //   title: 'Quasar Awesome',
  //   caption: 'Community Quasar projects',
  //   icon: 'favorite',
  //   link: 'https://awesome.quasar.dev'
  // }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup() {
    const rightDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  },
  mounted() {
    AOS.init({
      duration: 1000,
      offset: 300,
      // easing: 'ease',
      // once: true
    })
  }
})
</script>
<style scoped>
.foot {
  color: rgb(162, 162, 162);
  text-decoration: none;
}

.foot:hover {
  color: rgb(255, 182, 6);
}

.footicon {
  color: white;
  font-size: large;
}

.footicon :hover {
  color: rgb(255, 182, 6);
  transition: transform 2s;
  transform: scale(1.5);
}

.mail :hover {
  text-decoration: underline;
}

@media screen and (max-width:1023px) {
  .footmenu {
    align-items: start;
  }
}

@media screen and (max-width:600px) {
  .foottemplate {
    justify-content: flex-start;
  }
}

@media screen and (max-width:1235px) {
  .footimg {
    width: 220px;
  }
}

.hr {
  width: 9vw;
  height: 0.5vw;
}</style>
