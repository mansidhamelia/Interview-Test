<template>
  <div class="">
    <h2>Search List</h2>
    <div>
      <input
        v-model="search"
        type="text"
        id="Input"
        placeholder="Search here...."
      />
    </div>

    <div>
      <ul id="myList">
        <li v-for="data in result">
          {{ data.item }} <a id="edit" @click="edit(data)"> Edit</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      search: '',
      editing: false,
      resources: [
        { item: 'Alpha', id: 1 },
        { item: 'Applet', id: 2 },
        { item: 'Aim' , id: 3 },
        { item: 'Bite', id: 4 },
        { item: 'ByteFury', id: 5 },
        { item: 'Cindy' ,id: 6 },
        { item: 'Chemistry', id: 7 },
        { item: 'Dog', id: 8 },
        { item: 'Eye',id:9 },
        { item: 'Elephant' , id: 10},

      ],
    }
  },
  computed: {
    result() {
      if (this.search) {
        return this.resources.filter((data) => {
          return this.search
            .toLowerCase()
            .split(' ')
            .every((v) => data.item.toLowerCase().includes(v))
        })
      } else {
        return this.resources
      }
    },
  },
methods:{

    edit(data){
       console.log(data.item,"aaa")
    this.search = data.item
    },

}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
h3 {
  margin: 40px 0 0;
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

#Input {
  width: 70%;
  font-size: 16px;
  padding: 12px 20px 12px 40px;
  border: 1px solid black;
  border-radius: 3px;
  margin-bottom: 12px;
  margin-left: 10%;
  margin-right: 10%;
}
input:hover {
  background-color: #ddd;
}
#myList {
  list-style-type: none;
  padding: 0;
  margin-left: 10%;
  margin-right: 10%;
}
#myList li {
  text-align: center;
  border: 1px solid #ddd;
  background-color: lightgray;
  padding: 12px;
  text-decoration: none;
  font-size: 18px;
  color: black;
  display: block;
}
#myList li:hover {
  background-color: rgb(149, 149, 149);
}

#edit {
}
</style>
