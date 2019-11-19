# Precaution for reading this
I have provided references to give people/organisation their due but it is prescribed not to click on them yet. 

# Cascade
1. CSS stands for cascade style sheets.
2. So what does cascade means ?
3. The cascade is an algorithm that defines how to combine property values originating from different sources. [Ref](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
4. Read and try to understand what the above line meant.
5. Read again. 
6. If you don't then, "If you have multiple sources of css for example inline, user.css, bootstrap.css then cascade helps you resolve which property will be used to paint the element."
7. Only CSS declarations, that is property/value pairs, participate in the cascade. [Ref](https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)
8. Some property value pairs like color, font-weight etc.
9. So can you make sure that when cascade works a particular property is always applied ?
10. Yes you can. Add "!important". Not recommended. Makes your css brittle. But you should know, when everything else in your life is fucked.
11. But if multiple "!important" for a particular element and property conflicts it will again be cascaded.
12. So what is the general algorithm of how cascade works ?
13. Attributes that the CSS Cascade algorithm checks, listed in order from highest weight to least weight. [Ref](https://blog.logrocket.com/how-css-works-understanding-the-cascade-d181cd89a4d8/)
    1. Origin & Importance :- It can be your browser, you(User) or the html document(Author).
    2. Selector Specificity :- Inline styles, ID selectors, Classes / pseudo-selectors, Type selectors (for example, h1) & pseudo-elements (::before). If you have 2 CSS declarations with the same number of high-priority selectors, the resolution algorithm will consider the number of selectors at the next level of specificity. Best practice :- default to only using class selectors for your custom styles and element selectors for your default styles, it’s way easier to override styles when you actually need to. 
    3. Order of Appearance :- The last main tier of the CSS cascade algorithm is resolution by source order. When two selectors have the same specificity, the declaration that comes last in the source code wins.
    4. Initial & Inherited Properties (default values) :- Inherited properties will trickle down from parent elements to child elements. For example, the font-family & color properties are inherited. This behavior is what most people think of when they see the word “cascade” because styles will trickle down to their children.

14. So now you understand cascade and hence some css.

# Charset 

1. The @charset CSS at-rule specifies the character encoding used in the style sheet. It must be the first element in the style sheet and not be preceded by any character; as it is not a nested statement, it cannot be used inside conditional group at-rules. If several @charset at-rules are defined, only the first one is used, and it cannot be used inside a style attribute on an HTML element or inside the <style> element where the character set of the HTML page is relevant. [Ref](https://developer.mozilla.org/en-US/docs/Web/CSS/@charset)

2. How to use ? Add this at the top of you css file.

```
@charset "utf-8";

```

3. This is useful in contexts where the encoding is not told per HTTP header or other meta data, e.g. the local file system. If a reader saves the file to a hard drive and you omit the @charset rule, most browsers will read it in the OS’ locale encoding, e.g. Windows-1252, and insert â†— instead of an arrow. [Ref](https://stackoverflow.com/questions/2526033/why-specify-charset-utf-8-in-your-css-file)

4. Also to avoid xss. Not really sure how this charset is used to exploit. Once I understand I will update here.

# OneLineTips

1. Initial *Keyword* and *Value* :-  If the cascaded value of a property is the initial keyword, the property’s initial value becomes its specified value. Each property has an initial value, defined in the property’s definition table. If the property is not an inherited property, and the cascade does not result in a value, then the specified value of the property is its initial value. Initial acts as hard reset. [Ref](https://css-tricks.com/getting-acquainted-with-initial/) 

2. Inherit :- Each property has an initial value, defined in the property’s definition table. If the property is not an inherited property, and the cascade does not result in a value, then the specified value of the property is its initial value. Each property has an initial value, defined in the property’s definition table. If the property is not an inherited property, and the cascade does not result in a value, then the specified value of the property is its initial value. [Ref](https://www.w3.org/TR/CSS2/cascade.html#value-def-inherit)

3. Difference b/w Inherit and Initial :- initial and inherit are distinct in the extra step that inherit takes to check whether there are other properties it can use in the cascade before it moves to the initial value.

4. The "all" shorthand CSS property resets all of an element's properties (except unicode-bidi and direction). It can set properties to their initial or inherited values, or to the values specified in another stylesheet origin. [Ref](https://developer.mozilla.org/en-US/docs/Web/CSS/all) 
    ```
    all: initial;
    all: inherit;
    all: unset; /*Specifies that all the element's properties should be changed to their inherited values if they inherit by default, or to their initial values if not.*/
    all: revert; /* Specifies behavior that depends on the stylesheet origin to which the declaration belongs*/

    ```
5. 