<template>
  <header class="as-header">
    <nav class="as-navbar navbar navbar-expand-xl">
        <div class="as-navbar__info">
            <div class="d-flex justify-content-end d-xl-none">
                <button class="as-navbar-toggler collapsed" type="button" aria-label="menu" data-bs-toggle="collapse"
                    data-bs-target="#mobileNavbar" @click="collapseNavbar = !collapseNavbar">
                    <span class="bar bar--one"></span>
                    <span class="bar bar--two"></span>
                    <span class="bar bar--three"></span>
                </button>
            </div>
            <a class="navbar-brand" aria-label="Logo Niagahoster" href="">
                <img src="@/assets/img/logo-white.svg" height="55" width="55" loading="lazy" class="as-navbar__logo"
                    alt="logo niagahoster" />
            </a>
        </div>
        <div class="as-navbar__collapse collapse navbar-collapse">
            <ul class="as-navbar__nav navbar-nav">
                <MenuDropdown name="Layanan" :list="serviceMenuList"/>
                <Menu name="Tagihan" target="https://google.com" :count="99"/>
                <MenuDropdown name="Support & Tutorial" :list="supportMenuList"/>
                <MenuDropdown name="Program Kemitraan" :list="programMenuList"/>
                <Menu name="Niagahoster Poin" target="https://google.com"/>
            </ul>
        </div>
        <div class="justify-content-end">
            <div class="as-navbar__info">
                <Notification/>
                <Profile/>
            </div>
        </div>
    </nav>

    <div id="mobileNavbar" class="collapse as-navbar__mobile d-xl-none" :class="{'show' : collapseNavbar}">
        <div class="accordion js-accordion p-3">
            <div class="accordion as-accordion-menu__item js-accordion__item" :class="{'active' : serviceMenu}" @click="serviceMenu = !serviceMenu">
                <div class="accordion-header as-accordion-menu__header js-accordion__header">
                    Layanan
                </div>
                <div class="as-accordion-menu__body js-accordion__body" :class="{'d-block' : serviceMenu}">
                    <div class="as-accordion-menu__content">
                        <a href="#" class="as-navbar__dropdown-link">Layanan Saya </a>
                        <a href="#" class="as-navbar__dropdown-link">Order Layanan Baru </a>
                    </div>
                </div>
            </div>
            <a href="#" class="as-accordion-menu__link">
                <p class="as-navbar__link--name">Tagihan</p>
                <div class="as-navbar__count">
                    <span>99+</span>
                </div>
            </a>
            <div class="accordion as-accordion-menu__item js-accordion__item" :class="{'active' : supportMenu}" @click="supportMenu = !supportMenu">
                <div class="accordion-header as-accordion-menu__header js-accordion__header">
                    Support & Tutorial
                </div>
                <div class="as-accordion-menu__body js-accordion__body" :class="{'d-block' : supportMenu}">
                    <div class="as-accordion-menu__content">
                        <a href="#" class="as-navbar__dropdown-link">Niagahoster Course </a>
                        <a href="#" class="as-navbar__dropdown-link">Niagahoster Forum </a>
                        <a href="#" class="as-navbar__dropdown-link">Knowledge Base </a>
                        <a href="#" class="as-navbar__dropdown-link">Blog </a>
                        <a href="#" class="as-navbar__dropdown-link">E-Book </a>
                    </div>
                </div>
            </div>
            <div class="accordion as-accordion-menu__item js-accordion__item" :class="{'active' : programMenu}" @click="programMenu = !programMenu">
                <div class="accordion-header as-accordion-menu__header js-accordion__header">
                    Program Kemitraan
                </div>
                <div class="as-accordion-menu__body js-accordion__body" :class="{'d-block' : programMenu}">
                    <div class="as-accordion-menu__content">
                        <a href="#" class="as-navbar__dropdown-link">Niagahoster Partner </a>
                        <a href="#" class="as-navbar__dropdown-link">Afiliasi </a>
                    </div>
                </div>
            </div>
            <a href="#" class="as-accordion-menu__link">Niagahoster Poin </a>
        </div>
        <hr class="as-navbar__line">
        <div class="as-navbar__bottom">
            <div class="as-navbar__copyright">
                Copyright ©2021 Niagahoster
            </div>
            <div class="as-navbar__social">
                <ul class="as-navbar__social--list">
                    <li class="as-navbar__social--icon">
                        <a href="https://www.facebook.com/niagahoster" target="_blank" rel="noopener noreferrer"
                            aria-label="facebook niagahoster">
                            <svg width="11" height="20" viewBox="0 0 11 20" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M9.11999 3.32003H11V0.14003C10.0897 0.045377 9.17514 -0.00135428 8.25999 2.98641e-05C5.53999 2.98641e-05 3.67999 1.66003 3.67999 4.70003V7.32003H0.609985V10.88H3.67999V20H7.35998V10.88H10.42L10.88 7.32003H7.35998V5.05003C7.35998 4.00003 7.63999 3.32003 9.11999 3.32003Z"
                                    fill="white" />
                            </svg>
                        </a>
                    </li>
                    <li class="as-navbar__social--icon">
                        <a href="https://www.instagram.com/niagahoster.id" target="_blank" rel="noopener noreferrer"
                            aria-label="instagram niagahoster">
                            <svg width="20" height="20" viewBox="0 0 20 20" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M15.34 3.46C15.1027 3.46 14.8707 3.53038 14.6733 3.66224C14.476 3.79409 14.3222 3.98151 14.2313 4.20078C14.1405 4.42005 14.1168 4.66133 14.1631 4.89411C14.2094 5.12689 14.3236 5.34071 14.4915 5.50853C14.6593 5.67635 14.8731 5.79064 15.1059 5.83694C15.3387 5.88324 15.5799 5.85948 15.7992 5.76866C16.0185 5.67783 16.2059 5.52402 16.3378 5.32668C16.4696 5.12935 16.54 4.89734 16.54 4.66C16.54 4.34174 16.4136 4.03652 16.1885 3.81147C15.9635 3.58643 15.6583 3.46 15.34 3.46ZM19.94 5.88C19.9206 5.0503 19.7652 4.2294 19.48 3.45C19.2257 2.78313 18.83 2.17928 18.32 1.68C17.8248 1.16743 17.2196 0.774176 16.55 0.53C15.7727 0.236161 14.9508 0.07721 14.12 0.0599999C13.06 -5.58794e-08 12.72 0 10 0C7.28 0 6.94 -5.58794e-08 5.88 0.0599999C5.04915 0.07721 4.22734 0.236161 3.45 0.53C2.78168 0.776649 2.17693 1.16956 1.68 1.68C1.16743 2.17518 0.774176 2.78044 0.53 3.45C0.236161 4.22734 0.07721 5.04915 0.0599999 5.88C-5.58794e-08 6.94 0 7.28 0 10C0 12.72 -5.58794e-08 13.06 0.0599999 14.12C0.07721 14.9508 0.236161 15.7727 0.53 16.55C0.774176 17.2196 1.16743 17.8248 1.68 18.32C2.17693 18.8304 2.78168 19.2234 3.45 19.47C4.22734 19.7638 5.04915 19.9228 5.88 19.94C6.94 20 7.28 20 10 20C12.72 20 13.06 20 14.12 19.94C14.9508 19.9228 15.7727 19.7638 16.55 19.47C17.2196 19.2258 17.8248 18.8326 18.32 18.32C18.8322 17.8226 19.2283 17.2182 19.48 16.55C19.7652 15.7706 19.9206 14.9497 19.94 14.12C19.94 13.06 20 12.72 20 10C20 7.28 20 6.94 19.94 5.88ZM18.14 14C18.1327 14.6348 18.0178 15.2637 17.8 15.86C17.6403 16.2952 17.3839 16.6884 17.05 17.01C16.7256 17.3405 16.3332 17.5964 15.9 17.76C15.3037 17.9778 14.6748 18.0927 14.04 18.1C13.04 18.15 12.67 18.16 10.04 18.16C7.41 18.16 7.04 18.16 6.04 18.1C5.38089 18.1123 4.72459 18.0109 4.1 17.8C3.68578 17.6281 3.31136 17.3728 3 17.05C2.66809 16.7287 2.41484 16.3352 2.26 15.9C2.01586 15.2952 1.88044 14.6519 1.86 14C1.86 13 1.8 12.63 1.8 10C1.8 7.37 1.8 7 1.86 6C1.86448 5.35106 1.98295 4.70795 2.21 4.1C2.38605 3.67791 2.65627 3.30166 3 3C3.30381 2.65617 3.67929 2.3831 4.1 2.2C4.70955 1.98004 5.352 1.86508 6 1.86C7 1.86 7.37 1.8 10 1.8C12.63 1.8 13 1.8 14 1.86C14.6348 1.86728 15.2637 1.98225 15.86 2.2C16.3144 2.36865 16.7223 2.64285 17.05 3C17.3777 3.30718 17.6338 3.68273 17.8 4.1C18.0223 4.70893 18.1373 5.35178 18.14 6C18.19 7 18.2 7.37 18.2 10C18.2 12.63 18.19 13 18.14 14ZM10 4.87C8.98581 4.87198 7.99496 5.17453 7.15265 5.73942C6.31035 6.30431 5.65438 7.1062 5.26763 8.04375C4.88089 8.98131 4.78072 10.0125 4.97979 11.0069C5.17886 12.0014 5.66824 12.9145 6.38608 13.631C7.10392 14.3474 8.01801 14.835 9.01286 15.0321C10.0077 15.2293 11.0387 15.1271 11.9755 14.7385C12.9123 14.35 13.7129 13.6924 14.2761 12.849C14.8394 12.0056 15.14 11.0142 15.14 10C15.1413 9.3251 15.0092 8.65661 14.7512 8.03296C14.4933 7.40931 14.1146 6.84281 13.6369 6.36605C13.1592 5.88929 12.5919 5.51168 11.9678 5.25493C11.3436 4.99818 10.6749 4.86736 10 4.87ZM10 13.33C9.34139 13.33 8.69757 13.1347 8.14995 12.7688C7.60234 12.4029 7.17552 11.8828 6.92348 11.2743C6.67144 10.6659 6.6055 9.99631 6.73398 9.35035C6.86247 8.70439 7.17963 8.11104 7.64533 7.64533C8.11104 7.17963 8.70439 6.86247 9.35035 6.73398C9.99631 6.6055 10.6659 6.67144 11.2743 6.92348C11.8828 7.17552 12.4029 7.60234 12.7688 8.14995C13.1347 8.69757 13.33 9.34139 13.33 10C13.33 10.4373 13.2439 10.8703 13.0765 11.2743C12.9092 11.6784 12.6639 12.0454 12.3547 12.3547C12.0454 12.6639 11.6784 12.9092 11.2743 13.0765C10.8703 13.2439 10.4373 13.33 10 13.33Z"
                                    fill="white" />
                            </svg>
                        </a>
                    </li>
                    <li class="as-navbar__social--icon">
                        <a href="https://www.linkedin.com/company/niagahoster" class="as-navbar__icon" target="_blank"
                            rel="noopener noreferrer" aria-label="linkedin niagahoster">
                            <svg width="20" height="20" viewBox="0 0 20 20" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M18.47 1.77605e-05H1.53C1.33958 -0.00262686 1.1505 0.0322653 0.973563 0.102702C0.796628 0.173138 0.635301 0.277738 0.498795 0.41053C0.362289 0.543321 0.253279 0.701702 0.177989 0.876627C0.1027 1.05155 0.062606 1.2396 0.0599976 1.43002V18.57C0.062606 18.7604 0.1027 18.9485 0.177989 19.1234C0.253279 19.2983 0.362289 19.4567 0.498795 19.5895C0.635301 19.7223 0.796628 19.8269 0.973563 19.8973C1.1505 19.9678 1.33958 20.0027 1.53 20H18.47C18.6604 20.0027 18.8495 19.9678 19.0264 19.8973C19.2034 19.8269 19.3647 19.7223 19.5012 19.5895C19.6377 19.4567 19.7467 19.2983 19.822 19.1234C19.8973 18.9485 19.9374 18.7604 19.94 18.57V1.43002C19.9374 1.2396 19.8973 1.05155 19.822 0.876627C19.7467 0.701702 19.6377 0.543321 19.5012 0.41053C19.3647 0.277738 19.2034 0.173138 19.0264 0.102702C18.8495 0.0322653 18.6604 -0.00262686 18.47 1.77605e-05ZM6.09 16.74H3.09V7.74002H6.09V16.74ZM4.59 6.48002C4.17626 6.48002 3.77947 6.31566 3.48691 6.0231C3.19435 5.73055 3.03 5.33376 3.03 4.92002C3.03 4.50628 3.19435 4.10949 3.48691 3.81693C3.77947 3.52437 4.17626 3.36002 4.59 3.36002C4.80969 3.3351 5.03217 3.35687 5.24287 3.4239C5.45357 3.49093 5.64774 3.60171 5.81265 3.74898C5.97757 3.89625 6.10952 4.0767 6.19987 4.2785C6.29021 4.4803 6.33692 4.69891 6.33692 4.92002C6.33692 5.14112 6.29021 5.35973 6.19987 5.56154C6.10952 5.76334 5.97757 5.94378 5.81265 6.09106C5.64774 6.23833 5.45357 6.3491 5.24287 6.41613C5.03217 6.48316 4.80969 6.50493 4.59 6.48002ZM16.91 16.74H13.91V11.91C13.91 10.7 13.48 9.91002 12.39 9.91002C12.0527 9.91249 11.7242 10.0183 11.4488 10.2132C11.1735 10.4081 10.9645 10.6827 10.85 11C10.7717 11.2351 10.7378 11.4826 10.75 11.73V16.73H7.75C7.75 16.73 7.75 8.55002 7.75 7.73002H10.75V9.00002C11.0225 8.52712 11.4189 8.13754 11.8964 7.87322C12.374 7.6089 12.9146 7.47987 13.46 7.50002C15.46 7.50002 16.91 8.79002 16.91 11.56V16.74Z"
                                    fill="white" />
                            </svg>
                        </a>
                    </li>
                    <li class="as-navbar__social--icon">
                        <a href="https://twitter.com/niagahoster" target="_blank" rel="noopener noreferrer"
                            aria-label="twitter niagahoster">
                            <svg width="20" height="18" viewBox="0 0 20 18" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M20 2.79997C19.2483 3.12606 18.4534 3.34163 17.64 3.43997C18.4982 2.92729 19.1413 2.12075 19.45 1.16997C18.6436 1.65003 17.7608 1.98826 16.84 2.16997C16.2245 1.50254 15.405 1.05826 14.5098 0.906817C13.6147 0.755372 12.6945 0.905324 11.8938 1.33315C11.093 1.76099 10.4569 2.4425 10.0852 3.2708C9.71355 4.09911 9.62729 5.02736 9.84 5.90997C8.20943 5.82749 6.61444 5.40292 5.15865 4.66383C3.70287 3.92474 2.41885 2.88766 1.39 1.61997C1.02914 2.25013 0.839519 2.96379 0.84 3.68997C0.83872 4.36435 1.00422 5.02858 1.32176 5.62353C1.63929 6.21848 2.09902 6.72568 2.66 7.09997C2.00798 7.08222 1.36989 6.90726 0.8 6.58997V6.63997C0.804887 7.58486 1.13599 8.49906 1.73731 9.22793C2.33864 9.9568 3.17326 10.4556 4.1 10.64C3.74326 10.7485 3.37287 10.8058 3 10.81C2.74189 10.807 2.48442 10.7835 2.23 10.74C2.49391 11.5528 3.00462 12.2631 3.69107 12.7721C4.37753 13.2811 5.20558 13.5635 6.06 13.58C4.6172 14.7152 2.83588 15.3348 1 15.34C0.665735 15.3411 0.331736 15.321 0 15.28C1.87443 16.4902 4.05881 17.1327 6.29 17.13C7.82969 17.146 9.35714 16.855 10.7831 16.274C12.2091 15.6931 13.505 14.8338 14.5952 13.7465C15.6854 12.6591 16.548 11.3654 17.1326 9.94087C17.7172 8.51639 18.012 6.98969 18 5.44997C18 5.27996 18 5.09997 18 4.91997C18.7847 4.33478 19.4615 3.61739 20 2.79997Z"
                                    fill="white" />
                            </svg>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
  </header>
</template>

<script>

import Menu from './components/Menu.vue'
import MenuDropdown from './components/MenuDropdown.vue'
import Notification from './components/Notification.vue'
import Profile from './components/Profile.vue'

export default {
  name: 'App',
  components: {
      Menu,
      MenuDropdown,
      Notification,
      Profile
  },
  data() {
    return {
      collapseNavbar: false,
      serviceMenu: false,
      supportMenu: false,
      programMenu: false,
      serviceMenuList: [
          {name: 'Layanan Saya', target: '#'},
          {name: 'Order Layanan Baru', target: '#'}
      ],
      supportMenuList: [
          {name: 'Niagahoster Course', target: 'https://course.niagahoster.co.id'},
          {name: 'Niagahoster Forum', target: 'https://forum.niagahoster.co.id'},
          {name: 'Knowledge Base', target: 'https://niagahoster.co.id/kb'},
          {name: 'Blog', target: 'https://blog.niagahoster.co.id'},
          {name: 'E-Book', target: 'https://blog.niagahoster.co.id'}
      ],
      programMenuList: [
          {name: 'Niagahoster Partner', target: '#'},
          {name: 'Afiliasi', target: '#'}
      ],
    }
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/app.scss';
</style>
