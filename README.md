pl-slider
=========

##JavaScript
```js
'use strict';

var PlanediaApp = angular.module('planedia', ['pl.slider']);
PlanediaApp.controller('slider', function( $scope ) {

    $scope.minRate = [];
    $scope.maxRate = [];
    $scope.set = {
        minRate: 0,
        maxRate: 1000
    }

    $scope.value = {
        rate: [300, 710]
    };
    
    $scope.$watch('value.rate', function( term ){
        $scope.minRate = term[0]
        $scope.maxRate = term[1]
    });
});
```

##HTML

```html
<script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.2.26/angular.min.js"></script>
<script src="https://code.jquery.com/ui/1.10.3/jquery-ui.min.js"></script>
<script src="https://rawgit.com/Planedia/pl-slider/master/slider.js"></script>

div 
	pl-Slider="{range: true}" 
	min="{{ set.minRate }}" 
	max="{{ set.maxRate }}" 
	step="5" 
	use-decimals 
	ng-model="value.rate">
</div>
```

##CSS
```css
.ui-slider .ui-slider-handle {
	position: absolute;
	z-index: 2;
	width: 1.2em;
	height: 1.2em;
	cursor: default;
	-ms-touch-action: none;
	touch-action: none;
}
.ui-slider-horizontal .ui-slider-handle {
	top: -.3em;
	margin-left: -.6em;
}
.ui-state-default, .ui-widget-content .ui-state-default, .ui-widget-header .ui-state-default {
	border: 1px solid #FFF;
	background: #289daf;
	width: 10px;
	height: 20px;
	font-weight: bold;
	border-radius: 5px;
	color: #1c94c4;
}
.ui-slider .ui-slider-range {
	position: absolute;
	z-index: 1;
	font-size: .7em;
	display: block;
	border: 0;
	background-position: 0 0;
	background-color: #289daf;
}
.ui-slider-horizontal .ui-slider-range {
	top: 0;
	height: 100%;
}
.ui-widget-content {
	background: #2c3e50;
}
.ui-slider-horizontal {
	height: 10px;
	border-radius: 10px;
}
.ui-slider {
	position: relative;
	text-align: left;
	margin-top: 15px;
}
```
