<template>
  <section class="section">
    <div class="columns is-mobile">
      <card
        title="Free"
        icon="github"
      >
        Open source on <a href="https://github.com/buefy/buefy">
          GitHub
        </a>
      </card>

      <card
        :title="out"
        icon="cellphone-link"
      >
        <b class="has-text-grey">
          Every
        </b> component is responsive
      </card>

      <card
        title="Modern"
        icon="alert-decagram"
      >
        Built with <a href="https://vuejs.org/">
          Vue.js
        </a> and <a href="http://bulma.io/">
          Bulma
        </a>
      </card>

      <card
        title="Lightweight"
        icon="arrange-bring-to-front"
      >
        No other internal dependency
      </card>
    </div>
  </section>
</template>

<script>
import Card from '~/components/Card'

export default {
  name: 'HomePage',
  components: {
    Card
  },
  async asyncData ({ $http }) {
    let i = 0
    let k = 0
    const t = 1000000 // Math.round(1000000 * Math.random())
    const start = Date.now()

    for (i = 0; i < t; i++) {
      k = k + Math.random()
    }

    const end = Date.now()

    const out = 'Looped ' + i + ' times in ' + (end - start) + 'ms'
    // const thingy = await fetch('/inspire') // 'http://bbc.co.uk')

    const thingy = await new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve('foo');
      }, 1);
    });

    return { out, thingy }
  }
}
</script>
