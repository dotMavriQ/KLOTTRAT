# KLOTTRAT
My first amusing attempt at making my own font. 
It is roughly influenced by the type of graffiti I would do in the bottom of my notebooks at school.

I just wanted to spend some time getting into the creation of fonts and all that goes into it. 

It is *NOT* intended for sincere use, but *could* hypothetically be used for something.

![muh intropic](https://github.com/dotMavriQ/KLOTTRAT/blob/master/Klottrat_1.png?raw=true)

### Process of creation
I painted the font on a piece of paper. 

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
      src: url(elena-regular.woff);
    }

This creates a new web font family that can be referenced through the **font-family** or **font** shorthand property. But something’s missing here. When referencing a web font in a font stack, always make sure to include at least one fallback font in case the web font fails to load. 

Here, if klottrat fails to load, the browser will fall back on the generic **serif** font family:

    p {
      font-family: klottrat, serif;
    }

There’s more to fallback fonts, but for now, let’s keep our font stack simple by including only the generic **serif** and **sans-serif** font families.

## Font Families

Creating a font family with multiple styles is accomplished by creating an **@font-face** rule for each style and using the same **font-family** name. The following **@font-face** rules create a family with a normal and bold style:

       @font-face {
         font-family: klottrat;
         src: url(elena-regular.woff);
         font-weight: normal;
    }
       @font-face {
         font-family: klottrat;
         src: url(elena-bold.woff);
         font-weight: bold;
    }

You can use this font family in your CSS by referencing the family name and weight in your selectors. This applies the regular style to paragraphs and the bold style to **strong** paragraphs:

    p {
      font-family: klottrat, serif;
    }

    p strong {
      font-weight: bold;
    }

Besides **font-weight**, **@font-face** also accepts the **font-style** and **font-stretch** property descriptors, which define styles such as italic and condensed. All three property descriptors can be used to create a single font family with multiple styles. Theoretically, this lets you create a family containing 243 individual styles (nine **font-weight** values × three **font-style** values × nine **font-stretch** values).

In practice, however, you’re limited to 27 values, since some browsers don’t support **font-stretch**. Take a look at the table below to see which browsers you can use, and look [here](http://caniuse.com/#search=font-stretch) for more detailed information.

<a target="_blank" data-track-type="click" data-index="4" data-component="Inline links" data-count="10">
</a>

With luck, the remaining browsers will implement the **font-stretch** property soon, and you will be able to use all 243 font classifications.

## Font Formats

The **src** descriptor tells a browser where to get a font file. The previous examples used a single font format, but you’ll often see URLs to multiple font formats combined with format hints, which are appended after the URL using the **format("value")** syntax. 

Format hints tell the browser what the format of the font file at a given URL is.

    @font-face {
      font-family: klottrat;
      src: url(klottrat-regular.woff2) format("woff2"),
           url(klottrat-regular.woff) format("woff");
    }

If you list multiple formats, modern browsers will pick the first format they support based on the format hint. Therefore, it’s important to list web font formats in the order of best compression to least. 

Even though format hints are optional, always include them – they let the browser know about the format without needing to download the font. For example, if a browser does not support WOFF2, but does support WOFF, it can skip the WOFF2 font file based on the format hint.

Browsers support several web font formats: OpenType (TrueType), EOT, WOFF, and WOFF2\. Some browsers also support SVG fonts, but they’re deprecated and should no longer be used (and should not be confused with the [new OpenType-SVG format](https://helpx.adobe.com/typekit/using/ot-svg-color-fonts.html)). 

EOT, WOFF, and WOFF2 are technically not font formats. They are compressed OpenType files with varying degrees of compression. WOFF2 offers the best compression, followed by WOFF and EOT.

In researching coverage for all browsers, you may have come across something called the [bulletproof **@font-face** syntax](http://blog.fontspring.com/2011/02/the-new-bulletproof-font-face-syntax/) by Fontspring. 

The bulletproof syntax uses EOT, WOFF2, WOFF, raw OpenType, and SVG font files for maximum browser coverage:

    @font-face {
      font-family: klottrat;
      src: url(klottrat.eot?#iefix) format("embedded-opentype"),
           url(klottrat.woff2) format("woff2"),
           url(klottrat.woff) format("woff"),
           url(klottrat.otf) format("opentype"),
           url(klottrat.svg#elena) format("svg");
    }

The first URL line might look a little odd to you. Versions of Internet Explorer 8 and below do not support the syntax for multiple font formats, and treat the entire value of the **src** property as the URL. 

The bulletproof syntax tricks Internet Explorer 8 and below into thinking that the remaining URLs are part of the fragment identifier of the first URL. Because fragment identifiers are ignored when downloading files, Internet Explorer 8 and below simply use the first URL. 

Browsers other than Internet Explorer will skip the line because they do not support EOT. 

The rest of the entries are what you would expect: font formats listed in order of preference.

But is the bulletproof syntax still relevant? No. In fact, I think it’s harmful. SVG fonts are deprecated and only supported by browsers that are no longer in use. 

Most websites support Internet Explorer 9 and up, yet the syntax lists EOT as the first preferred font format. Even though Internet Explorer 9 and up support WOFF, those versions will still download the EOT file, simply because it is listed first.

Because most websites no longer support old browsers, I highly recommend using a simplified syntax. This simplified syntax covers all modern browsers, as well as slightly older ones that are still in active use, such as Android 4.4 and earlier:

    @font-face {
      font-family: klottrat;
      src: url(klottrat.woff2) format("woff2"),
           url(klottrat.woff) format("woff"),
           url(klottrat.otf) format("opentype");
    }

Even though older Android versions are still used, worldwide reliance on these browsers is rapidly dwindling. Soon you will probably be able to drop the raw OpenType format as well, and simplify the syntax even further:

    @font-face {
      font-family: klottrat;
      src: url(klottrat.woff2) format("woff2"),
           url(klottrat.woff) format("woff");
    }

In this case, someone running an older browser will simply see your fallback fonts instead of the web font. That’s fine; they can still read the content in the fallback font.

There’s another possible value for the **src** descriptor. The **local** function takes the name of a local font family. If the font happens to be installed on the system, the browser will use that instead, thereby avoiding an extra download.

    @font-face {
      font-family: klottrat;
      src: local("klottrat"),
           url(klottrat-regular.woff2) format("woff2"),
           url(klottrat-regular.woff) format("woff");
    }

While this may seem like a great optimisation, nothing guarantees that the local font matches your web font. 

You may get a different version of the font, a font with different language support, or even an entirely different font. For that reason, I usually recommend not using the **local** function unless you find these downsides acceptable.

</div>
</div>

</section>
