# GOAL

This is a demo to show-case how to make the form retain the context and take you back to your form without scrolling after submit.

[You can also check my other demos](https://github.com/andrerferrer/dedemos/blob/master/README.md#ded%C3%A9mos).

## What needs to be done?

### 1. Add the id in the HTML element

we do have a 
```html
<div id="reviews">
```

in the `app/views/restaurants/show.html.erb`.


### 2. Make the form take you to the anchor (to the id of the HTML element)

In the `app/views/restaurants/show.html.erb`, 
we need to specify the url to the `form` with an `anchor`:

```ruby
<%= simple_form_for([ @restaurant, @review ], url: (restaurant_reviews_path(@restaurant, anchor: 'reviews'))) do |f| %>
```

The above is better, but

We could also make the controller redirect to the anchor
```ruby
    if @review.save
      # You add an anchor to the redirection
      redirect_to restaurant_path(@restaurant)#, anchor: 'last-review'
```

### [To know more](https://www.rapidtables.com/web/html/link/html-anchor-link.html#example)

And we're good to go 🤓

Good Luck and Have Fun
