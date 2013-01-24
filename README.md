# Human Markup

A try to markup text, that is not marked up

Actually, there is no easy way for non-techies to mark up text for the internet. HTML and mark-down 
are way too geeky and WYSIWYG-editors are mainly producing bad code. With Human Markup we want to 
define some rules to mark up normal text only by interpreting punctuation marks, paragraphs and apostrophes.

There are a lot of tools like Twitter, Skype or Chat-Clients in general, which doesn't support any kind of rich text
but nevertheless, users find ways to work around these "problems" by using paragraphs or CAPITALS to "markup" there
texts. So, what if we try to adapt these patterns for blogs or cms' systems?

## Quote

A german quote mostly will look like this:

```
Jhon Doe says: "Lore Ipsum"!
```

So it should be compiled like that:

```html
Jhon Doe says: "<q>Lore Ipsum</q>"!
```

## Quote-Block

Depending on a small quote, a blockqote will mostly look like that:

```
John Doe says:

"Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua."!
```

So it should be compiled like that:

```html
<p>John Doe says:</p>

<blockquote><p>"Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua."!</p></blockquote>
```

## Bold

A bold word is mostly represented using caps:

```
Lorem IPSUM dolor sit amet.
```

So we it can be displayed like:

```html
Lorem <strong>ipsum</strong> dolor sit amet.
```

Another way is to use the "!" to emphase a whole sentence:

```
Lorem ipsum dolor sit amet!
```

As HTML:

```html
<strong>Lorem ipsum dolor sit amet!</strong>
```

Problems:

* Many languages (like german) are highly case sensitive, so it could be difficult to lowercase a capitalized word.

## Emphasis

Emphasis are mostly displayed using quotes. So this:

```
John Doe loves "OpenID Connect"!
```

could be displayed like that:

```html
John Doe loves <em>"OpenID Connect"</em>!
```

Problems:

* When is something an "em" and when a "q" (it could be distinguished by the use of ":" for quotes)

## Adapting from MarkDown

Not everything on [MarkDown](http://daringfireball.net/projects/markdown/) is geeky. There are a lot of patterns
that "normal" people already use.


### Unordered-Lists

compile

```
* one
* two
* three
  * three.one
  * three.two
```

to

```html
<ul>
<li>one<li>
<li>two<li>
<li>three
  <ul>
    <li>three.one</li>
    <li>three.two</li>
  </ul>
</li>
</ul>
```

### Ordered-Lists

compile

```
1. one
2. two
3. three
  3.1 three.one
  3.2 three.two
```

to

```html
<ol>
<li>one<li>
<li>two<li>
<li>three
  <ul>
    <li>three.one</li>
    <li>three.two</li>
  </ul>
</li>
</ol>
```

### Paragraphs ad Breaks

compile

```
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.

At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd 
gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

to

```html
<p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy<br />
eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua.</p>

<p>At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd<br />
gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>
```