<template>
  <div class="hello">
    <h3>Country Name</h3>
    <ul v-if="country">
      <li>Name: {{ country.name }}</li>
      <li>Cuty: {{ country.capital }}</li>
      <li>Flag: {{ country.emoji }}</li>
      <li>Currency: {{ country.currency }}</li>
      <li>Language Code:{{ country.languages[0].code }}</li>
      <li>Language Name: {{ country.languages[0].name }}</li>
    </ul>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  name: "HelloWorld",
  apollo: {
    country: gql`
      query {
        country(code: "BD") {
          name
          native
          capital
          emoji
          currency
          languages {
            code
            name
          }
        }
      }
    `,
  },
  props: {
    msg: String,
  },
};
</script>

