# Easy Box Model (EBM)

### Description

EBM or Easy Box Model is a set of automated and prebuilt Sass - Coffee - HTML5 - Grunt tools that __significantly increase your productivity__

### Installing EBM

		git clone https://github.com/netpoe/EasyBoxModel.git

### Out-of-the-box tools

- Twitter Bootstrap ^3.3.0
- Bourbon Sass gem
- CSS Animate
- VideoBG template with VideoJS
- Flexbox ready to use classes (with fallbacks)
- The actual EasyBoxModel Sass mixins, check out the full [list of available tools](https://github.com/netpoe/EasyBoxModel/tree/master/src/scss/EBM)

### Usage

__Development__

		grunt

__Production__

		grunt build

### Examples

Apply a margin top of 21px and a padding left of 35px to a `div`

	<body>
		
		<div class="mt-21 pl-35"></div>

	</body>

For this example, the Sass $times variable is set to 7, so it works for values 7, 14, 21, 28, 35, 42, 49, 56, 63, 70. 

### Reference

| Box Model Property Name| Class Abbreviation | Value |
| ------------- | ------------- | :-----: |
| padding | p- | *$times* sass-variable-value |
| padding-top | pt- | *$times* sass-variable-value |
| padding-right | pr- | *$times* sass-variable-value |
| padding-bottom | pb- | *$times* sass-variable-value |
| padding-left | pl- | *$times* sass-variable-value |
| padding-\* | p\*-sm | *$small* sass-variable-value |
| padding-\* | p\*-xs | *$xs* sass-variable-value |
| margin | m- | *$times* sass-variable-value |
| margin-top | mt- | *$times* sass-variable-value |
| margin-right | mr- | *$times* sass-variable-value |
| margin-bottom | mb- | *$times* sass-variable-value |
| margin-left | ml- | *$times* sass-variable-value |
| margin-\* | m\*-sm | *$small* sass-variable-value |
| margin-\* | m\*-xs | *$xs* sass-variable-value |

__NOTE__: The `p*-sm, p*-xs, m*-sm, m*-xs` classes are 5px and 3px respectively for `$times` 5 to 9, `$times` values from 1 to 4 are set to 1px on both _sm_ and _xs_. __IMPORTANT__: You should not confuse this syntax with the media queries syntax.

### EBM MEDIA QUERIES
___

Now you can create paddings and margins for different screen sizes as follow:

| Box Model Property Name| Class Abbreviation | Value | Screen size |
| ------------- | ------------- | :-----: | ------- |
| padding | p\*- | *$times* sass-variable-value | - xs - sm - md - lg |
| margin | m\*- | *$times* sass-variable-value | - xs - sm - md - lg |

### EBM CHILD SIBLINGS
___

Alternatively, you can target one or more direct siblings of a parent element, e.g. a `<ul class="mb-ch-21"></ul>`

#### Example
	
	<ul class="mb-ch-21-xs"> <!-- Will only apply on small devices -->
		<li></li>
		<li></li>
		<li></li>
	</ul>

| Box Model Property Name| Class Abbreviation | Value | Screen size |
| ------------- | ------------- | :-----: | ------- |
| padding | p\*-ch- | *$times* sass-variable-value | - xs - sm - md - lg |
| margin | m\*-ch- | *$times* sass-variable-value | - xs - sm - md - lg |

### EBM PERCENTAGE 
___

The same as all of the above but applying a letter __"p"__ for percentage as follows: 

	<div class="mlp-ch-21-sm">
		<!-- Will target children elements based on a 100% of the parent element relative sizing -->
	</div>

### EBM ADDITIONAL CLASSES AND HELPERS
___

Additionally, I found the following helpers useful on my projects

- Background color helper classes including `.bg-white` that match the Bootstrap 3 color reference
- Minimum heights `mh-$times` and `mhp-$times`
- A `.grid-block-\*` class for adding padding top and bottom only on any element
- A `_variables.scss` sass partial for using EBM without bootstrap 3
- `.grid-list` helper classes for creating grids based on floating list items (more on this later)

#### Extras

- EBM $times variable default value is 7
- EBM $times variable values are numbers from 1 to 9 only
- EBM class abbr and property values go from (1 * $times) to (10 * $times), make sure to study your algebra
- EBM works for IE8+ with a `px` unit fallback in each class
- EBM works with _rem_ CSS units for modern browsers
- EBM _em-base_ is set to 16px 
- EBM makes use of the _px to rems_ and the _strip-units_ Sass functions from [bourbon.io](http://bourbon.io)
