# Reference sheet

## abstracts

<strong>mixins.scss</strong>
<hr>

```scss
@mixin clearfix {
    &::after {
        content: "";
        display: table;
        clear: both;
    }
}

@mixin absCenter {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```
<strong>variables.scss</strong>
<hr>

```scss
// COLORS
$color-primary: #55c57a;
$default-font-size: 1.6rem;

// GRID
$grid-width: 114rem;
$gutter-vertical: 8rem;
$gutter-horizontal: 6rem;
```

## base

<strong>animations.scss</strong>
<hr>

```scss
 @keyframes moveInLeft {
    0% {
        opacity: 0;
        transform: translateX(-10rem);
    }

    80% {
        transform: translateX(1rem);
    }

    100% {
        opacity: 1;
        transform: translate(0);
    }
}

@keyframes moveInRight {
    0% {
        opacity: 0;
        transform: translateX(10rem);
    }

    80% {
        transform: translateX(-1rem);
    }

    100% {
        opacity: 1;
        transform: translate(0);
    }
}

@keyframes moveInBottom {
    0% {
        opacity: 0;
        transform: translateY(3rem);
    }

    100% {
        opacity: 1;
        transform: translate(0);
    }
}

```


<strong>base.scss</strong>
<hr>

```scss
*,
*::after,
*::before {
    margin: 0;
    padding: 0;
    box-sizing: inherit;
}

html {
    // This defines what 1rem is
    font-size: 62.5%;
}

body {
    box-sizing: border-box;
}

```

<strong>typography.scss</strong>
<hr>

```scss
body {
    font-family: "Lato", sans-serif;
    font-weight: 400;
    /*font-size: 16px;*/
    line-height: 1.7;
    color: $color-grey-dark;
    padding: 3rem;
}

.heading-primary {
    color: $color-white;
    text-transform: uppercase;

    backface-visibility: hidden;
    margin-bottom: 6rem;

    &--main {
        display: block;
        font-size: 6rem;
        font-weight: 400;
        letter-spacing: 3.5rem;
    
        animation-name: moveInLeft;
        animation-duration: 1s;
        animation-timing-function: ease-out;
    
        /*
        animation-delay: 3s;
        animation-iteration-count: 3;
        */
    }
    
    &--sub {
        display: block;
        font-size: 2rem;
        font-weight: 700;
        letter-spacing: 1.75rem;
        animation: moveInRight 1s ease-out;
    }
}

.heading-secondary {
    font-size: 3.5rem;
    text-transform: uppercase;
    font-weight: 700;
    display: inline-block;
    background-image: linear-gradient(to right, $color-primary-light, $color-primary-dark);
    -webkit-background-clip: text;
    color: transparent;
    letter-spacing: .2rem;
    transition: all .2s;

    &:hover {
        transform: skewY(2deg) skewX(15deg) scale(1.1);
        text-shadow: .5rem 1rem 2rem rgba($color-black, .2);
    }
}

.heading-tertiary {
    font-size: $default-font-size;
    font-weight: 700;
    text-transform: uppercase;
}

.paragraph {
    font-size: $default-font-size;

    &:not(:last-child) {
        margin-bottom: 3rem;
    }
}
```


<strong>typography.scss</strong>
<hr>

```scss
.u-center-text { text-align: center !important; }

.u-margin-bottom-small { margin-bottom: 1.5rem !important; }
.u-margin-bottom-medium { margin-bottom: 4rem !important; }
.u-margin-bottom-big { margin-bottom: 8rem !important; }

.u-margin-top-big { margin-top: 8rem !important; }
.u-margin-top-huge { margin-top: 10rem !important; }
```

## Components
<strong>bg-video.scss</strong>
<hr>

```scss 
.bg-video {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    z-index: -1;
    opacity: .15;
    overflow: hidden;

    &__content {
        height: 100%;
        width: 100%;
        object-fit: cover;
    }
}
```

<strong>button.scss</strong>
<hr>

```scss
.btn {
    &,
    &:link,
    &:visited {
        text-transform: uppercase;
        text-decoration: none;
        padding: 1.5rem 4rem;
        display: inline-block;
        border-radius: 10rem;
        transition: all .2s;
        position: relative;
        font-size: $default-font-size;

        //Change for the <button> element
        border: none;
        cursor: pointer;
    }
    
    &:hover {
        transform: translateY(-3px);
        box-shadow: 0 1rem 2rem rgba($color-black,.2);

        &::after {
            transform: scaleX(1.4) scaleY(1.6);
            opacity: 0;
        }
    }
    
    &:active,
    &:focus {
        outline: none;
        transform: translateY(-1px);
        box-shadow: 0 .5rem 1rem rgba($color-black,.2);
    }
    
    &--white {
        background-color: $color-white;
        color: $color-grey-dark;

        &::after {
            background-color: $color-white;
        }
    }

    &--green {
        background-color: $color-primary;
        color: $color-white;

        &::after {
            background-color: $color-primary;
        }
    }
    
    &::after {
        content: "";
        display: inline-block;
        height: 100%;
        width: 100%;
        border-radius: 10rem;
        position: absolute;
        top: 0;
        left: 0;
        z-index: -1;
        transition: all .4s;
    }
    
    &--animated {
        animation: moveInBottom .5s ease-out .75s;
        animation-fill-mode: backwards;
    }
}

.btn-text {
    &:link,
    &:visited {
        font-size: $default-font-size;
        color: $color-primary;
        display: inline-block;
        text-decoration: none;
        border-bottom: 1px solid $color-primary;
        padding: 3px;
        transition: all .2s;
    }

    &:hover {
        background-color: $color-primary;
        color: $color-white;
        box-shadow: 0 1rem 2rem rgba($color-black, .15);
        transform: translateY(-2px);
    }

    &:active {
        box-shadow: 0 .5rem 1rem rgba($color-black, .15);
        transform: translateY(0);
    }
}
```

<strong>card.scss</strong>
<hr>

```scss
.card {

    // FUNCTIONALITY
    perspective: 150rem;
    -moz-perspective: 150rem;
    position: relative;
    height: 52rem;
    
    &__side {
        height: 52rem;
        transition: all .8s ease;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        backface-visibility: hidden;
        border-radius: 3px;
        overflow: hidden;
        box-shadow: 0 1.5rem 4rem rgba($color-black, .15);

        &--front {
            background-color: $color-white;
        }

        &--back {
            transform: rotateY(180deg);

            &-1 {
                background-image: linear-gradient(to right bottom, $color-secondary-light, $color-secondary-dark);
            }

            &-2 {
                background-image: linear-gradient(to right bottom, $color-primary-light, $color-primary-dark);
            }

            &-3 {
                background-image: linear-gradient(to right bottom, $color-tertiary-light, $color-tertiary-dark);
            }
        }
    }
  

    &:hover &__side--front {
        transform: rotateY(-180deg);
    }

    &:hover &__side--back {
        transform: rotateY(0);
    }


    // FRONT SIDE STYLING
    &__picture {
        background-size: cover;
        height: 23rem;
        background-blend-mode: screen;
        -webkit-clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
        clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
        border-top-left-radius: 3px;
        border-top-right-radius: 3px;
        
        &--1 {
            background-image: linear-gradient(to right bottom, $color-secondary-light, $color-secondary-dark), 
            url(../img/nat-5.jpg);
        }

        &--2 {
            background-image: linear-gradient(to right bottom, $color-primary-light, $color-primary-dark), 
            url(../img/nat-6.jpg);
        }

        &--3 {
            background-image: linear-gradient(to right bottom, $color-tertiary-light, $color-tertiary-dark), 
            url(../img/nat-7.jpg);
        }
    }

    &__heading {
        font-size: 2.8rem;
        font-weight: 300;
        text-transform: uppercase;
        text-align: right;
        color: $color-white;
        position: absolute;
        top: 12rem;
        right: 2rem;
        width: 75%;
    
    }

    &__heading-span {
        padding: 1rem 1.5rem;
        -webkit-box-decoration-break: clone;
        box-decoration-break: clone;

        &--1 {
            background-image: linear-gradient(to right bottom, 
            rgba($color-secondary-light, .85), 
            rgba($color-secondary-dark, .85));
        }

        &--2 {
            background-image: linear-gradient(to right bottom, 
            rgba($color-primary-light, .85), 
            rgba($color-primary-dark, .85));
        }

        &--3 {
            background-image: linear-gradient(to right bottom, 
            rgba($color-tertiary-light, .85), 
            rgba($color-tertiary-dark, .85));
        }
    }

    &__details {
        padding: 3rem;

        ul {
            list-style: none;
            width: 80%;
            margin: 0 auto;

            li {
                text-align: center;
                font-size: 1.5rem;
                padding: 1rem;

                &:not(:last-child) {
                    border-bottom: 1px solid $color-grey-light-2;
                }
            }
        }
    }

    // FRONT SIDE STYLING
    &__cta {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 90%;
        text-align: center;
    }

    &__price-box {
        text-align: center;
        color: $color-white;
        margin-bottom: 8rem;
    }

    &__price-only {
        font-size: 1.4rem;
        text-transform: uppercase;
    }

    &__price-value {
        font-size: 6rem;
        font-weight: 100;
    }
}
```

<strong>composition.scss</strong>
<hr>

```scss
.composition {
    position: relative;

    &__photo {
        width: 55%;
        box-shadow: 0 1.5rem 4rem rgba($color-black, .4);
        border-radius: 2px;
        position: absolute;
        z-index: 10;
        transition: all .2s;
        outline-offset: 2rem;

        &--p1 {
            left: 0;
            top: -2rem;
        }

        &--p2 {
            right: 0;
            top: 2rem;
        }

        &--p3 {
            left: 20%;
            top: 10rem;
        }

        &:hover {
            outline: 1.5rem solid $color-primary;
            transform: scale(1.05) translateY(-.5rem);
            box-shadow: 0 2.5rem 4rem rgba($color-black, .5);
            z-index: 20;
        }

    }

    &:hover &__photo:not(:hover) {
        transform: scale(.95);
    }
}
```

<strong>feature-box.scss</strong>
<hr>

```scss
.feature-box {
    background-color: rgba($color-white, .8);
    font-size: 1.5rem;
    padding: 2.5rem;
    text-align: center;
    border-radius: 3px;
    box-shadow: 0 1.5rem 4rem rgba($color-black, .15);
    transition: transform .3s;

    &__icon {
        font-size: 6rem;
        margin-bottom: .5rem;
        display: inline-block;
        background-image: linear-gradient(to right, $color-primary-light, $color-primary-dark);
        -webkit-background-clip: text;
        color: transparent;
    }

    &:hover {
        transform: translateY(-1.5rem) scale(1.03);
    }
}
```

<strong>form.scss</strong>
<hr>

```scss
.form {
    &__group:not(:last-child) {
        margin-bottom: 2rem;
    }

    &__input {
        font-size: 1.5rem;
        font-family: inherit;
        color: inherit;
        padding: 1.5rem 2rem;
        border-radius: 2px;
        background-color: rbga($color-white, .5);
        border: none;
        border-bottom: 3px solid transparent;
        width: 90%;
        display: block;
        transition: all .3s;

        &:focus {
            outline: none;
            box-shadow: 0 1rem 2rem rgba($color-black, .1);
            border-bottom: 3px solid $color-primary;
        }

        &:focus:invalid {
            border-bottom: 3px solid $color-secondary-dark;
        }

        &::-webkit-input-placeholder {
            color: $color-grey-dark-2;
        }
    }


    &__label {
        font-size: 1.2rem;
        font-weight: 700;
        margin-left: 2rem;
        margin-top: .7rem;
        display: block;
        transition: all .3s;
    }

    &__input:placeholder-shown + &__label {
        opacity: 0;
        visibility: hidden;
        transform: translateY(-4rem);
    }


    &__radio-group {
        width: 49%;
        display: inline-block;
    }

    &__radio-input {
        display: none;
    }
    
    &__radio-label {
        font-size: $default-font-size;
        cursor: pointer;
        position: relative;
        padding-left: 4.5rem;
    }

    &__radio-button {
        height: 3rem;
        width: 3rem;
        border: 5px solid $color-primary;
        border-radius: 50%;
        display: inline-block;
        position: absolute;
        left: 0;
        top: -.4rem;

        &::after {
            content: "";
            display: block;
            height: 1.3rem;
            width: 1.3rem;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: $color-primary;
            opacity: 0;
            transition: opacity .2s;
        }
    }

    &__radio-input:checked ~ &__radio-label &__radio-button::after {
        opacity: 1;
    }
}
```

<strong>popup.scss</strong>
<hr>

```scss
.popup {
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba($color-black, .8);
    z-index: 9999;
    opacity: 0;
    visibility: hidden;
    transition: all .3s;

    &__content {
        @include absCenter;

        width: 75%;
        background-color: $color-white;
        box-shadow: 0 2rem 4rem rgba($color-black, .2);
        border-radius: 3px;
        display: table;
        overflow: hidden;
        opacity: 0;
        transform: translate(-50%, -50%) scale(.25);
        transition: all .5s .2s;
    }

    &__left {
        width: 33.333333%;
        display: table-cell;
    }

    &__right {
        width: 66.6666667%;
        display: table-cell;
        vertical-align: middle;
        padding: 3rem 5rem;
    }

    &__img {
        display: block;
        width: 100%;
    }

    &__text {
        font-size: 1.4rem;
        margin-bottom: 4rem;

        -moz-column-count: 2;
        -moz-column-gap: 4rem; //1em = 14px;
        -moz-column-rule: 1px solid $color-grey-light-2;

        column-count: 2;
        column-gap: 4rem; //1em = 14px;
        column-rule: 1px solid $color-grey-light-2;

        -moz-hyphens: auto;
        -ms-hyphens: auto;
        -webkit-hyphens: auto;
        hyphens: auto;
    }

    //Open states
    &:target {
        opacity: 1;
        visibility: visible;
    }

    &:target &__content {
        opacity: 1;
        transform: translate(-50%, -50%) scale(1);
    }

    &__close {
        &:link,
        &:visited {
            color: $color-grey-dark;
            position: absolute;
            top: 2.5rem;
            right: 2.5rem;
            font-size: 3rem;
            text-decoration: none;
            display: inline-block;
            transition: all .2s;
            line-height: 1;
        }

        &:hover {
            color: $color-primary;
        }
    }
}
```

<strong>story.scss</strong>
<hr>

```scss
.story {
    width: 75%;
    margin: 0 auto;
    box-shadow: 0 3rem 6rem rgba($color-black, .1);
    background-color: rgba($color-white, .6);
    border-radius: 3px;
    padding: 6rem;
    padding-left: 9rem;
    font-size: $default-font-size;
    transform: skewX(-12deg);

    &__shape {
        width: 15rem;
        height: 15rem;
        float: left;
        -webkit-shape-outside: circle(50% at 50% 50%);
        shape-outside: circle(50% at 50% 50%);
        -webkit-clip-path: circle(50% at 50% 50%);
        clip-path: circle(50% at 50% 50%);
        transform: translateX(-3rem) skewX(12deg);
        position: relative;
    }

    &__img {
        height: 100%;
        transform: translateX(-4rem) scale(1.4);
        backface-visibility: hidden;
        transition: all .5s;
    }

    &__text {
        transform: skewX(12deg);
    }

    &__caption {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, 20%);
        color: $color-white;
        text-transform: uppercase;
        font-size: 1.7rem;
        text-align: center;
        opacity: 0;
        transition: all .5s;
        backface-visibility: hidden;
    }

    &:hover &__caption {
        opacity: 1;
        transform: translate(-50%, -50%);
    }

    &:hover &__img {
        transform: translateX(-4rem) scale(1);
        filter: blur(3px) brightness(80%);
    }
}
```

## layout
<strong>footer.scss</strong>
<hr>

```scss
.footer {
    background-color: $color-grey-dark-3;
    padding: 10rem 0;
    font-size: 1.4rem;
    color: $color-grey-light-1;

    &__logo-box {
        text-align: center;
        margin-bottom: 8rem;
    }

    &__logo {
        width: 15rem;
        height: auto;
    }

    &__navigation {
        border-top: 1px solid $color-grey-dark;
        padding-top: 2rem;
        display: inline-block;
    }

    &__list {
        list-style: none;
    }

    &__item {
        display: inline-block;

        &:not(:last-child) {
            margin-right: 1.5rem;
        }
    }

    &__link {
        &:link,
        &:visited {
            color: $color-grey-light-1;
            background-color: $color-grey-dark-3;
            text-decoration: none;
            text-transform: uppercase;
            display: inline-block;
            transition: all .2s;
        }

        &:hover,
        &:active {
            color: $color-primary;
            box-shadow: 0 1rem 2rem rgba($color-black, .4);
            transform: rotate(5deg) scale(1.3);
        }
    }

    &__copyright {
        border-top: 1px solid $color-grey-dark;
        padding-top: 2rem;
        width: 80%;
        float: right;
    }
}
```

<strong>grid.scss</strong>
<hr>

```scss
.row {
    max-width: $grid-width;
    margin: 0 auto;

    &:not(:last-child) {
        margin-bottom: $gutter-vertical;
    }
    
    @include clearfix;

    [class^="col-"] {
        float: left;

        &:not(:last-child) {
            margin-right: $gutter-horizontal;
        }
    }

    .col-1-of-2 {
        width: calc((100% - #{$gutter-horizontal}) / 2);
        
    }

    .col-1-of-3 {
        width: calc((100% - 2 * #{$gutter-horizontal}) / 3);
    }

    .col-2-of-3 {
        width: calc(2 * ((100% - 2 * #{$gutter-horizontal}) / 3) + #{$gutter-horizontal});
    }

    .col-1-of-4 {
        width: calc((100% - 3 * #{$gutter-horizontal}) / 4);
    }

    .col-2-of-4 {
        width: calc(2 * ((100% - 3 * #{$gutter-horizontal}) / 4) + #{$gutter-horizontal});
    }

    .col-3-of-4 {
        width: calc(3 * ((100% - 3 * #{$gutter-horizontal}) / 4) + 2 * #{$gutter-horizontal});
    }

}

```

<strong>header.scss</strong>
<hr>

```scss
.header {
    height: 95vh;
    background-image: linear-gradient(
        to right bottom,
        rgba($color-primary-light, 0.8),
        rgba($color-primary-dark, 0.8)),
    url(../img/hero.jpg);
    background-size: cover;
    background-position: top;
    position: relative;
    -webkit-clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);
    clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);

    &__logo-box {
        position: absolute;
        top: 4rem;
        left: 4rem;
    }

    &__logo {
        height: 3.5rem;
    }
    
    &__text-box {
        position: absolute;
        top: 40%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
    }
}
```

<strong>navigation</strong>
<hr>

```scss
.navigation {
    &__checkbox {
        display: none;
    }

    &__button {
        background-color: $color-white;
        height: 7rem;
        width: 7rem;
        position: fixed;
        top: 6rem;
        right: 6rem;
        border-radius: 50%;
        z-index: 2000;
        box-shadow: 0 1rem 3rem rgba($color-black, .1);
        text-align: center;
        cursor: pointer;
    }

    &__background {
        height: 6rem;
        width: 6rem;
        border-radius: 50%;
        position: fixed;
        top: 6.5rem;
        right: 6.5rem;
        background-image: radial-gradient($color-primary-light, $color-primary-dark);
        z-index: 1000;
        transition: transform .8s cubic-bezier(0.86, 0, 0.07, 1);

        //transform: scale(80);
    }

    &__nav {
        height: 100vh;
        position: fixed;
        top: 0;
        left: 0;
        z-index: 1500;

        opacity: 0;
        width: 0;
        transition: all .8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }

    &__list {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        list-style: none;
        text-align: center;
        width: 100%;
    }

    &__item {
        margin: 1rem;
    }

    &__link {
        &:link,
        &:visited {
            display: inline-block;
            font-size: 3rem;
            font-weight: 300;
            padding: 1rem 2rem;
            color: $color-white;
            text-decoration: none;
            text-transform: uppercase;
            background-image: linear-gradient(120deg, transparent 0%, transparent 50%, $color-white 50%);
            background-size: 220%;
            transition: all .4s;

            span {
                margin-right: 1.5rem;
                display: inline-block;
            }
        }
        
        &:hover,
        &:active {
            background-position: 100%;
            color: $color-primary;
            transform: translateX(1rem);
        }
    }


    //FUNCTIONALITY
    &__checkbox:checked ~ &__background {
        transform: scale(80);
    }

    &__checkbox:checked ~ &__nav {
        opacity: 1;
        width: 100%;
    }


    //ICON
    &__icon {
        position: relative;
        margin-top: 3.5rem;

        &,
        &::before,
        &::after {
            width: 3rem;
            height: 2px;
            background-color: $color-grey-dark-3;
            display: inline-block;
        }

        &::before,
        &::after {
            content: "";
            position: absolute;
            left: 0;
            transition: all .2s;
        }

        &::before { top: -.8rem; }
        &::after { top: .8rem; }
    }

    &__button:hover &__icon::before {
        top: -1rem;
    }

    &__button:hover &__icon::after {
        top: 1rem;
    }

    &__checkbox:checked + &__button &__icon {
        background-color: transparent;
    }

    &__checkbox:checked + &__button &__icon::before {
        top: 0;
        transform: rotate(135deg);
    }

    &__checkbox:checked + &__button &__icon::after {
        top: 0;
        transform: rotate(-135deg);
    }
}

```
