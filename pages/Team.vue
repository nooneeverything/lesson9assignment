<template>
<b-container>
  <!-- V-For Loop Iterating Through Array of Images-->
  <div class="row">
    <div v-for="image in images">
      <b-img class="rounded fluid img-thumbnail mt-5 left" v-bind:src="image.src" height="300px"
    width="450px">
      </b-img>
      <h1 class="mt-5">{{image.name}}</h1>
      <p class="mt-5"> {{text}}</p>
    </div>
  </div>
</b-container>
</template>
    
  <script>
  

    export default {

      name: 'gallery', 
      data() {
        return {  
          images: [  
            { src: require('../assets/images/image1.jpg'), name: 'Robertaz Evenson'},
            { src: require('../assets/images/image2.jpg'), name: 'Robert Peterson'},
            { src: require('../assets/images/image3.jpg'), name: 'Rebecca Stevens'},
          ],
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut turpis enim, convallis at mi sed, finibus scelerisque felis. Etiam consequat nisi dui, venenatis porta erat consectetur eu. In sed lectus erat. Donec porttitor velit nec massa varius rhoncus. Vivamus orci nunc, commodo non mollis in, tristique sed neque. Aenean sollicitudin scelerisque mi quis pretium. In malesuada mauris sed ante ullamcorper lobortis. Duis erat nisi, varius sed bibendum non, vulputate et sem. Vestibulum ac mattis tortor. '
        
        }

  },
  head() {
    return {
      title: "Team",
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Information about the lawyers at the firm'
        }
      ]
    }
  }
}   
    
  </script>
