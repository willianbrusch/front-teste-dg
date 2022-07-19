<template>
  <header class="header-app">
    <a href="https://dgsolutions.com.br/">
      <img class="dg-logo" src="../assets/dg-logo.png" alt="dg-logo" />
    </a>
  </header>
</template>

<script></script>

<style>
.header-app {
  width: 100vw;
  height: 70px;
  background-color: var(--primaryBlue);
}

.dg-logo {
  padding: 7px;
  margin-left: 20px;
  width: 65px;
}

@media (max-width: 520px) {
  .header-app {
    width: 100vw;
  }
}
</style>
