<template>
  <Title>Custom Page Templatee</Title>
  <nav>
    Nav goes here
    <ul>
      <li><nuxt-link to="/about">About</nuxt-link></li>
      <li><nuxt-link to="/contact">Contact</nuxt-link></li>
      <li><nuxt-link to="/">Home</nuxt-link></li>
    </ul>
  </nav>
  <div>
    <slot/>
  </div>
</template>
