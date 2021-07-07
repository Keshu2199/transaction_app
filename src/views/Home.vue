<template>
  <div>
    <h1 style="text-align: center; margin-bottom: 30px">
      Welcome to Transaction App
    </h1>
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
      <button @click="createNote()" 
      class="button button1">
        + Add Transaction
      </button>
    </div>
    <div>
      <v-dialog v-model="createModal" 
      max-width="50%">
        <div style="border: solid">
          <div style="border-bottom: solid">
            <h2 style="background-color: #ffbb00; 
            text-align: center">
              Add transaction here...
            </h2>
          </div>
          <div class="modal">
            <v-form>
              <div style="text-align: center">
                <span style="font-size: 25px; 
                margin-right: 70px">
                  Transaction type:
                </span>
                <select
                  style="background-color: white; 
                  outline: auto; width: 200px;
                  padding-left: 5px;"
                  v-model="transType"
                >
                  <option disabled value="">
                    Please select one</option>
                  <option>credit</option>
                  <option>debit</option>
                </select>
                <br /><br />
                <span 
                style="font-size: 25px;
                 margin-right: 164px">
                  Amount:
                </span>
                <input
                  style="background-color: white; 
                  outline: auto; width: 200px;
                  padding-left: 5px;"
                  v-model="amount"
                  type="number"
                  min="0"
                />
                <br /><br />
                <span 
                style="font-size: 25px; 
                margin-right: 126px">
                  Description:
                </span>
                <input
                  style="background-color: white;
                   outline: auto; width: 200px;
                   padding-left: 5px;"
                  v-model="description"
                  type="text"
                />
              </div>
              <br /><br />
              <button class="button button2"
               @click="createModal=false">
                Cancel
              </button>
              <button class="button button2"
               @click="addTransaction()">
                Save
              </button>
            </v-form>
          </div>
        </div>
      </v-dialog>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",

  data: () => {
    return {
      
      createModal: false,
      
      transType: "",
      amount: "",
      description: "",
    
    };
  },

  methods: {
    createNote() {
      this.createModal = true;
    },

    addTransaction() {
      debugger;
      const obj1={
      transType:this.transType,
      amount: this.amount,
      description: this.description
      }
      
      console.log("Transaction_details---------",obj1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.modal {
  background-color: rgb(250, 242, 208);
  height: 300px;
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
  margin-left: 69%;
}

.button1:hover {
  background-color: #ffbb00;
  color: black;
}
.button2 {
  background-color: white;
  color: black;
  border: 2px solid #ffbb00;
  margin-left: 187px;
}

.button2:hover {
  background-color: #ffbb00;
  color: black;
}
</style>
