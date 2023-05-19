<template lang="pug">
  div
    nav.navbar.navbar-expand-lg.navbar-dark.bg-dark
      .container-fluid
        nuxt-link(to="/" class="navbar-brand") My - Notes
        button.navbar-toggler(type='button' data-bs-toggle='collapse' data-bs-target='#navbarSupportedContent' aria-controls='navbarSupportedContent' aria-expanded='false' aria-label='Toggle navigation')
          span.navbar-toggler-icon
        #navbarSupportedContent.collapse.navbar-collapse
    Nuxt
</template>