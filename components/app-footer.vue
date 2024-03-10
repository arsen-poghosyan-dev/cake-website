<template>
  <div class="app-footer">

    <div class="app-footer-contacts-info">
      <a href="">
        <i class="fa-solid fa-location-dot"></i>
        Russia Moscow
      </a>
      <a href="">
        <i class="fa-solid fa-mobile-screen-button"></i>
        +7 44444444444
      </a>
      <a href="">
        <i class="fa-regular fa-envelope"></i>
        moscow@.ru
      </a>
    </div>

    <div class="app-footer-contacts-form">
     <form>
       <div class="app-form-item">
         <label>Name</label>
         <input type="text" placeholder="First name">
       </div>
       <div class="app-form-item">
         <label>Email</label>
         <input type="email" placeholder="moscow@.ru">
       </div>
       <div class="app-form-item">
         <label>Phone</label>
         <input type="number" placeholder="+7 44444444444">
       </div>
       <div class="app-form-item">
         <label>Message</label>
         <textarea placeholder="Comments"></textarea>
       </div>
       <button type="button">Submit</button>
     </form>
   </div>

  </div>
</template>

<script  lang="ts">
export default  {
  name: 'app-footer'
}
</script>

<style >
.app-footer{
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 50px 0;
  .app-footer-contacts-info {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    border: 1px solid orange;
    a{
      text-decoration: none;
      color: black;
      font-weight: 600;
      font-size: 20px;
      margin-top: 30px;
    }
    i{
      color: burlywood;
    }
  }

  .app-footer-contacts-form {
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    flex-direction: column;
    width: 100%;
    form {
      display: flex;
      flex-direction: column;
      width: 100%;

    }
  }
  .app-form-item {
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    flex-direction: column;
    width: 100%;
    input {
      width: 100%;
      height: 40px;
      margin-top: 5px;
    }
    textarea {
      width: 100%;
      height: 90px;
      margin-top: 5px;
    }
    label{
      font-size: 20px;
      color: black;
      font-weight: 600;
      margin-top: 5px;
    }
  }
  button{
    width: 100%;
    height: 50px;
    margin-top: 20px;
    font-size: 17px;
    font-weight: 600;
    background: white;
  }
  button:hover{
    background: burlywood;
    color: white;
  }
}



</style>