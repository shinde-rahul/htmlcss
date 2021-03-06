###Lesson 6

#Working with Typography

The field of web typography has grown substantially over time. There are a couple of different reasons for its rise in popularity; one widely acknowledged reason is the development of a system for embedding our own web fonts on a website.

In the past we were limited to a small number of typefaces that we could use on a website. These typefaces were the most commonly installed fonts on computers, so they were the most likely to render properly on-screen. If a font wasn’t installed on a computer, it wouldn’t render on the website either. Now, with the ability to embed fonts, we have a much larger palette of typefaces to choose from, including those that we add to a website.

While the ability to embed fonts gives us access to countless new typefaces, it’s also important for us to know the basic principles of typography. In this lesson we’re going to take a look at some of these basic principles and how to apply them to our web pages using HTML and CSS.


### Typeface vs. Font

The terms “typeface” and “font” are often interchanged, causing confusion. Here is a breakdown of exactly what each term means.

A typeface is what we see. It is the artistic impression of how text looks, feels, and reads.

A font is a file that contains a typeface. Using a font on a computer allows the computer to access the typeface.

One way to help clarify the difference between a typeface and a font is to compare them to a song and an MP3. A typeface is very similar to a song in that it is a work of art. It is created by an artist or artists and is open to public interpretation. A font, on the other hand, is very similar to an MP3 in that it is not the artistic impression itself, but only a method of delivering the artistic value.

### Adding Color to Text
Typically one of the first decisions we’ll make when building a website is choosing the primary typeface and text color to be used. While there are a number of other properties that can be changed—size, weight, and so on—the typeface and text color generally have the largest impact on the look and legibility of a page. Getting rid of the browser defaults and using our own typeface and text color immediately begins setting the tone of our page.

The only property we need to set the color of text is the color property. The color property accepts one color value, but in many different formats. These formats, as we discussed in Lesson 3, “Getting to Know CSS,” include keywords, hexadecimal values, and RGB, RGBa, HSL, and HSLa values. Hexadecimal values are the most prevalent, as they provide the most control with the least amount of effort.

Let’s take a look at the CSS required to change the color of all the text within the <html> element on a page:

```
html {
  color: #555;
}
```

### Changing Font Properties
CSS offers a lot of different properties for editing the look and feel of text on a page. These properties fit into two categories: font-based properties and text-based properties. Most of these properties will be prefaced with either font-* or text-*. To begin we’ll discuss the font-based properties.


####Font Family

The font-family property is used to declare which font—as well as which fallback or substitute fonts—should be used to display text. The value of the font-family property contains multiple font names, all comma separated.

The first declared font, starting from the left, is the primary font choice. Should the first font be unavailable, alternative fonts are declared after it in order of preference from left to right.

Font names consisting of two or more words need to be wrapped in quotation marks. Additionally, the last font should be a keyword value, which will use the system default font for the specified type, most commonly either sans-serif or serif.

The font-family property in action looks like this:

```
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

In this case, Helvetica Neue is the preferred font to display. If this font is unavailable or not installed on a given device, the next font in the list—Helvetica—will be used, and so on.

####Font Size

The font-size property provides the ability to set the size of text using common length values, including pixels, em units, percentages, points, or font-size keywords.

Here the CSS is setting a font-size of 14 pixels on the <body> element:

```
body {
  font-size: 14px;
}
```

####Font Style

To change text to italics, or to prevent text from being italicized, we’ll use the font-style property. The font-style property accepts four keyword values: normal, italic, oblique, and inherit. Of these four, the most commonly used are italic (sets text to italic) and normal (returns text to its normal style).

The following CSS sets all elements with a class of special to include a font-style of italic:

```
.special {
  font-style: italic;
}
```

####Font Variant

It doesn’t happen often, but occasionally text will need to be set in small capitals, also known as small caps. For this specific case we’ll use the font-variant property. The font-variant property accepts three values: normal, small-caps, and inherit. The most typically seen values are normal and small-caps, which are used to switch typefaces between normal and small caps variants.

To switch all elements with a class of firm, we’ll use a font-variant of small-caps:

```
.firm {
  font-variant: small-caps;
}
```

####Font Weight

Occasionally, we’ll want to style text as bold or to change the specific weight of a typeface. For these cases we’ll use the font-weight property. The font-weight property accepts either keyword or numeric values.

Keyword values include normal, bold, bolder, lighter, and inherit. Of these keyword values, it is recommended to primarily use normal and bold to change text from normal to bold and vice versa. Rather than using the keyword values bolder or lighter, it’s better to use a numeric value for more specific control.

In practice, here’s the CSS to set the font-weight to bold for any element with the class of daring:

```
.daring {
  font-weight: bold;
}
```

The numeric values 100, 200, 300, 400, 500, 600, 700, 800, and 900 pertain specifically to typefaces that have multiple weights. The order of these weights starts with the thinnest weight, 100, and scales up to the thickest weight, 900. For reference, the keyword value of normal maps to 400 and the keyword bold maps to 700; thus, any numeric value below 400 will be fairly thin, and any value above 700 will be fairly thick.

Changing the font-weight to 600 for any element with the class of daring now renders that text as semibold—not quite as thick as the bold keyword value from before:

```
.daring {
  font-weight: 600;
}
```

####Typeface Weights

Before using a numeric value, we need to check and see whether the typeface we are using comes in the weight we’d like to use. Attempting to use a weight that’s not available for a given typeface will cause those styles to default to the closest value.

For example, the Times New Roman typeface comes in two weights: normal, or 400, and bold, or 700. Attempting to use a weight of 900 will default the typeface to the closest related weight, 700 in this case.

####Line Height

Line height, the distance between two lines of text (often referred to as leading) is declared using the line-height property. The line-height property accepts all general length values, which we covered in Lesson 3, “Getting to Know CSS.”

The best practice for legibility is to set the line-height to around one and a half times our font-size property value. This could be quickly accomplished by setting the line-height to 150%, or just 1.5. However, if we’re working with a baseline grid, having a little more control over our line-height using pixels may be preferable.

Looking at the CSS, we’re setting a line-height of 22 pixels within the element, thus placing 22 pixels between each line of text:

```
body {
  line-height: 22px;
}
```

Line height may also be used to vertically center a single line of text within an element. Using the same property value for the line-height and height properties will vertically center the text:

```
.btn {
  height: 22px;
  line-height: 22px;
}
```

This technique may be seen with buttons, alert messages, and other single-line text blocks.

####Shorthand Font Properties

All of the font-based properties listed earlier may be combined and rolled into one font property and shorthand value. The font property can accept multiple font-based property values. The order of these property values should be as follows, from left to right: font-style, font-variant, font-weight, font-size, line-height, and font-family.

As a shorthand value, these property values are listed from left to right without the use of commas (except for font names, as the font-family property value uses commas). A forward slash, /, separator is needed between the font-size and line-height property values.

When using this shorthand value, every property value is optional except the font-size and font-family property values. That said, we can include only the font-size and font-family property values in the shorthand value if we wish.

```
html {
  font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

#### Font Properties All Together

Let’s take a look at an example that uses all these font-based properties together. The following HTML and CSS demonstrates the different possibilities when styling text.

HTML
```
<h2><a href="#">I Am a Builder</a></h2>

<p class="byline">Posted by Shay Howe</p>

<p>Every day I see designers and developers working alongside one another. They work intelligently in pursuit of business objectives. They work diligently making exceptional products. They solve real problems and take pride in their work. They are builders. <a href="#">Continue&#8230;</a></p>
```

CSS
```
h2,
p {
  color: #555;
  font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
a {
  color: #0087cc;
}
a:hover {
  color: #ff7b29;
}
h2 {
  font-size: 22px;
  font-weight: bold;
  margin-bottom: 6px;
}
.byline {
  color: #9799a7;
  font-family: Georgia, Times, "Times New Roman", serif;
  font-style: italic;
  margin-bottom: 18px;
}
```
![](Screen Shot 2016-01-21 at 10.05.10 AM.png)


### CSS Pseudo-Classes

The demonstration here uses the :hover CSS pseudo-class, something we’ve never seen before. For reference, pseudo-classes are keywords that may be added to the end of a selector to style an element when it’s in a unique state.

The :hover pseudo-class styles an element when a user hovers over that element. When used with the <a> element, as shown here, all <a> elements will receive unique styles when they are hovered over. Now our <a> elements will change color upon being hovered over.




##Applying Text Properties
Knowing how to set the family, size, style, variant, weight, and line height of a font is only half the battle. Additionally we can decide how to align, decorate, indent, transform, and space text. Let’s start with text alignment.

###Text Align

Aligning text is an important part of building a rhythm and flow on a page; we do this using the text-align property. The text-align property has five values: left, right, center, justify, and inherit. All of these values are fairly straightforward; as expected, they align text to the left, right, or center, or they justify text.

The following CSS sets all paragraph text to be center aligned:

```
p {
  text-align: center;
}
```

The text-align property, however, should not be confused with the float property. The text-align values left and right will align text within an element to the left or right, whereas the float values left and right will move the entire element. Sometimes the text-align property will give us the desired outcome, and other times we may need to use the float property.

###Text Decoration

The text-decoration property provides a handful of ways to spruce up text. It accepts the keyword values of none, underline, overline, line-through, and inherit. Use of the text-decoration property varies, but the most popular use is to underline links, which is a default browser style.

Here the CSS styles any element with the class of note with a text-decoration of underline:

```
.note {
  text-decoration: underline;
}
```

Multiple text-decoration values may be applied to an element at once by space-separating each keyword within the value.

###Text Indent

The text-indent property can be used to indent the first line of text within an element, as is commonly seen in printed publications. All common length values are available for this property, including pixels, points, percentages, and so on. Positive values will indent text inward, while negative values will indent text outward.

Here, the CSS indents the text for all <p> elements inward by 20 pixels:

```
p {
  text-indent: 20px;
}
```

###Text Shadow

The text-shadow property allows us to add a shadow or multiple shadows to text. The property generally takes four values, all listed one after the other from left to right. The first three values are lengths, and the last value is a color.

Within the three length values, the first value determines the shadow’s horizontal offset, the second value determines the shadow’s vertical offset, and the third value determines the shadow’s blur radius. The fourth, and last, value is the shadow’s color, which can be any of the color values used within the color property.

The text-shadow property here is casting a 30% opaque black shadow 3 pixels towards the right, 6 pixels down, and blurred 2 pixels off all <p> element text:

```
p {
  text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
}
```

Using negative length values for the horizontal and vertical offsets allows us to move shadows toward the left and the top.

Multiple text shadows can also be chained together using comma-separated values, adding more than one shadow to the text. Using numerous shadows allows us to place them above and below the text, or in any variation we desire.

###Box Shadow

The text-shadow property places a shadow specifically on the text of an element. If we’d like to place a shadow on the element as a whole, we can use the box-shadow property.

The box-shadow property works just like the text-shadow property, accepting values for horizontal and vertical offsets, a blur, and a color.

The box-shadow property also accepts an optional fourth length value, before the color value, for the spread of a shadow. As a positive length value, the spread will expand the shadow larger than the size of the element it’s applied to, and as a negative length value the spread will shrink the shadow to be smaller than the size of the element it’s applied to.

Lastly, the box-shadow property may include an optional inset value at the beginning of the value to place the shadow inside an element as opposed to outside the element.

###Text Transform

Similar to the font-variant property, there is the text-transform property. While the font-variant property looks for an alternate variant of a typeface, the text-transform property will change the text inline without the need for an alternate typeface. The text-transform property accepts five values: none, capitalize, uppercase, lowercase, and inherit.

The capitalize value will capitalize the first letter of each word, the uppercase value will capitalize every letter, and the lowercase value will make every letter lowercase. Using none will return any of these inherited values back to the original text style.

The following CSS sets all <p> element text to appear in all uppercase letters:

```
p {
  text-transform: uppercase;
}
```

###Letter Spacing

Using the letter-spacing property, we can adjust the space (or tracking) between the letters on a page. A positive length value will push letters farther apart from one another, while a negative length value will pull letters closer together. The keyword value none will return the space between letters back to its normal size.

Using a relative length value with the letter-spacing property will help ensure that we maintain the correct spacing between letters as the font-size of the text is changed. It is, however, always a good idea to double-check our work.

With the CSS here, all of the letters within our <p> elements will appear .5 em closer together:

```
p {
  letter-spacing: -.5em;
}
```

###Word Spacing

Much like the letter-spacing property, we can also adjust the space between words within an element using the word-spacing property. The word-spacing property accepts the same length values and keywords as the letter-spacing property. Instead of spacing letters apart, though, the word-spacing property applies those values between words.

Here every word within a <p> element will be spaced .25 em apart.

```
p {
  word-spacing: .25em;
}
```

###Text Properties All Together

Let’s revisit our blog teaser demonstration from before, this time adding in a few text-based properties on top of our font-based properties.

HTML
```
<h2><a href="#">I Am a Builder</a></h2>

<p class="byline">Posted by Shay Howe</p>

<p class="intro">Every day I see designers and developers working alongside one another. They work intelligently in pursuit of business objectives. They work diligently making exceptional products. They solve real problems and take pride in their work. They are builders. <a href="#">Continue&#8230;</a></p>
```

CSS
```
h2,
p {
  color: #555;
  font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
a {
  color: #0087cc;
}
a:hover {
  color: #ff7b29;
}
h2 {
  font-size: 22px;
  font-weight: bold;
  letter-spacing: -.02em;
  margin-bottom: 6px;
}
h2 a {
  text-decoration: none;
  text-shadow: 2px 2px 1px rgba(0, 0, 0, .2);
}
.byline {
  color: #9799a7;
  font-family: Georgia, Times, "Times New Roman", serif;
  font-style: italic;
  margin-bottom: 18px;
}
.intro {
  text-indent: 15px;
}
.intro a {
  font-size: 11px;
  font-weight: bold;
  text-decoration: underline;
  text-transform: uppercase;
}
```
![](Screen Shot 2016-01-21 at 10.08.51 AM.png)

### Using Web-Safe Fonts
By default there are a few fonts that are pre-installed on every computer, tablet, smart-phone, or other web-browsing-capable device. Because they’ve been installed on every device, we can use these fonts freely within our websites, knowing that no matter what device is browsing our site, the font will render properly. These fonts have become known as “web-safe fonts.” There are only a handful of them, and the safest of the web-safe fonts are listed here:

- ArialCourier New, 
- CourierGaramondGeorgiaLucida Sans, 
- Lucida Grande, 
- LucidaPalatino LinotypeTahomaTimes New Roman, 
- TimesTrebuchetVerdana

### Embedding Web Fonts
We also have the ability to upload fonts to a server and include them on a website via the CSS @font-face at-rule. This capability has done wonders for online typography. Now, more than ever, typography is coming to life online.

Embedding our own web fonts looks a bit like the following CSS. First, we use the @font-face at-rule to identify our font’s name, via the font-family property, as well as the source of our font (the path to the font file containing our chosen font), via the src property. From there we are able to use this font by including its name within any font-family property value.

```
@font-face {
  font-family: "Lobster";
  src: local("Lobster"), url("lobster.woff") format("woff");
}
body {
  font-family: "Lobster", "Comic Sans", cursive;
}
```

Having the ability to embed any typeface on a website does not mean we legally have the authority to do so. Typefaces are works of art, and posting them on our server may allow others to easily steal them. The authority to use a typeface depends on the licensing we’ve been warranted.

Fortunately, the value of using new typefaces online has been recognized, and companies have begun developing ways to license and include new fonts on websites. Some of these companies, like Typekit and Fontdeck, work off a subscription model for licensing fonts, while others, like Google Fonts, license the fonts for free. Before uploading any fonts, let’s make sure we have permission to do so.


##Exercise

Following the exercise in lesson 3 you need to apply the same fonts as per the design given. You can download the font files from the link mentioned here.

- For the fonts Libre, Julius sans and baskerville you need to get it from google web fonts. 
- For the icons in the footer you need to download the font from [here](http://www.csszengarden.com/214/verdemoderna.woff) .
