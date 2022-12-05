<template>

    <v-card outlined>
        <v-card-title>
            MeansOfDelivery # {{$route.params.id }}
        </v-card-title>

        <v-card-text>
        </v-card-text>
    </v-card>

</template>

<script>
  const axios = require('axios').default;

  export default {
    name: 'MeansOfDeliveryViewDetail',
    props: {
      value: Object,
    },
    data: () => ({
        item : [],
    }),
    async created() {
      var params = this.$route.params;
      var temp = await axios.get(axios.fixUrl('/meansOfDeliveries/' + params.id))

      this.item = temp.data;

    },
    methods: {
    }
  }
</script>

