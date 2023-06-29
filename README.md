# Frontend Mentor - FAQ accordion card solution

This is a solution to the [FAQ accordion card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/faq-accordion-card-XlyjD0Oam). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

## Overview

### The challenge

The challenge was to build out this FAQ accordion card and get it looking as close to the design as possible. Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See hover states for all interactive elements on the page
- Hide/Show the answer to a question when the question is clicked

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- [Tailwindcss](https://tailwindcss.com/) Framework
- Flexbox
- Mobile-first workflow
- [Alpinejs](https://alpinejs.dev/) (JS framework)

### What I learned

With this project I learned what is and how to build a FAQs accordion for the web. I used **Tailwindcss** utility classes for the style and layout the way I've been studying and using this CSS framework for some time now. For the interactions on the UI I've decided to use **Alpinejs** because is a simple, lightweight and minimalistic JS framework well suited for small components with little and non complex UI funcionalities. Like Alpinejs state on its website, _"think of it like jQuery for the modern web"_. For me it is as if HTML had variables.

In the development of the FAQs accordion component I've used Alpinejs from a CDN

```html
<!-- //Alpine.js CDN -->
<script
	defer
	src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
```

Inside the accordion a pair of a question with its answer form a component wich state is tracked by Alpinejs. To achieve this we use the _**x-data**_ directive and set a reactive peace of state with the variable named **open** wich is set to false by default. The value of this variable will determine if the question's answer is been showed or not.

```html
<ul class="flex flex-col gap-4 mt-8">
	<li x-data="{open : false}">...</li>
</ul>
```

To show the answer to a question the user must click the orange arrow on the right of the question. Alpinejs tracks the UI event and mutates the reactive state for the component by toggling the **open** variable value. This interaction is possile by setting an event listener that listens for the click ( **@click="..."** ). Alpinejs also allows us to bind classes to an HTML tag depending on the state of the component with the _**x-bind:some_variable**_ directive or by using its shorthand **:some_variable** ( **:class="..."** )

```html
<button>
	<img
		@click="open =! open"
		:class="open && 'rotate-180 duration-500'"
		src="../assets/images/icon-arrow-down.svg"
		alt="" />
</button>
```

The answer is showed to the user once the event is processed and state data is mutated. The _**x-show**_ does all the magic for us by hiding or showing the real DOM element it is associated with. We can implements CSS transitions also using this directive in conjuction with the _**x-transition**_ directive. I stablished in the code a transition of 500ms

```html
<p
	x-show="open"
	x-transition.duration.500ms
	class="text-dark-grayish-blue font-light">
	You can invite up to 2 additional users on the Free plan. There is no limit on
	team members for the Premium plan.
</p>
```

In the project I've also train the skills for CSS positioning and building layouts, aswell the design skills to get the application as close to the original design as I can.

## Author

- Frontend Mentor - [@hagesake](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@hage_sake](https://www.twitter.com/yourusername)
