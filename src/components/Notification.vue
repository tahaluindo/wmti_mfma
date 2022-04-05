<template>
  <div class="dropdown">
    <div class="as-navbar__info--dropdown" data-toggle="dropdown">
      <span class="as-navbar__info--alert"></span>
      <img
        src="@/assets/img/icon/bell.svg"
        class="as-navbar__info--icon"
        loading="lazy"
        alt="notification"
      />
    </div>
    <div class="dropdown-menu as-navbar__info--wrapper">
      <div
        class="as-card-notification as-navbar__card as-card-notification as-navbar__card--notif"
      >
        <div class="as-card-notification__header">
          <ul
            class="as-card-notification__header--nav nav nav-pills"
            id="pills-tab"
            role="tablist"
          >
            <li class="nav-item" role="presentation">
              <button
                class="as-card-notification__header--link"
                :class="btnOneClassName"
                @click="tabClickHandler(true)"
                id="nav-notif-tab"
                data-bs-toggle="pill"
                data-bs-target="#nav-notif"
                type="button"
                role="tab"
                aria-controls="nav-notif"
                :aria-selected="tabOneActive"
              >
                Pemberitahuan
              </button>
              <span class="as-card-notification__header--indicator"></span>
            </li>
            <li class="nav-item" role="presentation">
              <button
                class="as-card-notification__header--link"
                :class="btnTwoClassName"
                @click="tabClickHandler(false)"
                id="nav-promo-tab"
                data-bs-toggle="pill"
                data-bs-target="#nav-promo"
                type="button"
                role="tab"
                aria-controls="nav-promo"
                :aria-selected="!tabOneActive"
              >
                Update & Promo
              </button>
              <span class="as-card-notification__header--indicator"></span>
            </li>
          </ul>
        </div>
        <div
          class="as-card-notification__body as-card-notification__body--scroll"
        >
          <div class="tab-content" id="pills-tabContent">
            <div
              class="tab-pane fade"
              :class="tabOneClassName"
              id="nav-notif"
              role="tabpanel"
              aria-labelledby="nav-notif-tab"
            >
              <a href="#" class="as-card-notification__content">
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/downtime.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="downtime"
                  />
                  <p class="as-text-12-semibold as-color-red">Downtime</p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih
                </p>
              </a>
              <a
                href="#"
                class="as-card-notification__content as-background--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/product.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="product status"
                  />
                  <p class="as-text-12-semibold as-color-yellow">
                    Product Status
                  </p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih
                </p>
              </a>
              <a
                href="#"
                class="as-card-notification__content as-card-notification__content--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/resource.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="resource"
                  />
                  <p class="as-text-12-semibold as-color-blue-dark">
                    Resource
                  </p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
              <a
                href="#"
                class="as-card-notification__content as-card-notification__content--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/invoice.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="Invoice"
                  />
                  <p class="as-text-12-semibold as-color-red">Invoice</p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
              <a
                href="#"
                class="as-card-notification__content as-card-notification__content--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/promo.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="Promo"
                  />
                  <p class="as-text-12-semibold as-color-green">Promo</p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
            </div>
            <div
              class="tab-pane fade"
              :class="tabTwoClassName"
              id="nav-promo"
              role="tabpanel"
              aria-labelledby="nav-promo-tab"
            >
              <a
                href="#"
                class="as-card-notification__content as-background--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/resource.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="resource"
                  />
                  <p class="as-text-12-semibold as-color-blue-dark">
                    Resource
                  </p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
              <a href="#" class="as-card-notification__content">
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/invoice.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="Invoice"
                  />
                  <p class="as-text-12-semibold as-color--red">Invoice</p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
              <a
                href="#"
                class="as-card-notification__content as-card-notification__content--soft"
              >
                <div class="d-flex gap-2 align-items-center as-mb-12">
                  <img
                    src="@/assets/img/status/promo.svg"
                    class="as-card-notification__content--image"
                    loading="lazy"
                    alt="Promo"
                  />
                  <p class="as-text-12-semibold as-color-green">Promo</p>
                  <span class="as-card-notification__content--dot"></span>
                  <p class="as-text-12 as-color-secondary-2">
                    30 Desember 2022, 17:00
                  </p>
                </div>
                <p class="as-text-16-bold as-mb-12">
                  Server akan mengalami maintanance
                </p>
                <p class="as-card-notification__content--text as-text-12">
                  Server srv56.niagahoster.com akan mengalami maintanance pada 7
                  Oktober 2021 jam 23.30-00.30. Mohon maaf atas
                  ketidaknyamanannya. Terima kasih jangan lupa like dan
                  subscribe channel kami agar kami cepat kaya raya
                </p>
              </a>
            </div>
          </div>
        </div>
        <div class="as-card-notification__footer">
          <AsButtonText link>
            Tandai semua sudah dibaca
          </AsButtonText>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue'
import { AsButtonText } from '@niagahoster/components'

const tabOneActive = ref(true)

const tabClickHandler = (isTabOne) => {
  tabOneActive.value = isTabOne
}

const btnOneClassName = computed(() => ({
  'active': tabOneActive.value
}))

const btnTwoClassName = computed(() => ({
  'active': !tabOneActive.value
}))

const tabOneClassName = computed(() => ({
  'active': tabOneActive.value,
  'show': tabOneActive.value, 
}))

const tabTwoClassName = computed(() => ({
  'active': !tabOneActive.value,
  'show': !tabOneActive.value,
}))
</script>
