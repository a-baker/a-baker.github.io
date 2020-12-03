<template>
  <div>
    <header class="header">
      <div class="container">
        <g-link to="/">
          <img class="nav__logo" src="@/assets/images/logo.svg" alt="A logo image of my face">
        </g-link>
        <nav class="nav">
          <g-link class="nav__link" to="/">Home</g-link>
          <g-link class="nav__link" to="/about/">About</g-link>
        </nav>
      </div>
    </header>
    <main>
      <slot/>
    </main>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style lang="scss">
.container {
  max-width: 76rem;
  margin: 0 auto;
  padding-left: 2rem;
  padding-right: 2rem;
}

.header {
  margin-bottom: 2rem;
  height: 8rem;

  .container {
    height: 8rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}

.nav__logo {
  width: 3.7rem;
  display: block;
}

$nav-link-color: #000;

.nav__link {
  color: $nav-link-color;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 10px;
  font-weight: bold;
  transition: 0.2s ease-in-out;
  transition-property: color, background-color;

  & + & {
    margin-left: 2rem;
  }

  &:hover {
    color: #fff;
    background-color: $nav-link-color;
  }
}
</style>
