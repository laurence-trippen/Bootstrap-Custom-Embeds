# Bootstrap-Custom-Embeds
Customize aspect-ratio in Bootstrap's embed-responsive class.

Bootstrap provides special CSS classes to simplify the handling of embeddings.
Embeddings refer to the following elements:

* iframe
* embed
* video
* ...

In order to embed embeddings in Bootstrap following classes are needed.

* embed-responsive
* embed-responsive-$aspect-ratio$

Example:
```html
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0=0" allowfullscreen></iframe>
</div>
```

The following aspect ratios are natively supported by Bootstrap:

* 1:1 .embed-responsive-1by1
* 4:3 .embed-responsive-4by3
* 16:9 .embed-responsive-16by9
* 21:9 .embed-responsive-21by9

If you want to use a different aspect ratio, you look into the void.
It is not difficult to define your own CSS class to solve the problem.

## 1. first you need an aspect ratio.

In this example I will use **5 : 4** as aspect ratio.
Aspect ratio = x : y = 5 : 4
x = 5
y = 4

## 2. now you have to calculate how much y of x is in percent.

Percent = (y / x) * 100

80% = (4 / 5) * 100

## 3. now we have to define our own CSS class.

Best we stick to the bootstrap spelling.
In our case, the class would look like this:

```css
.embed-responsive-5by4::before {
 padding-top: 80%;
}
```
