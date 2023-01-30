<template>
  <div id="app">
    <div id="totalcontainer">
      <div id="inputdetails">
        <div id="input1">
          <div id="cardback">
            <img id="cardbackimg" src="../src/assets/bg-card-back.png" alt="" />
            <p id="p4">{{ p4 }}</p>
          </div>
          <div id="cardfront">
            <img
              id="cardfrontimg"
              src="../src/assets/bg-card-front.png"
              alt=""
            />
            <img id="logo" src="../src/assets/card-logo.svg" alt="" />
            <p id="p1">{{ p1 }}</p>
            <p id="p2">{{ p2 }}</p>
            <div id="p3">
              <span>{{ MM }}</span
              >/<span></span><span>{{ YY }}</span>
            </div>
          </div>
        </div>
        <div id="input2" v-if="!confirm">
          <div id="spare"></div>
          <div class="inputarea" id="ïnputarea1">
            <label>CARDHOLDER NAME</label>
            <input type="text" v-model="p2" placeholder="Jane Appleseed" />
          </div>

          <div id="cardnumber" class="inputarea">
            <label>CARD NUMBER</label>
            <input
              type="text"
              v-model="p1"
              placeholder="e.g. 1234 5678 9123 0000"
            />
          </div>

          <div id="inputnumbers">
            <div class="numberslabel">
              <label for="">EXP. DATE</label>
              <input
                class="smallinputs"
                v-model="MM"
                type="text"
                placeholder="MM"
              />
            </div>
            <div class="numberslabel">
              <label for="">(MM/YY)</label>
              <input
                class="smallinputs"
                v-model="YY"
                type="text"
                placeholder="YY"
              />
            </div>
            <div class="numberslabel">
              <label for="">CVC</label>
              <input
                class="smallinputs"
                v-model="p4"
                type="text"
                placeholder="e.g. 123"
              />
            </div>
          </div>
          <div class="button" @click="confirm = !confirm">
            <button>Confirm</button>
          </div>
        </div>
      </div>

      <!-- Completed state start -->
      <transition>
        <div id="thankyou" v-if="confirm">
          <div id="spare"></div>
          <div>
            <img
              id="completeimg"
              src="../src/assets/icon-complete.svg"
              alt=""
            />
            <!-- </div>
        <div> -->
            <p id="thankp">THANK YOU!</p>
            <p id="wep">We've added your card details</p>
            <div class="button">
              <button id="continue" @click="confirm = !confirm">Continue</button>
            </div>
          </div>
        </div>
      </transition>

      <div class="attribution">
        Challenge by
        <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
          >Frontend Mentor</a
        >. Coded by <a href="#">Bage Silas</a>.
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      confirm: false,
      p1: "0000 0000 0000 0000",
      p2: "JANE APPLESEED",
      p3: "00/00",
      p4: "000",
      MM: "00",
      YY: "00",
    };
  },
  methods: {},
  computed: {},
};
</script>

<style scoped>
</style>
