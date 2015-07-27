# My Name is ... what? My Name is ...who ? CSS Selectors

CSS Selectors are some of the most important things to really understand. Without selecting which text you want to apply styling, our pages would remain black text on a white background. It's important to properly select your HTML elements so you apply your styling as specifically as a possible.

<img src="https://s3.amazonaws.com/after-school-assets/css-selectors.jpg" width="300" align="right" hspace="10">

**Use these examples to help you with the next project!**


## Classes

Let's say we have a paragraph with the class `text-1` defined on it. 

```html
  <p class="text-1"> Scoop, toppings marshmellow caramel shortcake ice sherbet banana sorbet. Butter peanut butter soft serve, cheesecake sundae soft serve. Vanilla froyo cheesecake chocolate chip, raspberry, maple. Shortcake coffee caramel peppermint nut peanut butter butterscotch soft serve banana pecan coffee. Cookies and cream nut orange frozen peppermint raspberry banana toppings.</p>
```

And let's say we want to make the font color of that paragraph blue: 


```css
.text-1 {
  color: blue;
}
```

In this example, we're using `.text-1` as our CSS selector. This is telling our CSS to find a paragraph take with the class text-1 and change that font color to blue. We tell CSS to look for a class by using a `.` in front of the name of the class.

## IDs

Now let's say we have two paragraphs. Our second paragraph has the id `icecream-2`. And we want to change the font of the 2nd to Wingdings.

```html
<p> Chocolate scoop mocha, raspberry cake sorbet froyo caramel. Mocha apple almond cake mocha coffee cookies and cream almond froyo. Apple cherry cake toppings almond, cup gelato coffee. Ice soft serve white chocolate, cup ice caramel banana blueberry nut chocolate peanut butter. Sorbet flavour caramel froyo almond cake, butter gelato chunky flavour cup.</p>

<p id="icecream-2">Soft serve marshmellow toppings orange, chocolate pecan, sundae flavour sherbet banana. Marshmellow almond sundae mint froyo nut toppings mint, blueberry butterscotch apple. Chunky popsicle, dessert cone maple banana marshmellow maple ice almond banana. Nut flavour banana maple cup apple caramel cup froyo. Sundae froyo froyo soft serve banana cone scoop gelato marshmellow.</p>
```

```css
#icecream-2 {
  font-family: Wingdings;
}
```

In this example, `#icecream-2` is our CSS selector. We tell CSS that we're selecting an id named `icecream-2`.

## Descendant Selectors

In our HTML, we can set up parent and child elements by nesting elements inside one another like this:

```html
<div id="lots-of-text">
  <p>Soft serve marshmellow toppings orange, chocolate pecan, sundae flavour sherbet banana. Marshmellow almond sundae mint froyo nut toppings mint, blueberry butterscotch apple. Chunky popsicle, dessert cone maple banana marshmellow maple ice almond banana. Nut flavour banana maple cup apple caramel cup froyo. Sundae froyo froyo soft serve banana cone scoop gelato marshmellow.</p>
</div>
```

In the HTML above, the `p` tag is nested inside of a `div` with the id `lots-of-text`. We can set up a descendant selector in our CSS like this:

```css
#lots-of-text p {
  color: red;
}
```

In this example, we're using the CSS selector `#lots-of-text p`. Basically, we're saying find the ID `lots-of-text` and then look for a `p` tag inside that ID. The `p` tag is a descendant of the `div` with the id `lots-of-text`.

## Adjacaent Sibling Selector

HTML elements can be siblings if they are nested at the same level like this:

```html
<div id="lots-of-text">
  <p id="first">Soft serve marshmellow toppings orange, chocolate pecan, sundae flavour sherbet banana. Marshmellow almond sundae mint froyo nut toppings mint, blueberry butterscotch apple. </p>
  <p> Chunky popsicle, dessert cone maple banana marshmellow maple ice almond banana. Nut flavour banana maple cup apple caramel cup froyo. Sundae froyo froyo soft serve banana cone scoop gelato marshmellow.</p>
</div>
```

The two paragraphs are known as sibling elements. Because they are next to each other they are "adjacent siblings"

If we wanted to select the paragraph NEXT TO the paragraph with the id `first`, we'd write our CSS like this:

```css
#first + p {
  font-size: 50px;
}
```

We used the CSS selector `#first + p`. In this case, we're saying apply the styling to the `p` tag that is next to an HTML tag with the id `first`.

## Attribute Selector

You'll notice that the `img` tag can have lots of attributes (`src` which is the source of the img, `alt`, which is the text that will show up in case the image is broken, etc.) We can use an attribute selector to select an HTML element based on the value of a specific attribute:

```html
<img src="http://www.auntebbysicecream.com/000802_c297_0033_cslp.jpg" alt="3 Cones">
<img src="https://upload.wikimedia.org/wikipedia/commons/d/da/Strawberry_ice_cream_cone_(5076899310).jpg" alt="1 cone">
```

So let's say we want to add a border to an image that has the alt text `1 cone`:

```css
img[alt="1 cone"] {
  border-style: solid;
  border-width: 5px;
  border-color: green;
}
```

In this example, our CSS selector is `img[alt="1 cone"]`. This selector is saying lets find an `img` tag with the `alt` attribute that is storing the value `1 cone`. Once it finds that, it will add a 5px wide solid green border to that image. 