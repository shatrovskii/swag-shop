<template>
  <section class="product-container">
    <div class="product-preview">
        <img class="product-preview__background" :src="colorsList[selectedColor].src">
        <img class="product-preview__print" :src="printsList[selectedPrint].src">
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
                         v-bind:style="{ backgroundColor: color.color }"
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
                    <button class="product-form__button"
                         v-for="(size, index) in sizesList" 
                         :key="`size-${index}`" 
                         v-bind:class="{ 'product-form__button--active': index === selectedSize }"
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
                    <div class="product-form__image-option" 
                         v-for="(print, index) in printsList" 
                         :key="`print-${index}`" 
                         v-bind:class="{ 'product-form__image-option--active': index === selectedPrint }"
                         v-on:click="selectedPrint = index">
                         <img :src="print.preview"/>
                         <span v-if="!print.preview">NO</span>
                    </div>
                </div>
            </div>
            <div class="product-form__footer">
                <a class="product-form__button product-form__button--active" href="/order-confirmation">Add to Cart</a>
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
                src: '',
                preview: ''
            },
            {
                src: require('~/assets/zip-mouth.svg'),
                preview: require('~/assets/zip-mouth-preview.svg')
            },
            {
                src: require('~/assets/tentacles.svg'),
                preview: require('~/assets/tentacles-preview.svg')
            },
            {
                src: require('~/assets/finger.svg'),
                preview: require('~/assets/finger-preview.svg')
            },
            {
                src: require('~/assets/geometry.svg'),
                preview: require('~/assets/geometry-preview.svg')
            },
            {
                src: require('~/assets/holes.svg'),
                preview: require('~/assets/holes-preview.svg')
            }
        ],
        selectedPrint: 0,
        colorsList: [
            {
                color: '#ffffff',
                src: require('~/assets/t-shirt-white@2x.jpg')
            },
            {
                color: '#000000',
                src: require('~/assets/t-shirt-black@2x.jpg')
            },
            {
                color: '#e1e1e1',
                src: require('~/assets/t-shirt-grey@2x.jpg')
            }
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
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 643px;
        margin-right: 36px;
    }

    .product-preview__print {
        position: absolute;
        margin-top: -64px;
    }

    .product-preview__background {
        width: 100%;
    }

    .product-info {
        width: 480px;
    }

    .product-info h1 {
        font-family: "ActionCondensedBold-Grade1", Helvetica, Arial, serif;
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
        display: flex;
        margin-top: 10px;
    }

    .product-form__image-option {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        border: 1px solid #e1e1e1;
        cursor: pointer;
        overflow: hidden;
    }

    .product-form__image-option span {
        color: #999999;
    }

    .product-form__image-option + .product-form__image-option {
        margin-left: 20px;
    }

    .product-form__image-option.product-form__image-option--active {
        border-color: #5b00ff;
    }

    .product-form__button {
        display: inline-block;
        line-height: 60px;
        padding: 0 32px;
        font-size: inherit;
        color: #5b00ff;
        background-color: #fff;
        border: 1px solid #5b00ff;
        cursor: pointer;
        text-decoration: none;
    }

    .product-form__button + .product-form__button {
        border-left-width: 0px;
    }

    .product-form__button:first-child {
        border-top-left-radius: 4px;
        border-bottom-left-radius: 4px;
    }

    .product-form__button:last-child {
        border-top-right-radius: 4px;
        border-bottom-right-radius: 4px;
    }

    .product-form__button.product-form__button--active {
        color: #fff;
        background-color: #5b00ff;
    }

    .product-form__button:hover:not(.product-form__button--active) {
        background-color: rgba(91, 0, 255, 0.04);
    }

    .product-form__footer {
        margin-top: 60px;
    }
    
</style>