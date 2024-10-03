<template>
  <img alt="images" src="../assets/yes.png">
  <h1 v-on:mousemove="getConsole()">Home Component length of {{ "Digital" }} is {{ "Digital".length }}</h1>
  <h1>{{ message }}</h1>
  <h1>{{ email }}</h1>
  <h1>{{ mobile }}</h1>
  <h2>Address : {{ getAddress("Sivakasi") }}</h2>
  <h3>{{ getData().text }} {{ getData().year }}</h3>
  <h4>{{ getData().disp }}</h4>
  <button v-on:click="getNotify()">Click Me</button>
  <button v-on:click="getNotify('Button 1 Click')">Click</button>
  <button v-on:dblclick="getDouble('Button 2 Double Click')">Click Here</button>
  <button v-on:click="getCount()">Count</button>
  <button v-on:click="getDecrease()">Decrease</button>
  <h1>{{ count }}</h1>
  <input type="text" v-model="sam" />
  <input type="text" v-model="emails"/>
  <input type="text" v-model="pass">
  <h6>{{ sam }}</h6>
  <h5>{{ emails }}</h5>
  <h4>{{ pass }}</h4>
  <button v-on:click="getWarn()">Get Details</button>

</template>

<script>
export default {
  name: 'venuGopal',
  data() {
    return {
      email: 'venugopal@gmail.com',
      mobile: 9080368568,
      count: 0,
      sam: 0,
      emails: null,
      pass: null,
      getAddress(address) {
        return address
      }
    }
  },
  methods: {
    getData() {
      return {
        disp: this.email,
        text: 'Copyright',
        year: '@2024'
      }
    },
    getNotify() {
      alert("Function Called")
    },
    getDouble() {
      alert("Double click function called")
    },
    getConsole() {
      console.log("Event is fired");
    },
    getCount() {
      this.count = this.count + 1;
    },
    getDecrease() {
      this.count = this.count - 1;
    },
    getWarn(){
      alert(this.emails +" "+this.pass);
    }
  },


  props: {
    message: String
  }
}


</script>


<style>
h1 {
  color: rgb(38, 1, 250);
}
</style>
