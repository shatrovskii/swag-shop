<template>
  <section class="product-container">
    <div class="product-preview">
        <img :src="printsList[selectedPrint].src"
             :srcset="`${printsList[selectedPrint].src2x} 2x, ${printsList[selectedPrint].src3x} 3x`">
    </div>
    <div class="product-info">
        <h1>The RtB Tee</h1>
        <h3>20$</h3>
        <p>Available in all colors as long as it's white,<br>grey or black. A job here doesn't come with it. Not available in Russia.</p>
        <div class="product-form">
            <div class="product-form__field">
                <div class="product-form__label">
                    Colors
                </div>
                <div class="product-form__options">
                    <div class="product-form__image-option" 
                         v-for="(color, index) in colorsList" 
                         :key="`color-${index}`" 
                         v-bind:style="{ backgroundColor: color }"
                         v-bind:class="{ 'product-form__image-option--active': index === selectedColor }"
                         v-on:click="selectedColor = index">
                    </div>
                </div>
            </div>
            <div class="product-form__field">
                <div class="product-form__label">
                    Size
                </div>
                <div class="product-form__options">
                    <button class="product-form__button-option"
                         v-for="(size, index) in sizesList" 
                         :key="`size-${index}`" 
                         v-bind:class="{ 'product-form__button-option--active': index === selectedSize }"
                         v-on:click="selectedSize = index">
                         {{size}}
                    </button>
                </div>
            </div>
            <div class="product-form__field">
                <div class="product-form__label">
                    Patterns
                </div>
                <div class="product-form__options">
                    <img class="product-form__image-option" 
                         v-for="(print, index) in printsList" 
                         :key="`print-${index}`" 
                         v-bind:class="{ 'product-form__image-option--active': index === selectedPrint }"
                         v-on:click="selectedPrint = index"
                         :src="print.preview"/>
                </div>
            </div>
        </div>
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
                src3x: require('~/assets/zip-mouth@3x.png'),
                preview: require('~/assets/zip-mouth.svg')
            },
            {
                src: require('~/assets/tentacles.png'),
                src2x: require('~/assets/tentacles@2x.png'),
                src3x: require('~/assets/tentacles@3x.png'),
                preview: require('~/assets/tentacles.svg')
            },
            {
                src: require('~/assets/finger.png'),
                src2x: require('~/assets/finger@2x.png'),
                src3x: require('~/assets/finger@3x.png'),
                preview: require('~/assets/finger.svg')
            },
            {
                src: require('~/assets/geometry.png'),
                src2x: require('~/assets/geometry@2x.png'),
                src3x: require('~/assets/geometry@3x.png'),
                preview: require('~/assets/geometry.svg')
            },
            {
                src: require('~/assets/holes.png'),
                src2x: require('~/assets/holes@2x.png'),
                src3x: require('~/assets/holes@3x.png'),
                preview: require('~/assets/holes.svg')
            }
        ],
        selectedPrint: 0,
        colorsList: [
            '#ffffff',
            '#000000',
            '#e1e1e1'
        ],
        selectedColor: 0,
        sizesList: [
            'XS',
            'S',
            'M',
            'L',
            'XL'
        ],
        selectedSize: 2
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

    .product-info {
        width: 480px;
    }

    .product-info h1 {
        font-family: ActionCondensedBold;
        font-size: 120px;
        font-weight: normal;
        line-height: 1;
        color: #212121;
    }

    .product-info h3 {
        margin-top: 10px;
        font-size: 40px;
        line-height: 1;
    }

    .product-info p {
        line-height: 1.4;
        margin-top: 40px;
        font-size: 20px;
    }

    .product-form {
        font-size: 20px;
        margin-top: 60px;
    }

    .product-form__field {
        margin-top: 20px;
    }

    .product-form__label {
        line-height: 1.2;
        color: #999;
    }

    .product-form__options {
        margin-top: 10px;
    }

    .product-form__image-option {
        display: inline-block;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        border: 1px solid #e1e1e1;
        cursor: pointer;
    }

    .product-form__image-option + .product-form__image-option {
        margin-left: 20px;
    }

    .product-form__image-option.product-form__image-option--active {
        border-color: #5b00ff;
    }

    .product-form__button-option {
        line-height: 60px;
        padding: 0 32px;
        font-size: inherit;
        color: #5b00ff;
        background-color: #fff;
        border: 1px solid #5b00ff;
        cursor: pointer;
    }

    .product-form__button-option + .product-form__button-option {
        border-left-width: 0px;
    }

    .product-form__button-option:first-child {
        border-radius: 4px 0 0 4px;
    }

    .product-form__button-option:last-child {
        border-radius: 0 4px 4px 0;
    }

    .product-form__button-option.product-form__button-option--active {
        color: #fff;
        background-color: #5b00ff;
    }

    .product-form__button-option:hover:not(.product-form__button-option--active) {
        background-color: rgba(91, 0, 255, 0.04);
    }
    
</style>