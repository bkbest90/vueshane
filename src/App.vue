<template>
  <div style="background-color: white;" id="material-kit">
    <div style="background-color: white;" :class="{ 'nav-open': NavbarStore.showNavbar }">
      <router-view name="header" />
      <div>
        <router-view style="" />
      </div>
      <router-view name="footer" />
    </div>
  </div>
</template>