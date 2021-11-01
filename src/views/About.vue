<template>
  <div class="hello">
    <h3>Country Name</h3>
    <ul v-if="getCityByName">
      <li>City ID: {{ getCityByName.id }}</li>
      <li>City Name: {{ getCityByName.name }}</li>
      <li>Country Name: {{ getCityByName.country }}</li>
      <li>Country coordinate Lon: {{ getCityByName.coord.lon }}</li>
      <li>Country coordinate Lat: {{ getCityByName.coord.lat }}</li>
      <li>Weather Title: {{ getCityByName.weather.summary.title }}</li>
      <li>Weather Description: {{ getCityByName.weather.summary.description }}</li>
      <li>Weather icon: {{ getCityByName.weather.summary.icon }}</li>
      <li>Temperature actual: {{ getCityByName.weather.temperature.actual }}</li>
      <li>Temperature feelsLike: {{ getCityByName.weather.temperature.feelsLike }}</li>
      <li>Temperature Min: {{ getCityByName.weather.temperature.min }}</li>
      <li>Temperature Max: {{ getCityByName.weather.temperature.max }}</li>
      <li>Wind Speed: {{ getCityByName.weather.wind.speed }}</li>
      <li>Wind Deg: {{ getCityByName.weather.wind.deg }}</li>
      <li>Clouds All: {{ getCityByName.weather.clouds.all }}</li>
      <li>Clouds visibility: {{ getCityByName.weather.clouds.visibility }}</li>
      <li>Clouds humidity: {{ getCityByName.weather.clouds.humidity }}</li>
      <li>Time Stamp: {{ getCityByName.weather.timestamp }}</li>
    </ul>
  </div>
</template>

<script>
import gql from "graphql-tag";
export default {
  name: "HelloWorld",
  apollo: {
    $client: "b",
    getCityByName: gql`
      query {
        getCityByName(name: "Dhaka") {
          id
          name
          country
          coord {
            lon
            lat
          }
          weather {
            summary {
              title
              description
              icon
            }
            temperature {
              actual
              feelsLike
              min
              max
            }
            wind {
              speed
              deg
            }
            clouds {
              all
              visibility
              humidity
            }
            timestamp
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

