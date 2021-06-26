# HTML & CSS
## image
- A picture can say a thousand words, and great images help make the difference between an average-looking site and a really engaging one
- **stock images** these are images you pay to use
- **Online extra** an online gallery that helps you choose the right image for your website.
- Images should :
  - Be relevant
  - Convey information
  - Convey the right mood
  - Be instantly recognisable
  - Fit the color palette
- If you are building a site from scratch, it is good practice to create a folder for all of the images the site uses.
- f you are using a content management system or blogging platform, there are usually tools built into the admin site that allow you to upload images,and the program will probably already have a separate folder for image files and any other uploads.

Adding Images :
<img> it has the following attributes :
  - src : This tells the browser where it can find the image file
  - alt : This provides a text description of the image
  - title : to provide additional information about the image.
  - height :This specifies the height of the image in pixels.
  - width : This specifies the width of the image in pixels
- Where to Place Images ?
  - before a paragraph
  - inside the start of a paragraph
  - in the middle of a paragraph
- browsers show HTML elements in one of two ways :
1. Block elements always appear on a new line
2. Inline elements sit within a block level element and do not start on a new line
- **align** : The align attribute was commonly used to indicate how the other parts of a page should flow around an image.
  - should use CSS to control the alignment of images
- The align attribute can take these horizontal values:
  - left : This aligns the image to the left
  - right : This aligns the image to the right
- Aligning Images Vertically values :
  - top
  - middle
  - bottom
- Three Rules for Creating Images :
  1. Save images in the right format
  2. Save images at the right size
  3. Use the correct resolution
- Tools to Edit & Save Images :to ensure that they are the right size, format, and resolution
  - The most popular tool amongst web professionals is Adobe Photoshop.
- Images format :
  - Whenever you have many different colors in a picture you should use a JPEG.
  - Use GIF or PNG format when saving images with few colors or large areas of the same color.
    - **flat color:** picture has an area that is filled with exactly the same color Logos, illustrations, and diagrams often use flat colors
- The images you use on your website should be saved at the same width and height that you want them to appear on the page.
- edit on images :
  - REDUCING IMAGE SIZE :You can reduce the size of images to create a smaller version of the image
  - INCREASING IMAGE SIZE :You can't increase the size of photos significantly without affecting the image quality
  - CHANGING SHAPE :Only some images can be cropped without losing valuable information
- When cropping images it is important not to lose valuable information. It is best to source images that are the correct shape if possible.
- Images created for the web should be saved at a resolution of 72 ppi. The higher the resolution of the image, the larger the size of the file.
- JPGs, GIFs, and PNGs belong to a type of image format known as bitmap.
- **resolution** is the number of squares that fit within a 1 inch x 1 inch square area.
- Images appearing on computer screens are made of tiny squares called pixels.
- Vector images differ from bitmap images and are resolution-independent. Vector images are commonly created in programs such as Adobe Illustrator
  - Vector images are created by placing points on a grid, and drawing lines between those points. A color can then be added to "fill in" the lines that have been created.
  - adv using vector images :you can increase the dimensions of the image without affecting the quality of it
- Animated GIFs show several frames of an image in sequence and therefore can be used to create simple animations.
  - If the transparent part of the image has straight edges and it is 100% transparent , you can save the image as a GIF
  - If the transparent part of the image has diagonal or rounded edges or if you want a semiopaque transparency or a dropshadow, then you will need to save it as a PNG.
  - Transparent PNGs are not fully supported in older browsers,
- **<figure> element **tocontain images and their caption so that the two are associated
  - You can have more than one image inside the <figure> as long as they all share the same caption.
- **<figcaption> ** : to allow web page authors to add a caption to an image

# css
## color
- The color property allows you to specify the color of text inside an element.You can specify any color in CSS in one of three ways:
  - rgb value
  - hex codes
  - color names
- Anything between the /* symbols and the */ symbols will not be interpreted by the browser. They are shown in grey above
- background-color : sets the color of the background for that box
- If you do not specify a background color, then the background is transparent
- We have also used the padding property to separate the text from the edges of the boxes.
- Every color on a computer screen is created by mixing amounts of red,green, and blue.
- Color picking tools are available in image editing programs like Photoshop and GIMP
- RGB Values Values for red, green, and blue are expressed as numbers between 0 and 255.
- Hex Codes Hex values represent values for red, green, and blue in hexadecimal code.
- Color Names Colors are represented by predefined names.
- Hue : a color can also have saturation and brightness as well as hue.
- Saturation : refers to the amount of gray in a color
- Brightness : Brightness (or "value") refers to how much black is in a color.
- When picking foreground and background colors, it is important to ensure that there is enough ***contrast*** for the text to be legible.
- To check contrast there is a handy online tool at: www.snook.ca/technical/colour_contrast/colour.html
- **Opacity ** :specify the opacity of an element and any of its child elements. The value is a number between 0.0 and 1.0
- **rgba** property allows you to specify a color, just like you would with an RGB value,but adds a fourth value to indicate opacity This value is known as an alpha value
- hsl color property has been introduced :
  - hue This is expressed as an angle (between 0 and 360 degrees).
  - saturation
  - lightness :lightness offers both white and black and brightness but brightness only adds black
  - alpha 

## Text
- Typeface :When choosing a typeface, a browser only display it if it's installed on that user's computer.
  - Serif fonts: have extra details on the ends of the main strokes of the letters.
  - Sans-serif: fonts have straight ends to letters, and therefore have a much cleaner design
  - monospace: Every letter is the same width
  - Fantasy:Fantasy fonts are usually decorative fonts and are often used for titles
  - Cursive Cursive fonts either have joining strokes or other cursive characteristics,
- weight:can also affect the amount of white space and contrast on a page.
  - Light
  - Medium
  - Bold
  - Black
- style :
  - Normal
  - Italic :have a cursive aspect to some of the lettering
  - Oblique :take the normal style and put it on an angle
- Stretch :
  - Condensed
  - Regular
  - Extended
- There are several ways to use fonts other than those listed :
  - font-family :The value of this property is the name of the typeface you want to use.The user's computer needs the typeface installed
    - You can specify a list of fonts separated by commas so that,if the user does not have your first choice of typeface installed,the browser can try to use an alternative font from the list.
    - If a font name is made up of more than one word, it should be put in double quotes.
  - font-face :CSS specifies where a font can be downloaded from
  - Service-based Font-Face :Commercial services give users access to a wider range of fonts using @font-face.
    - @font-face allows you to use a font, even if it is not installed on the computer of the person browsing, by allowing you to specify a path to a copy of the font, which will be downloaded if it is not on the user's machine.
- Cufon offers similar functionality to sIFR. It uses JavaScript to create either an SVG or VML version of the text.
- SIFR The font is embedded into a Flash movie, and JavaScript replaces specified HTML text with a flash version of it.
- Images You can create a graphic that contains the text as you want it to appear in a different typeface
- The ***font-size*** property enables you to specify a size for the font.(pixels,percentages(The default size is 16px. 75% would be 12px, and 200% would be 32px.) and ems (An em is equivalent to the width of a letter m.))
- The ****text-transfor*** property is used to change the case of text giving it one of the following values:
  - uppercase This causes the text to appear uppercase.
  - lowercase : This causes the text to appear lowercase.
  - capitalize :This causes the first letter of each word to appear capitalized
- The text-decoration property allows you to specify the following values:
  - none: This removes any decoration already applied to the text.
  - underline: This adds a line underneath the text.
  - overline:This adds a line over the top of the text.
  - line-through:This adds a line through words.
  - blink :This animates the text to make it flash on and off.
- ***Leading *** :use for the vertical space between lines of text
- **line-height**:property sets the height of an entire line of text, so the difference between the fontsize and the line-height is equivalent to the leading
  - Increasing the line-height makes the vertical gap between lines of text larger
  - Increasing the default amount of leading can make text easier to read.
- **Kerning **is the term typographers use for the space between each letter
  - **letter-spacing** control the space between each letter
- **word-spacing** You can also control the gap between words using the
- **text-align** allows you to control the alignment of text. The property can take one of four values:
  - left
  - right
  - center
  - justify every line in a paragraph, except the last line,should be set to take up the full width of the containing box.
- **vertical-align** property is a common source of confusion it does have this effect when used with table cells (the <td> and <th> elements).
  - It is more commonly used with inline elements such as <img>,<em>, or <strong> elements.
- **text-indent **property allows you to indent the first line of text within an element.The amount you want the line indented by can be specified in a number of ways but is usually given in pixels or ems.
- **text-shadow** It is used to create a drop shadow, which is a dark version of the word just behind it and slightly offset.
- Styling Links:
  1. link :This allows you to set styles for links that have not yet been visited.
  2. visited :This allows you to set styles for links that have been clicked on.
- There are three pseudo-classes that allow you to change the appearance of elements when a user is interacting with them:
  - hover :This is applied when a user hovers over an element with a pointing device such as a mouse.
  - active:This is applied when an element is being activated by a user;
  - focus:This is applied when an element has focus. Any element that you can interact with,

- There are also a set of attribute selectors that allow you to create rules that apply to elements that have an attribute with a specific value.
  - Existence ([]) 
  - Equality (=)
  - Space (~=)
  - Prefix (^=)
  - SubString (*=)
  - Suffix ($=)














