<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <div id="card" class="card">
<head> 
    <meta charset="UTF-8"> 

    <meta name="viewport" content="width=device-width, initial-scale=1.0"> 

    <link rel="stylesheet" href="styles.css"> 

    <title>Card Example</title> 

</head> 

<body> 

    <div class="card"> 

        <img src="https://media.istockphoto.com/id/1369053959/vector/house.jpg?s=612x612&w=0&k=20&c=iA7YgnbjMT89OD8WDtINPoD6p4-sY-GVp1Tt0YdeqxA=" alt="Card Image/logo"> 

        <div class="card-content"> 

            <h2>Two Pod Realty</h2> 

            <p id= 'description'>Real Estate Company Focused on delivering the best properties in the State College Area</p> 

            <button class="details-button" id="detailsBtn">Details</button>
          
        </div> 

    </div> 

</body> 
  </div>
  <button id ="btn">Duplicator</button>
  <button id="colorBtn">BGColorChanger</button>
  <button id="Headingbtn">HeadingChanger</button>
  <button id ="dltbtn">DeleteCard</button>
  <script>
    document.querySelector('#btn').addEventListener('click',function(e){
      const clone = document.querySelector('#card').cloneNode('card');
      document.body.appendChild(clone);
    })
  </script>
   <script>
        var numbers = ["1", "2", "3", "4", "5", "6", "7", "8", "9"];
        var letters = ["A", "B", "C", "D", "E", "F"];
        function randomColor() {
            var color = "";
            for (var i = 0; i < 3; i++) {
                var index = Math.floor(Math.random() * (numbers.length + letters.length));
                color += (index < numbers.length) ? numbers[index] : letters[index - numbers.length];
            }
            return color;
        }
        document.querySelector('#colorBtn').addEventListener('click', function (e) {
            const card = document.querySelector('.card');
            // Check the current background color
            const currentColor = card.style.backgroundColor;
            // Change background color
            card.style.backgroundColor = '#' + randomColor();
        });
    </script>
  <script>
    //HEADING CHANGER
    document.querySelector('#Headingbtn').addEventListener('click', function(e){
      const title = document.querySelector('h2');
      title.innerText = "Super Pod 2 Realty";
    })
  </script>
  <script>
    //card delete
    document.querySelector('#dltbtn').addEventListener('click', function(e){
      const cards = document.querySelectorAll('.card');
      //GPT Assist:
      // Check if there are cards to delete
    if (cards.length > 2) {
        const lastCard = cards[cards.length - 1];
        lastCard.parentNode.removeChild(lastCard);
    }
    })
  </script>
  <script>
    var original= document.querySelector('#description').innerText;
document.querySelector('#detailsBtn').addEventListener('click', function(e) {
    const description = document.querySelector('#description');
    // Toggle the visibility of the description
    if (description.innerText === 'none' || description.innerText=== '') {
        description.innerText = original; // Show the description
    } else {
        description.innerText = ''; // Hide the description
    }
});
  </script>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
.card {
  max-width: 400px;
  margin: 0 auto;
  border: 1px solid #0C0B0B;
  background-Color: #0C0B0B;
  padding: 16px;
  display: flex;
  flex-direction: column;
  text-align: center;
  
}

.card img {
    max-width: 100%;
    height: auto;
}

.card-content {
  flex: 1;
}

/* Style for the Title label */
h2 {
  font-size: 24px;
  margin: -10px 0;
  /*background color and border */
  background-color: #F8471B; /* background color */
  color: #fff; /* Text color on the background */
  padding: 8px 16px;
  border-radius: 4px;
}

p {
  font-size: 16px;
  margin: 8px 0;
  color: #fff
}
a.details-button {
    background-color: #EA5F0A;
    color: #fff;
    padding: 8px 16px;
    text-decoration: none;
    border-radius: 4px;
}
</style>
