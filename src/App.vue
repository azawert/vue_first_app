<template>
  <div>
    <div>
      <form>
        <input type="text" class="input_field" placeholder="title"/>
        <input type="text" class ="input_field" placeholder="description" />
        <button @click="(e)=>{
          e.preventDefault()
          console.log(description,title)
        }">Add post</button>
      </form>
    </div>
    <div class="post" v-for="item in posts">
      <div>
        <strong>Title:</strong>
        {{item.title}}
      </div>
      <div>
        <strong>Description:</strong>
        {{item.description}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts:[{title:'JavaScript',description:'Frontend language'},{title:'Python',description: 'BackEnd Language'}]
    }
  },
  methods: {
    addPost(event,data) {
      event.preventDefault()
      return [...this.posts,data]
    }
  }

}
</script>
<style>
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
.post {
  padding: 15px;
  border: 2px solid darkgreen;
  margin-top: 15px;
}
.input_field {
  margin-right: 10px;
  border-radius: 6px;
  margin-top: 10px;
  width:100%;
  padding: 10px;
  border: 1px solid teal;

}
form {
  display:flex;
  flex-direction: column;
}
button {
  padding: 5px;
  margin-top: 5px;
  width: 5%;
  align-self: flex-end;
  margin-right: 5px;
}
</style>