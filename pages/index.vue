<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md-12>
      <v-card class="my-10">
        <!-- title and description -->
        <p class="display-3 text--primary">
          Calculator Demo
        </p>
        <div class="body-1 text--primary">
          Choose an operator, type two numbers in and press calculate
        </div>
        <v-form ref="form">
          <br />
          <!-- create operator buttons -->
          <v-btn
            v-for="operator in operators"
            :class="{
              highlight: operator == selected
            }"
            @click="selected = operator"
            :key="operator.id"
            :depressed="selected == operator"
            class="mx-1"
            tile
            x-large
          >
            {{ operator }}
          </v-btn>
          <!-- create number inputs -->
          <div class="my-8">
            <v-text-field
              v-model="num1"
              label="Input 1"
              type="number"
              hide-details
            ></v-text-field>
            <v-text-field
              v-model="num2"
              label="Input 2"
              type="number"
              hide-details
            ></v-text-field>
          </div>
          <!-- calulate button -->
          <v-btn @click="calculate" x-large>Calculate</v-btn>
        </v-form>
        <br /><br />
        <hr />
        <br /><br />
        <!-- result section -->
        <transition name="fade" mode="out-in">
          <div v-if="calculated">
            <div class="display-1">Result:</div>
            <v-card flat>
              <div class="display-1 pa-5 my-3 result">
                {{ result }}
              </div>
            </v-card>
          </div>
        </transition>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      operators: ['Addition', 'Subtraction', 'Exponentiation'],
      num1: undefined,
      num2: undefined,
      selected: undefined,
      result: undefined,
      calculated: false
    }
  },
  methods: {
    calculate() {
      // popup alert if user has not selected an operator or number
      if (this.selected === undefined) {
        return alert('Please select an operator')
      } else if (this.num1 === undefined || this.num2 === undefined) {
        return alert('Please select a number')
      }
      // perform calculation based on selected operator
      if (this.selected === 'Addition') {
        this.result = parseFloat(this.num1) + parseFloat(this.num2)
      } else if (this.selected === 'Subtraction') {
        this.result = parseFloat(this.num1) - parseFloat(this.num2)
      } else {
        this.result = parseFloat(this.num1) ** parseFloat(this.num2)
      }
      // set to true to reveal result
      this.calculated = true
    }
  }
}
</script>

<style scoped>
.highlight {
  background-color: rgb(218, 150, 86) !important;
  color: white;
}

.v-text-field {
  height: 4rem;
  font-size: 1.5rem;
}

.result {
  background-color: rgb(202, 202, 202);
  border: solid black 1px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}

.my-10 {
  padding: 50px 50px;
}
</style>
