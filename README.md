# KLOTTRAT
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/pools/c/83Kuv5N5xA)

My first amusing attempt at making my own font. 

[I blame Reddit for this](https://www.reddit.com/r/AskReddit/comments/au3iag/if_your_handwriting_was_a_font_what_would_it_be/)

It is roughly influenced by the type of graffiti I would do at the bottom of my notebooks in highschool.

I just wanted to spend some time getting into the creation of fonts and all that goes into it. 

It is *NOT* intended for sincere use, but *could* hypothetically be used for something.

I am actually trained in typography and have done courses in it, this font will not reflect that, intentionally.

![muh intropic](https://github.com/dotMavriQ/KLOTTRAT/blob/master/Klottrat_1.png?raw=true)

### Process of creation
I sketched out the font on a piece of paper. 

Researched apps that would allow me to do it easily. They don't exist. This is a true artform. 

I wanted a more sophisticated app that would allow me to vectorize photos and capture my sketches in order to create the font,
but at the end I opted to try to make it in an app.
If I have a day with more time on my hands I'll be sure to make a more sincere attempt in the near future.

Sketching on paper is far more comfortable than doing it on a screen for me, 
rendering a lot of the letters botched and fugly..which gives this font the aesthetic it deserves, I guess.

I then used some online service to convert it into all possible formats.

![muh second pic](https://github.com/dotMavriQ/KLOTTRAT/blob/master/Klottrat_2.png?raw=true)

*hahaha... yeah, it turned out _great_*.

![muh third pic](https://github.com/dotMavriQ/KLOTTRAT/blob/master/Klottrat_3.png?raw=true)

*It's the Comic Sans/Jokerman/Papyrus of 2019 people!*

![muh fourth pic](https://github.com/dotMavriQ/KLOTTRAT/blob/master/Klottrat_4.png?raw=true)


#### Commentary
If I were to redo this font to truly reflect my teenage graffiti I would put a lot more effort into standardizing each letter. 
One improvement I can see right away is spacing, which is by far the worst crime commited with this font. 

I guess if you sweat it in GIMP or the likes for a good 20 minutes while questioning your life choices you could end up with something like this.

![like this!](https://github.com/dotMavriQ/KLOTTRAT/blob/master/dotmavriqKLOTTER.jpg?raw=true)



#### Credits

I'd give some credit to Alexander Berglund-Höglund for teaching me parts of my graffiti chops when I was a kid.
Also the FC-crew, YR and the lot. You know who you are.



----

# How do I use a Webfont?



<section class="content-wrapper" style="overflow: visible;">

<div itemprop="articleBody" id="article-body" class="text-copy bodyCopy auto">

For the sake of completeness, let’s quickly run through a basic example:

    @font-face {
      font-family: klottrat;
      src: url(klottrat.woff);
    }

This creates a new web font family that can be referenced through the **font-family** or **font** shorthand property. But something’s missing here. When referencing a web font in a font stack, always make sure to include at least one fallback font in case the web font fails to load. 

Here, if **klottrat** fails to load, the browser will fall back on the generic **serif** font family:

    p {
      font-family: klottrat, serif;
    }

There’s more to fallback fonts, but let’s keep our font stack simple by including only the generic **serif** and **sans-serif** font families for the sake of this example.

This applies the regular style to paragraphs and the bold style to **strong** paragraphs:

    p {
      font-family: klottrat, serif;
    }

    p strong {
      font-weight: bold;
    }

Besides **font-weight**, **@font-face** also accepts the **font-style** and **font-stretch** property descriptors, which define styles such as italic and condensed. All three property descriptors can be used to create a single font family with multiple styles. Theoretically, this lets you create a family containing 243 individual styles (nine **font-weight** values × three **font-style** values × nine **font-stretch** values).

In practice, however, you’re limited to 27 values, since some browsers don’t support **font-stretch**. Take a look at the table below to see which browsers you can use, and look [here](http://caniuse.com/#search=font-stretch) for more detailed information.


With luck, the remaining browsers will implement the **font-stretch** property soon, and you will be able to use all 243 font classifications.

We'll see...

---

Thank you for your time.
