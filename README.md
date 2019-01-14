# Aspects
## SCSS grid library
### DOCUMENTATION

**ASPECTS v0.1**

**Please, notice that *ASPECTS* is under development without a stable release**

*Aspects on Alpha version* - MIT License

1. How to install
2. Dependencies
3. Usage
	* Methods
4. Thanks to


#### 1.- How to install

**For last stable version**
Copy/Download the *"aspects"* directory and add it to your project, import the file *"_aspects.scss"* to your main SCSS.
```scss
	@import "$path/aspects/_aspects"

	// $path -> path to the aspects directory
```

**For development version**
Copy/Download the *"ASPects"* directory and add it to your project, import the file *"imports.scss"* to your main SCSS :
```scss
	@import "$path/ASPects/includes/scss/imports"

	// $path -> path to the aspects directory
```
or the *ASPects* main SCSS to your main SCSS file to work with the ASPects standards:
```scss
	@import "$path/ASPects/includes/scss/main"

	// $path -> path to the aspects directory
```

#### 2.- Dependencies

* **v0.1**
	* aspects 	-> Last Version ready to use of *ASPECTS*
	* img 		-> Images for Readme.md
	* includes
		* framework 	-> *ASPECTS* ready to use
		* global 	-> *ASPECTS* development
		* modules 	-> *ASPECTS* Development tests
		* imports.scss 	-> Imports file
		* main.scss 	-> *ASPECTS* base styles for testing
	* gitignore -> Files ignored by git
	* README 	-> Read me document



#### 3.- Usage

In the alpha version, this tool is designed to take care about you grid layout while you can take care about the styles. Using SCSS, ASPects allows you to build 100% responsive & cross browser layouts.
*ASPECTS*, built above SASS mixins and SASS extends, is intuitive and easy to use.

Here we have an example:
```html
<!-- THREE COLUMN FOOTER -->
	<section class="three-column">
		<div class="footer">
			<div class="footer__panels">
				<div class="panel">
					<ul>
						<li>test</li>
						<li>test</li>
						<li>test</li>
						<li>test</li>
					</ul>
				</div>
			</div>
			<div class="footer__panels">
				<div class="panel">
					<ul>
						<li>test</li>
						<li>test</li>
						<li>test</li>
						<li>test</li>
					</ul>
				</div>
			</div>
			<div class="footer__panels">
				<div class="panel">
					<ul>
						<li>test</li>
						<li>test</li>
						<li>test</li>
						<li>test</li>
					</ul>
				</div>
			</div>
			<div class="footer__menu">
				<a href="#" class="menu__link">This</a>
				<a href="#" class="menu__link">is</a>
				<a href="#" class="menu__link">a</a>
				<a href="#" class="menu__link">test</a>
			</div>
			<div class="footer__showoff">
				<a href="https://www.asp.com/exhibition-website" target="_blank">Exhibition Website by ASP</a></div>
			</div>
		</div>
	</section>
```

We have the section, a container and five direct children, three of them with the same class. In *ASPECTS*, it doesn't matter which classes you have assigned to each element. It is built to work with the DOM tags/inheritance directly, leaving the freedom to use the classes with which you feel most comfortable.

In this case, we want to achieve a three column layout with two containers sharing half of the space. We will do this:
```scss
section 							{ width: 100%; display: flex; 
	.footer 						{ @include row(center, wrap); 
		> div 						{ 
			@include exactly(5) 			{ @include col-2; background: green;
				 @include first(3)  		{ @include col-3; background: orange;}
			}
		}
	}
}
```

And here we have the result:
![Example Image](/img/test1.png)

##### 3.1.- Methods
*ASPECTS* has different methods to build the grid, for parents, children nodes and selectors:

**PARENTS**
```scss
	.selector 	{ @include row($x, $y), @content... }
	
	// row = father mixin
	// X = justify-content
	// Y = flex-wrap
```
**CHILDREN**
```scss
	.selector 	{ @include col-$n, @content... }

	// col- -> children mixin
	// $n -> Integer, it will say how much room the object has, as 1/$n , ex:
	// col-1 = mobile = 1/1, tablet = 1/1, laptop = 1/1
	// col-2 = mobile = 1/2, tablet = 1/2, laptop = 1/2
	// col-3 = mobile = 1/3, tablet = 1/3, laptop = 1/3
```
**SELECTORS**
```scss
	@include first($x) 			{ @content; }
	//It will include the first X direct children

	@include between($x,$y)			{ @content ;}
	//It will include from the X to the Y direct children

	@include last($x) 			{ @content; }
	// It will include the X last direct children

	@include exactly($x) 			{ @content; }
	// It will run when the selector contains exactly the X direct children

	@include at-least($x) 			{ @content; }
	// It will run when the selector contains at least the X direct children

	@include as-most 			{ @content; }
	// It will run when the selector contains at most the X direct children

```


#### 4.- Thanks to

*Mixin breakpoint by Joao Guerreiro*

*_qq by Daniel Guillan and Borja Miralles*


***APECTS is a SASS grid system library created by Borja Miralles under MIT license***

