# css
/*===== GOOGLE FONTS =====*/
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap");

/*===== VARIABLES CSS =====*/
:root {
  --header-height: 3rem;

  /*===== Colors =====*/
  --first-color: #5B65F5;
  --first-color-light: #C4C7F5;
  --dark-color: #0E1026;
  --white-color: #FBFBFB;

  /*===== Font and typography =====*/
  --body-font: 'Open Sans', sans-serif;
  --nav-name-font-size: 1.5rem;
  --normal-font-size: .938rem;

  /*===== z index =====*/
  --z-fixed: 100;
}

@media screen and (min-width: 768px) {
  :root {
    --nav-name-font-size: 1rem;
    --normal-font-size: 1rem;
  }
}

/*===== BASE =====*/
*, ::before, ::after {
  box-sizing: border-box;
}

body {
  margin: var(--header-height) 0 0 0;
  font-family: var(--body-font);
  font-size: var(--normal-font-size);
  font-weight: 600;
}

ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

a {
  text-decoration: none;
}

.bd-grid {
  max-width: 1024px;
  display: grid;
  grid-template-columns: 100%;
  margin-left: 1.5rem;
  margin-right: 1.5rem;
}

/*===== HEADER =====*/
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: var(--header-height);
  padding: 0 1rem;
  background-color: #FFF;
  z-index: var(--z-fixed);
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.header__logo {
  color: var(--dark-color);
}

.header__toggle {
  font-size: 1.7rem;
  cursor: pointer;
}

/*===== NAV =====*/
@media screen and (max-width: 768px) {
  .nav {
    position: fixed;
    top: 0;
    left: -100%;
    background-color: var(--first-color);
    width: 80%;
    height: 100vh;
    padding: 2rem 0;
    z-index: var(--z-fixed);
    transition: .5s;
    overflow-y: auto;
  }
}

.nav__content {
  display: flex;
  flex-direction: column;
}

.nav__perfil {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin-bottom: 3rem;
}

.nav__img {
  display: flex;
  justify-content: center;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  overflow: hidden;
  margin-bottom: 1rem;
}

.nav__img img {
  width: 70px;
}

.nav__name {
  display: block;
  font-size: var(--nav-name-font-size);
  color: var(--white-color);
}

.nav__item {
  margin-bottom: 2rem;
}

.nav__link {
  color: var(--first-color-light);
}

.nav__link:hover {
  color: var(--white-color);
}

/*Show menu*/
.show {
  left: 0;
}

/*Active link*/
.active {
  color: var(--white-color);
}

/*=== Dropdown ===*/
.dropdown__link {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.dropdown__icon {
  font-size: 1.3rem;
  transition: .5s;
}

.dropdown__menu {
  margin: 1rem 0 0 1rem;
  display: none;
}

.dropdown__item {
  margin: 1rem 0;
}

.dropdown:hover > .dropdown__menu {
  display: block;
}

.dropdown:hover .dropdown__icon {
  transform: rotate(180deg);
}

/* ===== MEDIA QUERIES=====*/
@media screen and (min-width: 576px) {
  .nav {
    width: 288px;
  }
}

@media screen and (min-width: 768px) {
  body {
    margin: 0;
  }
  .header {
    height: calc(var(--header-height) + 1rem);
  }
  .header__logo, .header__toggle {
    display: none;
  }
  .nav {
    width: 100%;
  }
  .nav__content {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .nav__perfil {
    flex-direction: row;
    text-align: initial;
    margin-bottom: 0;
  }
  .nav__img {
    width: 40px;
    height: 40px;
    margin-right: .5rem;
    margin-bottom: 0;
  }
  .nav__img img {
    width: 46px;
  }
  .nav__name {
    color: var(--dark-color);
  }
  .nav__list {
    display: flex;
    align-items: center;
  }
  .nav__item {
    margin: 0 1.5rem;
    padding: 1.4rem 0;
  }
  .nav__link {
    color: var(--dark-color);
  }
  .nav__link:hover {
    color: var(--first-color);
  }
  /*Active link new color*/
  .active {
    color: var(--first-color);
  }
  .dropdown {
    position: relative;
  }
  .dropdown__menu {
    position: fixed;
    margin: 0;
    top: calc(var(--header-height) + 1rem);
    padding: .5rem 1.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: .5rem;
  }
  .dropdown__item {
    margin: .5rem 0;
  }
}

@media screen and (min-width: 1024px) {
  .bd-grid {
    margin-left: auto;
    margin-right: auto;
  }
}
