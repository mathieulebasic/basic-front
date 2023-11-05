<template>
  <img :src="path" alt="Vue logo" />
  <div>
    <!-- Your component template here -->
    <button @click="fetchData">Fetch Data</button>
    <div v-if="apiResponse">
      <pre>{{ apiResponse }}</pre>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      query:
        '[out:json];nwr["ref:INSEE"="38018"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38021"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26035"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38036"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26059"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26066"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26069"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26074"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38090"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38092"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26086"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38103"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38108"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38111"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38113"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38117"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26100"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38129"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26113"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26117"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38153"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38169"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26141"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26142"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38186"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38187"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38195"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38205"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26159"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26163"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26168"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38216"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26175"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38225"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38235"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38243"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38248"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26217"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38281"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26221"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26223"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38301"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26240"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26246"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38319"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38322"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38333"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38338"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26270"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26282"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38345"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26290"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38355"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26291"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38356"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38390"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38391"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26307"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26308"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26309"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38409"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26311"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38419"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26315"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26316"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38429"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26320"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38433"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38436"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38438"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38443"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38450"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38453"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26331"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26299"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26302"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38474"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38485"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38486"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26354"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26359"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38524"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="26364"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38540"](0.865,0.25,66.9,66.27);nwr["ref:INSEE"="38548"](0.865,0.25,66.9,66.27);out geom;',
      url: "https://overpass-api.de/api/interpreter",
      bbox: "0,40,67,51", // Replace with your bounding box coordinates
      apiResponse: null,
    };
  },
  computed: {
    path() {
      return require(`@/assets/icons/${this.name}.svg`);
    },
  },
  async mounted() {
    const api = await fetch("https://www.overpass-api.de/api/interpreter?", {
      method: "POST",
      headers: {
        Accept: "application/json",
        "Content-Type": "application/json",
      },
      body: '[out:json];nwr["ref:INSEE"="38018"]({{bbox}});nwr["ref:INSEE"="38021"]({{bbox}});nwr["ref:INSEE"="26035"]({{bbox}});nwr["ref:INSEE"="38036"]({{bbox}});nwr["ref:INSEE"="26059"]({{bbox}});nwr["ref:INSEE"="26066"]({{bbox}});nwr["ref:INSEE"="26069"]({{bbox}});nwr["ref:INSEE"="26074"]({{bbox}});nwr["ref:INSEE"="38090"]({{bbox}});nwr["ref:INSEE"="38092"]({{bbox}});nwr["ref:INSEE"="26086"]({{bbox}});nwr["ref:INSEE"="38103"]({{bbox}});nwr["ref:INSEE"="38108"]({{bbox}});nwr["ref:INSEE"="38111"]({{bbox}});nwr["ref:INSEE"="38113"]({{bbox}});nwr["ref:INSEE"="38117"]({{bbox}});nwr["ref:INSEE"="26100"]({{bbox}});nwr["ref:INSEE"="38129"]({{bbox}});nwr["ref:INSEE"="26113"]({{bbox}});nwr["ref:INSEE"="26117"]({{bbox}});nwr["ref:INSEE"="38153"]({{bbox}});nwr["ref:INSEE"="38169"]({{bbox}});nwr["ref:INSEE"="26141"]({{bbox}});nwr["ref:INSEE"="26142"]({{bbox}});nwr["ref:INSEE"="38186"]({{bbox}});nwr["ref:INSEE"="38187"]({{bbox}});nwr["ref:INSEE"="38195"]({{bbox}});nwr["ref:INSEE"="38205"]({{bbox}});nwr["ref:INSEE"="26159"]({{bbox}});nwr["ref:INSEE"="26163"]({{bbox}});nwr["ref:INSEE"="26168"]({{bbox}});nwr["ref:INSEE"="38216"]({{bbox}});nwr["ref:INSEE"="26175"]({{bbox}});nwr["ref:INSEE"="38225"]({{bbox}});nwr["ref:INSEE"="38235"]({{bbox}});nwr["ref:INSEE"="38243"]({{bbox}});nwr["ref:INSEE"="38248"]({{bbox}});nwr["ref:INSEE"="26217"]({{bbox}});nwr["ref:INSEE"="38281"]({{bbox}});nwr["ref:INSEE"="26221"]({{bbox}});nwr["ref:INSEE"="26223"]({{bbox}});nwr["ref:INSEE"="38301"]({{bbox}});nwr["ref:INSEE"="26240"]({{bbox}});nwr["ref:INSEE"="26246"]({{bbox}});nwr["ref:INSEE"="38319"]({{bbox}});nwr["ref:INSEE"="38322"]({{bbox}});nwr["ref:INSEE"="38333"]({{bbox}});nwr["ref:INSEE"="38338"]({{bbox}});nwr["ref:INSEE"="26270"]({{bbox}});nwr["ref:INSEE"="26282"]({{bbox}});nwr["ref:INSEE"="38345"]({{bbox}});nwr["ref:INSEE"="26290"]({{bbox}});nwr["ref:INSEE"="38355"]({{bbox}});nwr["ref:INSEE"="26291"]({{bbox}});nwr["ref:INSEE"="38356"]({{bbox}});nwr["ref:INSEE"="38390"]({{bbox}});nwr["ref:INSEE"="38391"]({{bbox}});nwr["ref:INSEE"="26307"]({{bbox}});nwr["ref:INSEE"="26308"]({{bbox}});nwr["ref:INSEE"="26309"]({{bbox}});nwr["ref:INSEE"="38409"]({{bbox}});nwr["ref:INSEE"="26311"]({{bbox}});nwr["ref:INSEE"="38419"]({{bbox}});nwr["ref:INSEE"="26315"]({{bbox}});nwr["ref:INSEE"="26316"]({{bbox}});nwr["ref:INSEE"="38429"]({{bbox}});nwr["ref:INSEE"="26320"]({{bbox}});nwr["ref:INSEE"="38433"]({{bbox}});nwr["ref:INSEE"="38436"]({{bbox}});nwr["ref:INSEE"="38438"]({{bbox}});nwr["ref:INSEE"="38443"]({{bbox}});nwr["ref:INSEE"="38450"]({{bbox}});nwr["ref:INSEE"="38453"]({{bbox}});nwr["ref:INSEE"="26331"]({{bbox}});nwr["ref:INSEE"="26299"]({{bbox}});nwr["ref:INSEE"="26302"]({{bbox}});nwr["ref:INSEE"="38474"]({{bbox}});nwr["ref:INSEE"="38485"]({{bbox}});nwr["ref:INSEE"="38486"]({{bbox}});nwr["ref:INSEE"="26354"]({{bbox}});nwr["ref:INSEE"="26359"]({{bbox}});nwr["ref:INSEE"="38524"]({{bbox}});nwr["ref:INSEE"="26364"]({{bbox}});nwr["ref:INSEE"="38540"]({{bbox}});nwr["ref:INSEE"="38548"]({{bbox}});out geom;',
    });
    const answer = await api.json();
    console.log(answer);
  },
  methods: {
    fetchData() {
      const data = new URLSearchParams();
      data.append("data", this.query);
      data.append("bbox", this.bbox);

      fetch(this.url, {
        method: "POST",
        body: data,
      })
        .then((response) => {
          if (!response.ok) {
            throw new Error(`Request failed with status: ${response.status}`);
          }
          return response.json();
        })
        .then((data) => {
          // Process the data returned from the API
          this.apiResponse = data;
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
};
</script>
