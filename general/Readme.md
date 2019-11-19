## Precaution for reading this
I have provided references to give people/organisation their due but it is prescribed not to click on them yet. 
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