<template>
<div class="mirror-main">
  <div class="top">
    <div class="left">
      <div class="l-items">
        <h1>left</h1>
        <div class="clock">
          <iframe src="http://free.timeanddate.com/clock/i7q6l91p/n176/fs60/fcfff/tc000/pc000/ftb/ts1" frameborder="0" width="256" height="70"></iframe>
          <iframe src="https://free.timeanddate.com/clock/i7r7bv1p/n176/tlin/fs28/fcfff/tc000/pc000/tt1/tw0" frameborder="0" width="231" height="33"></iframe>
        </div>

        <div class="calendar"> 
              
      </div>
      </div>
    </div>
    <div class="right">
      <div class="r-items">
        <h1>right</h1>

      </div>  
    </div>
  </div>
  <div class="bottom">
    <div class="carousel">
      <h1 class="myslides">{{ greetMsg }}</h1>
    </div>
    </div>
</div>
</template>

<script>
/* eslint-disable */
export default {
  components: {

  },
  data(){
    return{
      myIndex: 0,
      greetMsg: "",
      greet:{
        0:'Hello, G`day to you mate',
        1:'Buenos Dias Amigo', 
        2:'Get Ready, It`s a new day and a new beginning', 
        3:'Reality is an illusion', 
        4:'It`s a new dawn. It`s a new day and I`m feeling good'

      }
    }
  },
  methods: {
    carousel() {
      var i = Math.floor(Math.random() * 5); 
      this.greetMsg = this.greet[i];
      setTimeout(this.carousel, 15000);
    }
  },
  beforeMount() {
    this.carousel();
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  overflow: hidden;
}
.mirror-main{
  background-color: black;
  width: 100%;
  height: 100vh;
  color: white;
  font-family: 'Montserrat', sans-serif;
  font-size: 22px ;
}

.top{
  display: flex;
  height: 70vh;
}
.left{
  width: 50%;
  border: solid 1px yellow;
}
.right{
  text-align: end;
  width: 50%;
  border: solid 1px yellow;
}

/* bottom */

.bottom{
  width: 100%;
  text-align: center;
  border: solid 1px yellow;
}

/* left */

.l-items{
  padding: 20px;
}

.calendar{
  margin: 0;
  padding: 0;
  pointer-events: none;
}


/* right */

.r-items{
  padding: 20px;
}

.clock{
  display: flex;
  flex-direction: column;
  padding: 20px 0px 40px 0px;
}

.clock iframe{
  pointer-events: none;
}


</style>
