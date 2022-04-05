<template>
  <div class="dropdown">
    <div class="as-navbar__info--dropdown" data-toggle="dropdown">
      <img
        src="@/assets/img/profile.svg"
        class="as-navbar__account"
        loading="lazy"
        alt="user account"
      />
    </div>
    <div class="dropdown-menu as-navbar__info--wrapper">
      <div class="as-navbar__card">
        <div class="as-navbar__card--header">
          <div class="d-flex gap-3">
            <img
              src="@/assets/img/profile-56.svg"
              class="as-navbar__card--image"
              loading="lazy"
              alt="user account"
            />
            <div>
              <p class="as-card-popup__text as-text--bold as-mb--4">
                Handri Hermawan
              </p>
              <div class="d-flex gap-2 align-items-center">
                <p class="as-text--14 as-color-secondary-2">Support PIN:</p>
                <p
                  class="as-text--14-semibold as-color-secondary text-uppercase"
                >
                  AB123C
                </p>
                <div class="as-tooltip as-mb--4">
                  <i class="as-icon-ask-rounded as-icon-gray"></i>
                  <span
                    class="as-tooltip__info as-tooltip__info--sm as-tooltip__info--bottom"
                    >Support PIN adalah salah satu cara untuk memverifikasi
                    bahwa Anda (klien) benar-benar pemilik akun tersebut saat
                    meminta bantuan pada Tim Support kami.</span
                  >
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="as-navbar__card--body">
          <a href="#" class="as-navbar__card--link">
            <i class="as-icon as-icon-user"></i>
            <p class="as-text--16-semibold">Pengaturan Profile</p>
          </a>
          <a href="#" class="as-navbar__card--link-label">
            <div class="as-navbar__card--link-flex">
              <i class="as-icon as-icon-coupon"></i>
              <p class="as-text--16-semibold">Kupon Saya</p>
            </div>
            <div class="as-label--md as-label as-label--blue as-label--rounded">
              145
            </div>
          </a>
          <a href="#" class="as-navbar__card--link">
            <i class="as-icon as-icon-envelope"></i>
            <p class="as-text--16-semibold">Request Fitur</p>
          </a>
          <a href="#" class="as-navbar__card--link">
            <i class="as-icon as-icon-logout as-color--red"></i>
            <p class="as-text--16-semibold as-color--red">Keluar</p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: "Profile"
}
</script>