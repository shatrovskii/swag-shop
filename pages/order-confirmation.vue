<template>
  <section class="order-confirmation">
    <img src="~/assets/rtb-shop-logo.svg"/>
    <p class="order-confirmation__text">
      Your order has been successfully<br>processed. It will be delivered<br>in 1 minute.
    </p>
  </section>
</template>

<style>
  .order-confirmation {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    height: 100vh;
  }

  .order-confirmation__text {
    margin-top: 40px;
    font-family: "Gerbera-Light";
    font-size: 40px;
    line-height: 1.3;
    color: "#1a1919";
  }
</style>