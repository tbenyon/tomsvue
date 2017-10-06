<template>
  <div class="test">
    <input type="text" v-on:keyup="pressed_key" v-on:keyup.enter="enter_hit"><br>
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.first_name}} {{user.last_name}}</p>
    <p v-else>Nothing to see here!</p>
    <p v-text="user.first_name"></p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>

    <button v-on:click="greet('tombo')">Say Greeting</button>

    <br><br><br>
    <label>First Name</label><br><input type="text" v-model="user.first_name"><br>
    <label>Last Name</label><br><input type="text" v-model="user.last_name"><br>
    <label>Full Name: {{full_name}}</label>
    <br><br><br>
    <label>Got to 37:51 on <a href="https://youtu.be/z6hQqgvGI4Y?t=37m51s">video</a>.</label>

  </div>
</template>

<script>
  export default {
    name: 'test',
    data() {
      return {
        title: 'Hello World Dave',
        user: {
          first_name: "John",
          last_name: "Benyon"
        },
        showName: true,
        items: [
          {title: "pet"},
          {title: "fish"},
          {title: "dog"}
        ]
      }
    },
    methods: {
      greet: function (greeting) {
        alert(greeting);
      },
      pressed_key: function (e) {
        console.log(e.target.value);
      },
      enter_hit: function () {
        console.log("you hit enter");
      }
    },
    computed: {
      full_name: function () {
        return this.user.first_name + " " + this.user.last_name
      }
    }
  }
</script>

<style scoped>

</style>
