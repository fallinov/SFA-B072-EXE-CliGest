<template>
  <q-page padding>
    <h3>Liste des clients</h3>

    <q-list
      v-if="clients.length"
      class="rounded-borders"
      bordered
      separator
    >
      <!-- Composant Client.vue avec propriété client -->
      <client
        v-for="client of clients"
        :key="client.id.value"
        :client="client"
      />
    </q-list>

    <p v-else>Pas de clients ...</p>
  </q-page>
</template>

<script>
// Importation du composant Client.vue
import Client from 'components/Client'

// Importation des outils de mappage Vuex
import { mapGetters } from 'vuex'

// Application Vue
export default {
  // Nom du composant
  name: 'ListeClients',
  // Importation des composants exerternes
  components: { Client },
  // Proriétés calculées
  computed: {
    // Donne accès au getter clients() du magasin Clients
    ...mapGetters('clients', ['clients'])
  }
}
</script>
