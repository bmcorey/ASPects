# ASPects
## SCSS grid library
### DOCUMENTATION

**ASPECTS v0.1**

*ASPects on Alpha version* - MIT License

1. How to install
2. Dependecies
3. Usage
4. Collaboratos


#### 1.- How to install

#### 2.- Dependencies

#### 3.- Usage

In the alpha version, this tool is designed to take care about you grid layout while you can take care about the styles, using SCSS, allows to build 100% responsive & cross browser layouts.
ASPECTS built above SASS mixins and SASS extends, intuitive and easy to use.

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

We have the section, a container and five direct childs, three of them with the same class. In ASPECTS, doesn't matter which classes have you assigned to each element, is built working with DOM directly, leaving the freedom to use the classes with which you feel more confortable.

In this case, we want to achieve a three column layout with two containers sharing half of the space, we will do the next:
```scss
section 						{ width: 100%; display: flex; 
	.footer 					{ @include row(center, wrap); 
		> div 					{ 
			@include exactly(5) 		{ @include col-2; 
				 @include first(3)  	{ @include col-3; }
			}
		}
	}
}
```

#### 4.- Collaborators

* *ASP TEAM*
	* Lily Bentley
	* Joao Guerreiro
	* Luke Sherrington
	* Vincent Le Neindre
	* Mattew Hilder
	* Kelly Tester
