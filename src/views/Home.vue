<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex xs12>
        <v-img
          :src="require('@/assets/logo.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-flex>

      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to aiogram
        </h1>
        <p class="subheading font-weight-regular mx-3">
          <strong>aiogram</strong> is modern and fully asynchronous framework
          <br/>for <a href="https://core.telegram.org/bots/api">Telegram Bot API</a>
          written in <a href="https://www.python.org/">Python</a>
          with <a href="https://docs.python.org/3/library/asyncio.html">asyncio</a>
          and <a href="https://aiohttp.readthedocs.io/en/stable/">aiohttp</a>.
          <br/>It helps you to make your bots faster and simpler.
        </p>
      </v-flex>

      <v-flex
        mb-5
        xs12
      >
        <h2 class="headline font-weight-bold mb-3">What's next?</h2>
        <p><strong>aiogram</strong> currently has {{ versions.length }} active versions:</p>

        <v-layout justify-center>
          <v-tooltip
            v-for="(next, i) in versions"
            :key="i"
            bottom
          >
            <template v-slot:activator="{ on }">
              <a
                :href="next.documentation"
                class="subheading mx-3"
                target="_blank"
                v-on="on"
              >
                {{ next.label }}
              </a>
            </template>
            <span>{{ next.tooltip }}</span>
          </v-tooltip>

        </v-layout>
      </v-flex>

      <v-flex
        xs12
        mb-5
      >
        <p class="subheading font-weight-regular">
          For help and collaboration with other <strong>aiogram</strong> developers,
          <br />please visit our online
          <a href="https://t.me/aiogram" target="_blank">community</a>.
        </p>
      </v-flex>

      <v-flex
        xs12
        mb-5
      >
        <h3>Special thanks</h3>
        <p>
          Special thanks to
          <router-link to="/contributors">our contributors</router-link> and
          <a href="https://opencollective.com/aiogram#section-contributors">financial contributors</a>.
        </p>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    name: 'Home',
    data: () => ({
      versions: [
        {
          documentation: 'https://docs.aiogram.dev/en/dev-3.x/',
          label: '3.0',
          tooltip: 'Release Candidate',
        },
      ]
    }),
  };
</script>
