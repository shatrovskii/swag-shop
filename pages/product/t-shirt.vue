<template>
  <section class="product-container">
    <div class="product-preview">
        <img :src="printsList[selectedPrint].src"
             :srcset="`${printsList[selectedPrint].src2x} 2x, ${printsList[selectedPrint].src3x} 3x`">
    </div>
    <div class="product-form">
        <h1>The RtB Tee</h1>
        <h3>20$</h3>
        <p>Available in all colors as long as it's white,<br>grey or black. A job here doesn't come with it. Not available in Russia.</p>
        
    </div>
  </section>
</template>

<script>
export default {
  asyncData ({params}) {
      return {
        printsList: [
            {
                src: require('~/assets/zip-mouth.png'),
                src2x: require('~/assets/zip-mouth@2x.png'),
                src3x: require('~/assets/zip-mouth@3x.png')
            }
        ],
        selectedPrint: 0
      }
  }
}
</script>

<style>
    .product-container {
        display: flex;
        justify-content: center;
        align-items: center;
        padding-top: 60px;
        height: 100vh;
        color: #1a1919;
    }

    .product-preview {
        width: 680px;
        margin-right: 20px;
    }

    h1 {
        font-family: ActionCondensedBold;
        font-size: 120px;
        font-weight: normal;
        line-height: 1;
        color: #212121;
    }

    h3 {
        margin-top: 10px;
        font-size: 40px;
        line-height: 1;
    }

    .product-form p {
        width: 480px;
        line-height: 1.4;
        margin-top: 40px;
        font-size: 20px;
    }
</style>