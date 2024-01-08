<template>
  <h1>This is Home Page Component.</h1>
  <p>Name: {{getName()}} -- Last Name: {{ lastNameWithParams("Hasan Shourav")}} -- Email: {{email}} -- Mobile: {{mobile}}</p>
  <p>Profession: {{profession("Web Developer")}} -- Specific: {{ profession("Laravel Developer")}}</p>
  <p>All Data: {{ getData() }}</p>
  <p>Age: {{ getData().age }},, Address: {{ getData().address}},, Email: {{ getData().email}},, Name: {{ getData().name}}</p>
  <br>
  <h3>Events</h3>

  <button v-on:click="clickOneTest('Button 1 Clicked')">Click Me 1</button>
  <button v-on:dblclick="clickOneTest('Button 2 Clicked')">Click Me 2</button>
  <h3 v-on:mousemove="mouseMoveTest()">Ekhane mouse alne kichu ekta hobe console e.</h3>
  <button v-on:click="countIncrease()">Click me to increase count</button>
  <p><b>{{count}}</b></p>
  
  <h3>Two Way Binding</h3>

  <input type="text" v-model="bindCount">
  <h3>{{bindCount}}</h3>
  <hr>

  <h3>Get Input field Value</h3>
  <p>Name: <input type="text" placeholder="Enter Name" v-model="inputEmail"></p>
  <p>Password: <input type="password" placeholder="Enter Password" v-model="inputPassword"></p>
  <button type="button" v-on:click="getInputValues()">Get the input fields value</button>
  <p> Text: {{ displayEmail }} || Password: {{ displayPassword}}</p>
  <br>
  <hr>

  <h3> Get Checkbox & Radio Button Value </h3>
  <h4>Language:</h4>
  <label for="java">Java</label>
  <input type="checkbox" class="ml-4" value="Java" name="java" id="java" v-model="technology">

  <label for="php">php</label>
  <input type="checkbox" class="ml-4" value="PHP" name="php" id="php" v-model="technology">

  <label for="laravel">laravel</label>
  <input type="checkbox" class="ml-4" value="Laravel" name="laravel" id="laravel" v-model="technology">
  <br>

  <h4>Who am I:</h4>
  <input type="radio" name="profession" id="Student" value="student" v-model="whoAmI">
  <label for="Student">Student</label>
  <input type="radio" name="profession" id="Developer" value="developer" v-model="whoAmI" >
  <label for="Developer">Developer</label>

  <h4>Selected Language: {{ technology }}</h4>
  <h4>Profession: {{whoAmI}}</h4>
  <hr>

  <h4>IF Else Conditions</h4>
  <p v-if="show=='abc'">Show if condition statement</p>
  <p v-else>Show else condition statement</p>
  <br>
  <h4>Conditions Toggle</h4>
  <p v-if="toggle">Show if condition statement</p>
  <p v-else>Show else condition statement</p>
  <button v-on:click="toggle=!toggle">Toggle Conditions</button>
  <hr>

  <h4>For Loop</h4>
  <p>Showing the birds:</p>
  <ul>
    <li v-for="items in birds" :key="items">
      {{items}}
    </li>
  </ul>

  <p>Showing the users with multiple information:</p>
  <ul>
    <li v-for="(items, dIdx) in users" :key="dIdx">
      {{dIdx+1}}. Name: {{items.name}} , Email: {{items.email}} , Password: {{items.password}},  <br>
      <p>Phone1: {{items.phone.phone1}} -- Phone2: {{items.phone.phone2}}</p>
    </li>
  </ul>
  <hr>

  <h4>Showing Child Component to HopagePage</h4>
  <ChildComponent text="i am passing this text to child component" :childUser="childUser" :parentFun="callParent" />


</template>

<script>
import ChildComponent from "@/components/ChildComponent.vue";
export default {
  name: 'HomePage',
  components: {
    ChildComponent,
  },

  data(){
    return {
      email: "Shykot@gmail.com",
      mobile: "123456",
      getName:function()
      {
        return "I am Shykot";
      },
      lastNameWithParams:function(a)
      {
        return a;
      },
      count: 0,
      bindCount: 'This is two way binding..',
      inputEmail: 'shykot',
      inputPassword: '12345678',
      displayEmail: '',
      displayPassword: '',

      technology: [],
      whoAmI: null,

      show: 'abc',
      toggle: true,

      birds: ['pigeon','crow','doel','sprraw'],

      users: [
        {
          'name' : 'Shykot',
          'email' : 'shykot@gmail.com',
          'password' : '123456',
          'phone' : {
            'phone1' : '0162',
            'phone2' : '0187',
          }
        },
        {
          'name' : 'Hasan',
          'email' : 'hasan@gmail.com',
          'password' : '123456',
          'phone' : {
            'phone1' : '0162',
            'phone2' : '0187',
          }
        },
        {
          'name' : 'Shourav',
          'email' : 'shourav@gmail.com',
          'password' : '123456',
          'phone' : {
            'phone1' : '0162',
            'phone2' : '0187',
          }
        },
      ],
      childUser: {'name': 'child artisat', 'address': 'Dhaka' },


    }
  },
  methods: {
    // profession(){
    //   return "Web Developer";
    // },
    profession(pro){
      return pro;
    },
    getData(){
      return {
        age: "25",
        address: "Narayanganj",
        email: this.email, //data() theke access er niyom
        name: this.getName(), // data theke function access evabe kore.
      }
    },
    clickOneTest(btn){
      // alert(this.email);
      // confirm(this.getData().name)
      alert(btn) ;
    },
    mouseMoveTest(){
      console.log("Move Function Called");
    },
    countIncrease(){
      this.count = this.count+1;
    },
    getInputValues(){
      console.log("text: ",this.inputEmail, "password: ", this.inputPassword) // console log eo value dekhabe abar text: & password: eo dekhabe.
      this.displayEmail = this.inputEmail;
      this.displayPassword = this.inputPassword;
    },
    callParent(){
      alert("Child Function called")
    },


  }

}
</script>

<style scoped>
h1 {
  color: orange;
}
</style>