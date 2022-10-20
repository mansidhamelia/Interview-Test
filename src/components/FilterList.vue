<template>
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
      <li v-for="data in result">{{ data.item }}</li>
    </ul>
  </div>
</template>

<style scoped>
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
</style>
