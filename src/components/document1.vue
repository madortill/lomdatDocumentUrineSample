<template>
  <div id="part1-documents" :class="background">
    <!-- <div v-if="page === 1" class="document1">

    </div> -->
    <div v-if="result !== ''" class="black-div"></div>
    <document class="document1" @result="sendResult" @to-end="toEnd"></document>
    <result class="result" :resultFrom="result" />
    <button class="back-btn" @click="$emit('back-to-info')">
  חזרה לפרטים
</button>
    <!-- <div class="contaner-details">
      <p class="detailBtn" @click="isOpen = !isOpen">
        {{ isOpen ? "סגירה" : "פרטים" }}
      </p>
      <details-box v-show="isOpen" class="details"></details-box>
    </div> -->
    <!-- <img
      src="@/assets/media/part1documents/nextBtn.png"
      @click="check1"
      class="button-next"
      :disabled="!debugMode && !validateAllFields()"
      :class="{ 'disabled-btn': !debugMode && !validateAllFields() }"
      alt="btn"
    /> -->

    <!-- <button class="infoBtn" @click="openInfo">
      {{ isInfoOpen ? "סגירה" : "דגשים למילוי" }}
    </button>
    <information v-if="isInfoOpen" class="information"></information> -->
  </div>
</template>

<script>
import Information from "./Information.vue";
import DetailsBox from "./DetailsBox.vue";
import document from "./document.vue";
import result from "./result.vue";
export default {
  components: {
    Information,
    DetailsBox,
    document,
    result
  },
  data() {
    return {
      inputs: [],
      reasonAnswer: "",
      roomUser: "",
      result: "",
      isOpen: false,
      isInfoOpen: false,
    };
  },
  methods: {
    sendResult(res) {
      this.result = res;
    },
    toEnd() {
      this.$emit("to-end");
    },
    openInfo() {
      this.isInfoOpen = !this.isInfoOpen;
    },
  },
};
</script>

<style scoped>
.document1 {
  height: 95vh;
}
.result {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
}

.black-div {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.623);
  pointer-events: none;
}
.back-btn {
  font-family: "rubik";
  font-weight: bold;
  font-size: 1rem;
  background-color: #be0000;
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  color: white;
  cursor: pointer;
  border: none;
  position: fixed;
  right: 1%;
  z-index: 3;
}

</style>
