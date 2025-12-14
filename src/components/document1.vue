<template>
  <div id="part1-documents" :class="background">
    <!-- <div v-if="page === 1" class="document1">

    </div> -->
    <div v-if="result !== ''" class="black-div"></div>
    <document class="document1" @result="sendResult" @to-end="toEnd"></document>
    <result class="result" :resultFrom="result" />
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
.marking2 {
  position: relative;
  top: 8.6rem;
  right: 15.2rem;
  width: 3.2rem;
  height: 1rem;
  border: solid 2px rgb(0, 0, 0);
  border-radius: 100%;
  opacity: 0;
  cursor: pointer;
}
.signature {
  width: 2rem;
  margin-top: -0.8rem;
  margin-right: 5rem;
  cursor: pointer;
  /* opacity: 0; */
}
.chosen {
  opacity: 1;
}
.up {
  display: flex;
  flex-direction: column;
  align-items: center;
  /* margin-top: -9rem; */
  /* gap: 1.8rem; */
}
.group1 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 3.6rem;
  gap: 1.8rem;
}
.input {
  position: relative;
  /* margin-top: 7rem; */
  right: 4rem;
  width: 2.7rem;
  height: 0.7rem;
  /* border: solid 2px; */
  border-radius: 5px;
  font-size: 0.7rem;
}
.inputUp {
  position: relative;
  top: -3.5rem;
  right: 10.8rem;
  width: 2.7rem;
  height: 0.5rem;
  border-radius: 5px;
  font-size: 0.7rem;
}
.group2 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 0.5rem;
  margin-right: 11.5rem;
  gap: 0.8rem;
}
.group3 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 1.8rem;
  margin-right: 1rem;
  gap: 2.6rem;
}
.jobA {
  width: 4rem;
  position: relative;
  top: 1.7rem;
  left: 17.5rem;
  border-radius: 5px;
}
.confirmation-dateA {
  width: 3rem;
  position: relative;
  top: 3rem;
  left: 12.5rem;
  border-radius: 5px;
}
.confirmation-signatureA {
  width: 2rem;
  position: relative;
  top: 2.7rem;
  left: 13rem;
  /* opacity: 0; */
}
.group4 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 4.9rem;
  margin-right: 4.2rem;
  gap: 1.5rem;
}
.input-statementB {
  width: 2rem;
  border-radius: 5px;
  height: 0.8rem;
}
.input-marked-statementB {
  width: 3rem;
  border-radius: 5px;
  height: 0.8rem;
  position: relative;
  right: 11rem;
}
.input-date-statementB {
  width: 2rem;
  border-radius: 5px;
  height: 0.6rem;
  position: relative;
  top: 1.2rem;
  left: 12.8rem;
}
.group5 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 1.9rem;
  margin-right: -1.3rem;
  gap: 2rem;
}
.statement-signatureB {
  width: 2rem;
  position: relative;
  top: -0.5rem;
  right: 5rem;
  /* opacity: 0; */
}
.group6 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 1.5rem;
  margin-right: 1rem;
  gap: 2.6rem;
}
.jobB {
  width: 4rem;
  position: relative;
  top: 1.5rem;
  left: 17.5rem;
  border-radius: 5px;
}
.confirmation-dateB {
  width: 3rem;
  position: relative;
  top: 3rem;
  left: 12.5rem;
  border-radius: 5px;
}
.confirmation-signatureB {
  width: 2rem;
  position: relative;
  top: 2.7rem;
  left: 13rem;
  /* opacity: 0; */
}
.group7 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 1.5rem;
  margin-right: 1rem;
  /* gap:2.6rem; */
}
.marked-resultTest {
  width: 3rem;
  position: relative;
  top: 3.5rem;
  right: 13rem;
  border-radius: 5px;
}
.date-resultTest {
  width: 3rem;
  position: relative;
  top: 3.5rem;
  right: 16rem;
  border-radius: 5px;
}
.input-resultTest {
  width: 3rem;
  position: relative;
  top: 5rem;
  left: 4rem;
  border-radius: 5px;
  margin-left: 2rem;
}
.input-resultTest-unit {
  width: 3rem;
  margin-right: 2rem;
}
.drugKind {
  width: 3rem;
  border-radius: 5px;
  margin-top: 6.5rem;
  margin-right: 19rem;
}
.checkbox0 {
  position: relative;
  left: 20.2rem;
}
.checkbox1 {
  position: relative;
  top: 3.2rem;
  left: 21.2rem;
}
.checkbox2 {
  position: relative;
  top: 4.2rem;
  left: 22.2rem;
}
.group9 {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-top: 5.5rem;
  margin-right: 2.3rem;
  gap: 0.2rem;
}
.input-giver {
  width: 1.8rem;
  border-radius: 5px;
}
.input-checker {
  width: 1.8rem;
  border-radius: 5px;
}
.input-checker0 {
  margin-right: 4rem;
}
.giver-SignatureC {
  width: 2rem;
  position: relative;
  top: -1.5rem;
  right: 12rem;
  /* opacity: 0; */
}
.checker-signatureC {
  width: 2rem;
  position: relative;
  top: -1.5rem;
  right: 23.5rem;
  /* opacity: 0; */
}

.button-next {
  position: absolute;
  bottom: 2rem;
  left: 0.1rem;
  width: 2.2rem;
  cursor: pointer;
}
.disabled-btn {
  opacity: 0.5;
  pointer-events: none;
  cursor: not-allowed;
}
.infoBtn {
  position: absolute;
  bottom: 41rem;
  left: 36.5rem;
  border: none;
  width: 10rem;
  text-align: center;
  color: white;
  font-size: 1rem;
  font-weight: bold;
  border-radius: 1rem;
  font-family: "rubik";
  padding: 0.5rem;
  background-color: #0e2c8e;
  filter: drop-shadow(0 0 10px #0051ff);
  cursor: pointer;
}

.infoBtn:hover {
  background-color: #0e277a;
}
.infoBtn:active {
  background-color: #123199;
}
.container-details {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.details {
  width: 16rem;
  position: absolute;
  top: 5rem;
  right: 36rem;
}

.detailBtn {
  position: absolute;
  height: 1rem;
  right: 36.5rem;
  top: 1rem;
  width: 5rem;
  z-index: 3;
  padding: 12px 0px;
  background-color: white;
  border-radius: 30%;
  text-align: center;
  color: white;
  font-size: 1rem;
  font-weight: bold;
  border-radius: 1rem;
  font-family: "rubik";
  background-color: #0e2c8e;
  filter: drop-shadow(0 0 10px #0051ff);
  cursor: pointer;
}
.detailBtn:hover {
  background-color: #0e277a;
}
.detailBtn:active {
  background-color: #123199;
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
</style>
