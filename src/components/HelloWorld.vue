<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" placeholder="What is that you desire the most ?" @keypress.enter="addNote">
    <ul v-for="( note , index ) in notes" :key="note">
      <li>
        {{note}}
      </li>
      <div class="remove_item" @click="removeitem(index)">
        &times;
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to ToDOS App',
      notes: []
    }
  },
  methods: {
    addNote (event) {
      this.notes.push(event.target.value)
      event.target.value = ''
    },
    removeitem (index) {
      this.notes.splice(index, 1)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

input{
 margin: 30px;
 padding: 15px;
 width: 14%;
 height: 15%;
}

.remove_item{
  size: 150px;
  display: inline-flex;
  padding: 0;
}

</style>
