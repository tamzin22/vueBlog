<template>
  <div class="home">
   <form>
  <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-2 col-form-label col-form-label-sm">Title</label>
    <div class="col-sm-10">
      <input type="text" v-model="title" class="form-control form-control-sm">
    </div>
  </div>
  <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-2 col-form-label col-form-label-sm">Post</label>
    <div class="col-sm-10">
      <input type="text" v-model="post" class="form-control form-control-sm">
    </div>
  </div>  
 <button @click="addPost">Add New Post</button>
</form>
       <table class="table table-bordered mt-5">
         <thead>
           <tr>
              <th >Title</th>
              <th >Post</th>
              <th >Edit</th>
              <th >Delete</th>
           </tr>
         </thead>
         <tbody>
           <tr v-for="(post , index) in posts" :key="index">
             <td>{{post.title}}</td>
             <td>{{post.post}}</td>
             <td><button @click="deletePost(index)">Edit</button></td>
             <td><button>Delete</button></td>
           </tr>
         </tbody>
       </table>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  data() {
    return {
      title: '',
      post : '',
      newPost :
        {
          title: '',
          post : '',
        },
      posts:[
        {
          title : 'vue',
          post  : 'hcgugcu uyfdi7tywgfyf ygdoygiu ygfyug'
        },
        {
          title : 'laravel',
          post :'gvcgv uwfyg hggy yugfyugf gfyug'
        },
        {
          title : 'react',
          post : 'zdfy ojvvf smxg dhgfjfnbv'
        }
      ]
    }
  },
  methods: {
    addPost(){
      // if(this.newPost.length) return;

      // this.newPost.push({
      //   title:this.title,
      //   post : this.post
      // })
      console.log(this.$newPost)
      
    },
    deletePost(index){
      this.title.splice(index, 1);
    }
  },
}
</script>
