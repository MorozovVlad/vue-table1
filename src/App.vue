<template>
  <div>
      <h1>Table</h1>
      <div class="input-block">
        <button class="btn" @click="createItem">Create</button>
        <input v-bind:value="id" @input="id = $event.target.value" class="input" type="text" placeholder="id">
        <input v-bind:value="count" @input="count = $event.target.value" class="input" type="text" placeholder="count">
        <input v-bind:value="name" @input="name = $event.target.value" class="input" type="text" placeholder="name">
        <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text" placeholder="title">
        <input v-bind:value="description" @input="description = $event.target.value" class="input" type="text" placeholder="description">
      </div>
      <div class="table">
        <table id="table">
          <thead><tr class="head"> 
            <th>id</th> 
            <th><p @click="soort1">count</p></th> 
            <th><p @click="soort2">name</p></th> 
            <th><p @click="soort3">title</p></th> 
            <th><p @click="soort4">description</p></th> 
            </tr></thead>
          <tbody>
          <tr class="item" v-for="item in items" :key="item.id">
            <td>{{item.id}}</td><td>{{item.count}}</td><td>{{item.name}}</td><td>{{item.title}}</td><td>{{item.description}}</td>
          </tr> 
          </tbody>
        </table> 
      </div>
  </div>
</template>

<script>
export default {
  name: 'page',
  data () {
    return {
      items: [
        { id: 1, count:'3', name: 'erg', title: 'bknpoo', description: 'sdgfsgsdjzb' },
        { id: 2, count:'4', name: 'ghdr', title: 'nknpoo', description: 'ijbsfgsgdgarb' },
        { id: 3, count:'7', name: 'sgh', title: 'iknpoo', description: 'ihjzsrgzzsdjzb' },
        { id: 4, count:'3', name: 'fku', title: 'aknpoo', description: 'bjdjbosdjzb' },
        { id: 5, count:'1', name: 'sdgb', title: 'gknpoo', description: 'kyuosdjzb' },
        { id: 6, count:'9', name: 'huyf', title: 'fknpoo', description: 'dfjhjzbijbosdjzb' },
        { id: 7, count:'4', name: 'dfgn', title: 'aknpoo', description: 'dfgndjzbijbosdjzb' },
        { id: 8, count:'8', name: 'hjk', title: 'cknpoo', description: 'nmbvbijbosdjzbijbosdjzb' },
        { id: 9, count:'7', name: 'ewrg', title: 'rknpoo', description: 'lkjosdjzb' },
        { id: 10, count:'8', name: 'asdf', title: 'yknpoo', description: 'trjbosdjzb' },
        { id: 11, count:'3', name: 'erg', title: 'hknpoo', description: 'zszjzbijbosdjzb' },
        { id: 12, count:'4', name: 'ghdr', title: 'yknpoo', description: 'dfgszbijbosdjzb' },
        { id: 13, count:'7', name: 'sgh', title: 'uknpoo', description: 'cxzdjzbijbosdjzb' },
        { id: 14, count:'3', name: 'fku', title: 'iknpoo', description: 'iujzbijbosdjzb' },
        { id: 15, count:'1', name: 'sdgb', title: 'mknpoo', description: 'qijbosdjzb' },
        { id: 16, count:'9', name: 'huyf', title: 'zknpoo', description: 'sbijbosdjzb' },
        { id: 17, count:'4', name: 'dfgn', title: 'xknpoo', description: 'pzbijbosdjzb' },
        { id: 18, count:'8', name: 'hjk', title: 'eknpoo', description: 'vbosdjzb' },
        { id: 19, count:'7', name: 'ewrg', title: 'qknpoo', description: 'cbosdjzbijbosdjzb' },
        { id: 20, count:'8', name: 'asdf', title: 'tknpoo', description: 'bbijbosdjzb' },       
        ],
        id: '',
        count: '',
        name: '',
        title: '',
        description: ''
    }
  },
  methods: {
    createItem(){
      const newItem = {
        id: this.id,
        count: this.count,
        name: this.name,
        title: this.title,
        description: this.description,
      }
      this.items.push(newItem);
      this.id = '';
      this.count = '';
      this.name = '';
      this.title = '';
      this.description = '';
    },
    soort1(){
      let sortedRows = Array.from(table.rows)
      .slice(1)
      .sort((rowA, rowB) => rowA.cells[1].innerHTML > rowB.cells[1].innerHTML ? 1 : -1);

      table.tBodies[0].append(...sortedRows);
    },
    soort2(){
      let sortedRows = Array.from(table.rows)
      .slice(1)
      .sort((rowA, rowB) => rowA.cells[2].innerHTML > rowB.cells[2].innerHTML ? 1 : -1);

      table.tBodies[0].append(...sortedRows);
    },
    soort3(){
      let sortedRows = Array.from(table.rows)
      .slice(1)
      .sort((rowA, rowB) => rowA.cells[3].innerHTML > rowB.cells[3].innerHTML ? 1 : -1);

      table.tBodies[0].append(...sortedRows);
    },
    soort4(){
      let sortedRows = Array.from(table.rows)
      .slice(1)
      .sort((rowA, rowB) => rowA.cells[4].innerHTML > rowB.cells[4].innerHTML ? 1 : -1);

      table.tBodies[0].append(...sortedRows);
    }
    
  }
}
</script>

<style scoped>

  *{
    text-align: center;
    margin: 0;
    padding: 0;
    background-color: #CCFFFF;
  }
  h1{
    font-family: Consolas;
    font-size: 50px;
    padding-bottom: 15px;
  }
  .input-block{
    position: fixed;
    margin: 40px;
  }
  .btn{
    font-family: Consolas;
    font-size: 20px;
    font-weight: bold;
    border: 3px solid grey;
    border-radius: 10px;
    padding: 17px;
    background-color: #99FFFF;
    display: list-item;
    margin: auto;
    text-align: center;
  }
  .btn:hover {
    background-color: #33FFFF;
    cursor: pointer;
  } 
  p:hover {
    cursor: pointer;
    color: blue;
  } 
  input{
    border: 0px solid grey;
    border-radius: 10px;
    padding: 17px;
    text-align: center;
    font-family: Consolas;
    font-size: 20px;
    background-color: #99FFFF;
    display: list-item;
    margin: 5px;

  }
  .table{
    margin: auto;
    text-align: center;
  }
  table{
    display: inline-block;
  }
  .head{
    font-family: Consolas;
    font-size: 20px;
  }
  td {
    border: 0px solid grey;
    border-radius: 10px;
    padding: 17px;
    text-align: center;
    font-family: Consolas;
    font-size: 20px;
    background-color: #99FFFF;
  }
</style>
