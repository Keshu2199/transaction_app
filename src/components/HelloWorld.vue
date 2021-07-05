<template>
  <div>
    <h1>Welcome to Transaction App</h1>
    <table class="table1" border="2px">
      <tr>
        <th>Date</th>
        <th>Description</th>
        <th>Credit</th>
        <th>Debit</th>
        <th>Running Balance</th>
      </tr>
      <tr>
        <td>02/07/2020</td>
        <td>Misc Expenses</td>
        <td></td>
        <td>3000</td>
        <td>2000</td>
      </tr>
      <tr>
        <td>01/07/2020</td>
        <td>Self Credit</td>
        <td>5000</td>
        <td></td>
        <td>5000</td>
      </tr>
    </table>
    <div style="margin-top: 50px">
      <button @click="createNote()" class="button button1">
        + Add Transaction
      </button>
      <!-- <button class="button button2">Save</button> -->
    </div>

    <v-dialog v-model="createModal" 
    transition="dialog-bottom-transition">
      <div class="modal">
        <h2>Add transaction here...</h2>
      </div>
    </v-dialog>

    
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  
  data: () => {
    return {
      createModal: false,
    };
  },

  methods: {
    createNote() {
      this.createModal = true;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.modal {
  background-color: rgba(216, 252, 235, 0.959);
  height: 300px;
  margin-left: 20%;
    width: 60%;
    border: solid;
}
.table1 {
  border-color: rgb(0, 0, 0);
  margin-left: auto;
  margin-right: auto;
  border-collapse: collapse;
  width: 60%;
}
th {
  background-color: #ffbb00;
  color: rgb(0, 0, 0);
}
th,
td {
  text-align: left;
  padding: 8px;
}
.button {
  background-color: #4caf50; /* Green */
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  border-radius: 12px;
  cursor: pointer;
}
.button1 {
  background-color: white;
  color: black;
  border: 2px solid #ffbb00;
}

.button1:hover {
  background-color: #ffbb00;
  color: black;
}
.button2 {
  background-color: white;
  color: black;
  border: 2px solid #008cba;
}

.button2:hover {
  background-color: #008cba;
  color: white;
}
</style>
