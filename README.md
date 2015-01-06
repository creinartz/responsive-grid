#Simple Responsive Grid

inspired by OOCSS, see https://github.com/stubbornella/oocss/wiki/Grids

```css
.g-1of1 { width: 100%; }
.g-1of2 { width: 50%; }
.g-1of3 { width: 33.33333%; }
.g-2of3 { width: 66.66666%; }
.g-1of4 { width: 25%; }
.g-3of4 { width: 75%; }
.g-1of5 { width: 20%; }
.g-2of5 { width: 40%; }
.g-3of5 { width: 60%; }
.g-4of5 { width: 80%; }
.g-1of6 { width: 16.66666%; }
.g-4of6 { width: 66.66666%; }
.g-5of6 { width: 83.33333%; }
```

5 layers of media queries from

```css
@media only screen and (min-width: $screen-small) {
    .g1-1of1 { width: 100%; }
    .g1-1of2 { width: 50%; }
    .g1-1of3 { width: 33.33333%; }
    .g1-2of3 { width: 66.66666%; }
    .g1-1of4 { width: 25%; }
    .g1-3of4 { width: 75%; }
    .g1-1of5 { width: 20%; }
    .g1-2of5 { width: 40%; }
    .g1-3of5 { width: 60%; }
    .g1-4of5 { width: 80%; }
    .g1-1of6 { width: 16.66666%; }
    .g1-4of6 { width: 66.66666%; }
    .g1-5of6 { width: 83.33333%; }
}
```

until

```css
@media only screen and (min-width: $screen-xxlarge) {
    .g5-1of1 { width: 100%; }
    .g5-1of2 { width: 50%; }
    .g5-1of3 { width: 33.33333%; }
    .g5-2of3 { width: 66.66666%; }
    .g5-1of4 { width: 25%; }
    .g5-3of4 { width: 75%; }
    .g5-1of5 { width: 20%; }
    .g5-2of5 { width: 40%; }
    .g5-3of5 { width: 60%; }
    .g5-4of5 { width: 80%; }
    .g5-1of6 { width: 16.66666%; }
    .g5-4of6 { width: 66.66666%; }
    .g5-5of6 { width: 83.33333%; }
}
```

media query range can be defined

```scss
$screen-small: 25.5em !default;
$screen-medium: 32em !default;
$screen-large:  43.5em !default;
$screen-xlarge: 52.5em !default;
$screen-xxlarge: 60em !default;
```

columns can be nested

sample markup

```html
<div class="grid-wrap">
    <div class="row">
        <div class="col g-1of1 g3-2of3 g4-1of2">
            <div class="in">
                <div class="row is-nested">
                    <div class="col g4-1of1">
                        <div class="in">
                            <div class="module">
                                <h1 class="h3">Column</h1>
                                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad expedita cumque eveniet repudiandae asperiores illo ipsam ea pariatur dicta quia animi repellat quis atque rerum distinctio officia eos vitae cupiditate.</p>
                            </div>
                        </div>
                    </div>
                    <div class="col g3-1of1 g4-1of2">
                        <div class="in">
                            <div class="module">
                                <h1 class="h3">Column</h1>
                                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad expedita cumque eveniet repudiandae asperiores illo ipsam ea pariatur dicta quia animi repellat quis atque rerum distinctio officia eos vitae cupiditate.</p>
                            </div>
                        </div>
                    </div>

                    <div class="col g3-1of1 g4-1of2">
                        <div class="in">
                            <div class="module">
                                <h1 class="h3">Column</h1>
                                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad expedita cumque eveniet repudiandae asperiores illo ipsam ea pariatur dicta quia animi repellat quis atque rerum distinctio officia eos vitae cupiditate.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="col g-1of1 g3-1of3 g4-1of2">
            <div class="in">
                <div class="row is-nested">
                    <div class="col g4-1of1">
                        <div class="in">
                            <div class="module">
                                <h1 class="h3">Column</h1>
                                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad expedita cumque eveniet repudiandae asperiores illo ipsam ea pariatur dicta quia animi repellat quis atque rerum distinctio officia eos vitae cupiditate.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </div>
</div>
```