/* eslint-disable */
<template>
  <div>
<!-- We are Binding Text in Vue i.e we are adding text to our template(html) 
we could add this for dynamically changing text by including the text properties in the data() method
 which returns a key-value pair 
this is the Moustache Syntax-->
  <!-- <div>{{name}} {{greet}}</div> -->
<!-- Another way to bind data is by using the  v-text directive
it is important to note however that v-text is one of the least used directives in vue
-->
<!-- Short Comings -->
<!-- Allows only one data element unlike moustache syntax SO it would override the div contents-->
<!-- <div v-text ="name2"></div> -->

<!-- we can bind html as well look for the case of a data object classic
we us the v-html directive -->
  <!-- <div v-html="classic"></div> -->
  <!-- <p>binding html without the v-html dirextive</p> -->
  <!-- <div v-text="classic"></div> -->
  <!-- <div>{{classic}}</div> -->
  <!-- BINDING ATTRIBUTES OF THE HTML  -->
  <!-- <div :class="paraid"> PARAGRAPH ID</div>  -->
  <!-- <div :class="paraid"> PARAGRAPH ID</div> -->
  <!-- <div :class="paraid"> PARAGRAPH ID</div> -->

  <!-- <p>HELLO WE ARE GOING TO SEE CONDITIONAL RENDERING USING THE 'v-else-if="condition"' directive</p> -->
  <!-- <h2 v-if="number>0">The Number is positive and {{number}}</h2> -->
  <!-- <h2 v-else-if="number<0">The Number is negative and {{number}}</h2> -->
  <!-- <h2 v-else>The Number is zero and and  {{number}}</h2> -->
  <!-- <h2 v-for="(name ,index) in names" :key="name">{{index}} {{name}}</h2> -->
  <!-- LIST RENDERING USING THE V-FOR DIRECTIVE -->
  <!-- <p>Full names using v -for</p> -->
  <!-- <h3 v-for="name in fullNames" :key="name">{{name.first}} {{name.last}}</h3> -->

 <!-- <h6>Array OF Arrrays</h6> -->
 <!-- <div v-for="play in players" :key="play"> -->
    <!-- <h1>{{play.player}}</h1> -->
    <!-- <h3 v-for="club in play.clubs" :key="club">{{club}}</h3> -->


    <h2>FORM HANDLING IN VUE</h2>
    <div>
      <pre>
        {{JSON.stringify(formValues,null,2)}}
      </pre>
    </div>
    <form @submit="submitform">
      <input type="text" id="name" v-model='formValues.employeename'/>
      <label for ='name'>Name</label>
      <hr/>
      <input type="text" id="email" v-model='formValues.email'/> 
       <!-- <div v-text="classic"></div>
      <div v-text="classic"></div> -->

      <label for="email">Email</label>
      <button type="submit"> SEND</button>
    </form>
 </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      formValues:{
        employeename :'',
        email:''
      },
      'name':'Douglas',
      'greet':'Good Afternoon',
      'name2':'Ivy',
      'classic':'<i>I am the binded HTML italicised</i>',
      'paraid':'my-para',
      'number':-6,
      'names' :['Douglas','Diana','Derrick'],
      'fullNames' :[
        {first:'Musinguzi',last:'Douglas' },
        {first:'Kemigabo',last:'Diana'},
        {first:'Senkatuuka',last:'Derrick'},
      ],
      players:[
        { player:'Antony Dos Santos',
          clubs:['Man U','Ajax','Santos']
      },
      {  player:'Neymar Junior dos Santos',
         clubs:['PSG','Barca','Santos']
      },
      { player:'Vinicius Junior',
        clubs:['Madrid','Brazil','Santos']
      },
      ]
    }
  },
  methods:{
    submitform(event){
      event.preventDefault();
      console.log('formValues',this.formValues)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
