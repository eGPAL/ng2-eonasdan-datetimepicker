# ng2-eonasdan-datetimepicker

* A wrapper directive around the [bootstrap-datetimepicker component](http://eonasdan.github.io/bootstrap-datetimepicker/).
* It is a continuation of [angular-eonasdan-datetimepicker](https://github.com/atais/angular-eonasdan-datetimepicker).
* It works with angular 2, angular 4 and angular 5


Having problems using the wrapper? <br>
Please, post an issue on GitHub and **provide a plunker** with your question.

## Installation

1) Install the directive via bower or npm (or download it manually, as you prefer)
```javascript
npm install ng2-eonasdan-datetimepicker --save
```

2) Include dependent libraries in your application:
    * jquery.js, 
    * bootstrap (.js & .css),
    * eonasdan bootsrap datetimepicker (.js & .css),
    * moment.js.

    #### Angular cli:
    Example configuration for [angular-cli](https://github.com/angular/angular-cli) in `.angular-cli.json` file

    ```json 
      "styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.min.css",
        "../node_modules/eonasdan-bootstrap-datetimepicker/build/css/bootstrap-datetimepicker.min.css"
      ],
      "scripts": [
        "../node_modules/jquery/dist/jquery.min.js",
        "../node_modules/bootstrap/dist/js/bootstrap.min.js",
        "../node_modules/moment/min/moment.min.js",
        "../node_modules/eonasdan-bootstrap-datetimepicker/src/js/bootstrap-datetimepicker.js"
      ],
    ```
    
    #### Webpack:
    Example configuration for [webpack](https://github.com/webpack/webpack) in `vendor.ts` file

    ```javascript
    // css files
    import 'bootstrap/dist/css/bootstrap.min.css';
    import 'eonasdan-bootstrap-datetimepicker/build/css/bootstrap-datetimepicker.min.css';
    // js files
    import * as $ from 'jquery';
    window['jQuery'] = window['$'] = $;
    import 'bootstrap/dist/js/bootstrap.min.js';
    import 'eonasdan-bootstrap-datetimepicker/src/js/bootstrap-datetimepicker.js'
    import * as moment from 'moment';
    ```    


3) Add the A2Edatetimepicker module import in your module.:

```javascript
import {A2Edatetimepicker} from 'ng2-eonasdan-datetimepicker';
import {FormsModule} from '@angular/forms';

@NgModule({
  imports: [
    ...
    FormsMoudle,
    A2Edatetimepicker,
    ...
  ]
})
export class SomeModule {}
```

4) Start using!

## Examples

*  <a href="https://atais.github.io/ng2-eonasdan-datetimepicker/" target="_blank">Live demo</a>
 * Simple example, with one datetimepicker: <a href="https://embed.plnkr.co/XcVl8BrTWVMR6eqAji7S/" target="_blank">SystemJS (Plunker)</a> | <a href="https://github.com/atais/ng2-eonasdan-datetimepicker/tree/master/examples/angular-cli/src/app/simple-datepicker" target="_blank">Demo code (Angular cli or Webpack)</a>
* Example with two, linked datetimepickers: <a href="https://run.plnkr.co/preview/cjfj8gqhm0007fill6tel3dg6/" target="_blank">SystemJS (Plunker)</a> | <a href="https://github.com/atais/ng2-eonasdan-datetimepicker/tree/master/examples/angular-cli/src/app/linked-datepickers" target="_blank">Demo code  (Angular cli or Webpack)</a>
* Example with Reactive form: <a href="https://github.com/atais/ng2-eonasdan-datetimepicker/tree/master/examples/angular-cli/src/app/reactive-form/" target="_blank">Demo code (Angular cli or Webpack)</a>, 


## Directive usage

Add `a2e-datetimepicker` tag and add the `date` attribute. 

Currently the `a2e-datetimepicker` tag can be added on either `input-group` or the `input` element.

Option #1
```html
<div class="form-group">
<div class="input-group">
  <input class="form-control" 
        a2e-datetimepicker
        [(ngModel)]="dateTo"
        [options]="a2eOptions"/>
  <span class="input-group-addon">
    <span class="glyphicon glyphicon-calendar"></span>
  </span>
</div>
</div>
```

Option #2
```html
<div class="form-group">
<div class="input-group"
        a2e-datetimepicker
        [(ngModel)]="dateTo"
        [options]="a2eOptions"
        (onClick)="dateClick()">
  <input class="form-control"/>
  <span class="input-group-addon">
    <span class="glyphicon glyphicon-calendar"></span>
  </span>
</div>
</div>
```


In both cases the directive will work exactly the same. Also triggering the callendar with the icon in `span` will work in both cases. 
**This comes from angular1 version and may be deleted in the future.**

## Parameters


### options

With `options` attribute you can pass an object containing all the required configuration for your datetimepicker.
All the options available in the original library are supported. Check the list of options on official website: http://eonasdan.github.io/bootstrap-datetimepicker/Options/

```javascript
options = {
    format: "DD.MM.YYYY",
    maxDate: dateTo
};
```

### onClick

An `EventEmitter` which gives you information whenever you open or close the datetimepicker.


## [License](https://github.com/atais/ng2-eonasdan-datetimepicker/blob/master/LICENSE)
