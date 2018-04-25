<template>
  <div>
    <section>
      <div class="container">
        <div class="section-one">
          <div class="searchbox">
            <button @click="searchByCity">
              <i class="fas fa-search"></i>
            </button>
            <input v-model="city" class="input" placeholder="Search" type="text">
            <button @click="clearSearch">
              <i class="fas fa-times"></i>
            </button>
            <hr>
          </div>
          <div>
            <div style="display: flex; justify-content: center; align-content: center;">
              <h1>
                <!-- <h1 v-show="curTempDisplay"> -->
                {{ temprature }}
                <!-- <i class="wi" :class="[classWI]"></i> {{ curTempDisplay }} -->
                <!-- <span class="btn btn-deg" :class="{ 'btn-deactivate': displayMode }" @click="getTemp(0)">°C</span> | -->
              </h1>
                <span class="fah">°</span>
                <span class="fah">F</span>

                <div class="weather-info">
                          <span></span>
                          <span></span>
                          <span></span>
                          <span></span>
                          <span></span>
                  <span class="info-text">{{description}}</span>
                  <span class="info-text">{{humidity}}% Humidity</span>
                </div>
            </div>
          </div>
        </div>

        <div class="section-two">
          <div>
            <li>Jan 5</li>
            <li>
              <i class="fas fa-sun"></i>
            </li>
            <li>13</li>
            <li>-2</li>
          </div>
          <span class="line"></span>
          <div>
            <li>Jan 5</li>
            <li>
              <i class="fas fa-sun"></i>
            </li>
            <li>13</li>
            <li>-2</li>
          </div>
          <span class="line"></span>
          <div>
            <li>Jan 5</li>
            <li>
              <i class="fas fa-sun"></i>
            </li>
            <li>13</li>
            <li>-2</li>
          </div>
          <span class="line"></span>
          <div>
            <li>Jan 5</li>
            <li>
              <i class="fas fa-sun"></i>
            </li>
            <li>13</li>
            <li>-2</li>
          </div>
          <span class="line"></span>
          <div>
            <li>Jan 5</li>
            <li>
              <i class="fas fa-sun"></i>
            </li>
            <li>13</li>
            <li>-2</li>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'Weather',

  data() {
    return {
      city: '',
      temprature: '',
      description: '',
      humidity: '',
      key: '6a5a99aa870b51c7bcc6dd4e890dc690',
      lang: 'en',
      weatherUrl: 'http://api.openweathermap.org/data/2.5/forecast?',
      weatherIconUrl: 'http://openweathermap.org/img/w/'
    }
  },

  methods: {
    clearSearch() {
      this.city = ''
    },
    searchByCity() {
      // const data = res.data
      axios
        .get(
          `${this.weatherUrl}q=${this.city}&units=imperial&appid=${this.key}`
        )
        .then(
          res => (
            (this.description = res.data.list[0].weather[0].description),
            ((this.temprature = parseInt(res.data.list[0].main.temp)),
            (this.humidity = res.data.list[0].main.humidity))
          )
        )
      // .then(res => data.list)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
// Variables
$white: #f5f4f5;
$lightBorderDark: rgba(0, 0, 0, 0.1);
$lightBorderWhite: rgba(255, 255, 255, 0.4);

// Multiple Style

input,
button,
.section-one {
  background: transparent;
  color: $white;
  font-size: 1.2rem;
  text-transform: capitalize;
  i {
    color: #373f4a;
  }
  ::placeholder {
    color: $white;
  }
}

h1 {
  font-size: 8em;
}
section {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  border-radius: 0.6rem;
  align-self: center;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
}

.searchbox {
  display: flex;
  padding: 0.5rem 1rem;
  margin-bottom: 2rem;
}

hr {
  border: none;
  height: 1px;
  background: $lightBorderDark;
}

button {
  border: none;
  outline: none;
  cursor: pointer;
  &:hover {
    color: rgb(71, 71, 71);
  }
}

input {
  border: none;
  width: 100%;
  padding: 1rem;
  border-bottom: 1px solid $lightBorderDark;
  transition: border 200ms ease-in;
  &:focus {
    outline: none;
    border-bottom: 1px solid $lightBorderWhite;
  }
  &:active {
    border: none;
  }
}

.weather-info {
  display: flex;
  flex-direction: column;
}

.info-text {
  font-size: 0.6rem;
}

.section-one {
  padding: 1rem 3rem;
  .fah {
    font-size: 2.5rem;
  }
  span {
    font-size: 1.3rem;
    margin: 0.3rem 0;
  }
}

.section-two {
  background: $white;
  padding: 1rem 3rem;
  display: flex;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
  div {
    padding: 0.4rem 1rem;
    font-size: 1.5rem;
    li {
      padding: 0.2rem 0.5rem;
    }
  }
  .line {
    border: none;
    background: $lightBorderDark;
    width: 1px;
    margin: 0.2rem 0;
  }
}
</style>
