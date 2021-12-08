<template>
<main>
  <section>
    <router-view/>
  </section>

  <div class="btn-group">
      <div class="small-btn-group">
        <a href="/about"><button class="small-btn">關於</button></a>
        <a href="/login"><button class="small-btn">登入</button></a>
        <a href="/register"><button class="small-btn">註冊</button></a>
      </div>
      <a href="/"><button class="big-btn">查詢</button></a>
  </div>
</main>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,300;0,400;0,500;0,600;1,100;1,300&display=swap");
*{
    font-family: 'Poppins', san-serif;
    margin: 0; padding: 0;
    box-sizing: border-box;
    outline: none;
    border: none;
    text-decoration: none;
    transition: .4s linear;
}

$black: #2c3e50;
$white: #fff;

a{
  list-style: none;
  color: $black;
  cursor: pointer;
}
input{
  outline: none;
  cursor: pointer;
}
button, label{
  cursor: pointer;
}



@mixin grid($val){
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax($val, 1fr));
  }

main{
    display: flex;
    align-items: center;
    column-gap: 2.5rem;
    padding: 2rem 9%;
    width: 100%;
    height: 100vh;
    background: url("./assets/images/bus-night.jpg") no-repeat;
    background-position: center;
    background-size: cover;

    section{
      width: 100%;
      height: 100%;
      padding: 4rem;
      background: rgba($color: #000000, $alpha: 0.7);
      border: .35rem solid #48dbfb;
      border-radius: 2rem ;
      display: flex;
      justify-content: center; align-items: center;
    }


    .btn-group{
      display: flex;
      align-items: center;
      justify-content: flex-end;
      
      button{
          border-radius: 50%;
          border: 3px solid blue;
          font-size: 1.5rem;
          cursor: pointer;
          background: #130f40;
          color: $white;

          &:hover{
            background: #000;
          }
        &.big-btn{
          width: 12rem; height: 12rem;
        }
        &.small-btn{
            width: 6rem; height: 6rem;
        }
      }

    .small-btn-group{
      position: relative;
        a:nth-child(1){
            position: absolute;
            top: 130%;
            left: 50%;
        }
        a:nth-child(2){
            position: absolute;
            top: -130%;
            left: 50%;
        }
        a:nth-child(3){
            position: relative;
            left: -10%;
        }
      }
  }
}

  @media screen and (max-width: 991px) {
    html {
      font-size: 90%;
    }
    
    main{
      @include grid(32rem);

       .btn-group{
          order: -1; // grid順序
        }
    }
  }

  @media screen and (max-width: 768px) {
    html {
      font-size: 80%;
    }
    
    main{
      padding: 0;
    }

    .btn-group{
        flex-direction: column-reverse;
        row-gap: 1rem;
      
      .small-btn-group{
        position: initial;
        display: flex;
        column-gap: 1.75rem;

        a{
          transform: none;
          position: initial !important;
        }
          a:nth-child(1){
            transform: translateY(-50%);
          }
          a:nth-child(3){
            transform: translateY(-50%);
          }
      }
    }
  }


  @media screen and (max-width: 450px) {
  html {
    font-size: 60%;
  }
}
</style>
