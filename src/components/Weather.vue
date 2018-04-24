<template>
  <div>
    <section>
      <div class="container">
        <div class="section-one">
          <div class="searchbox">
            <button>
              <i class="fas fa-search"></i>
            </button>
            <input v-model="isFocus" class="input" placeholder="Search" type="text">
            <button>
              <i class="fas fa-times"></i>
            </button>
            <hr>
          </div>
          <div>
            <div style="display: flex; justify-content: center; align-content: center;">
              <h1>
                <!-- <h1 v-show="curTempDisplay"> -->
                {{ 13 }}
                <!-- <i class="wi" :class="[classWI]"></i> {{ curTempDisplay }} -->
                <!-- <span class="btn btn-deg" :class="{ 'btn-deactivate': displayMode }" @click="getTemp(0)">°C</span> | -->
              </h1>
                <span class="info-text">°F</span>
                <div class="weather-info">
                  <span class="info-text">Clear Skies</span>
                  <span class="info-text">52% Humidity</span>
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
export default {
  name: 'Weather',

  data() {
    return {}
  },
  methods: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
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
  background: rgba(0, 0, 0, 0.1);
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
  padding: 0.3rem 1.5rem;
  &:focus {
    outline: none;
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
  background: #367cd6;
  padding: 1rem 2rem;
  span {
    font-size: 1.3rem;
    margin: 0.3rem 0;
  }
}

.section-two {
  padding: 2rem;
  display: flex;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
  div {
    padding: 0.4rem 0.7rem;
    font-size: 1rem;
  }
  .line {
    border: none;
    background: rgba(0, 0, 0, 0.1);
    width: 1px;
    margin: 0.2rem 0;
  }
}

h1 {
  font-size: 6rem;
}
</style>
