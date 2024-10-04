<template>
  <ChildRen names="VenuGopal"></ChildRen>
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
  <input type="text" v-model="emails" />
  <input type="text" v-model="pass">
  <h6>{{ sam }}</h6>
  <h5>{{ emails }}</h5>
  <h4>{{ pass }}</h4>
  <button v-on:click="getWarn()">Get Details</button>
  <h2>Technology</h2>
  <input type="checkbox" value="java" id="java" v-model="tech">
  <label for="java">Java</label>
  <input type="checkbox" value="c" id="c" v-model="tech">
  <label for="c">C</label>
  <input type="checkbox" id="csharp" value="csharp" v-model="tech">
  <label for="csharp">csharp</label><br><br>
  <input type="radio" value="Developer" id="dev" v-model="profession">
  <label for="dev">Developer</label>
  <input type="radio" value="Student" id="stud" v-model="profession">
  <label for="stud">Student</label>
  <h2>{{ tech }}</h2>
  <h1>{{ profession }}</h1>
  <h1 v-if="show">If Condition in vue js</h1>
  <h1 v-else>else part in vue js</h1>
  <button v-on:click="show = !show">Condition</button>
  <h2>For Loop</h2>
  <ul>
    <li id="techstacks" v-for="item in techstacks" :key="item">
      {{ item }}
    </li>
  </ul>
  <br>
  <ol>
    <li id="user" v-for="items in users" :key="items">
      User Name is : {{ items.name }} and Email is : {{ items.email }}
    </li>
  </ol>
</template>

<script>
import ChildRen from './Child.vue'
export default {
  name: 'venuGopal',
  components:{
    ChildRen

  },
  data() {
    return {
      email: 'venugopal@gmail.com',
      mobile: 9080368568,
      count: 0,
      sam: 0,
      emails: null,
      pass: null,
      tech: [],
      techstacks: ['HTML', 'CSS', 'JAVA', 'NODE'],
      users: [{
        name: 'anand',
        email: 'anand@gmail.com'
      },
      {
        name: 'arun',
        email: 'arun@gmail.com'
      },
      {
        name: 'dinesh',
        email: 'dinesh@gmail.com'
      },
      ],
      profession: null,
      show: true,
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
    getWarn() {
      alert(this.emails + " " + this.pass);
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
