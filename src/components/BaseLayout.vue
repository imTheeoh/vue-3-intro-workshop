<script>
export default {
  data() {
    return {
      pageTitle: 'Yayyy it works!',
    }
  },
}
</script>

<template>
  <header>
    <h1>{{ pageTitle }}</h1>
  </header>
  <main>
    <section>
      <slot name="section-1"></slot>
    </section>
    <section>
      <slot name="section-2"></slot>
    </section>
    <section>
      <slot name="section-3"></slot>
    </section>
  </main>
  <footer>
    <slot name="footer"></slot>
  </footer>
</template>
