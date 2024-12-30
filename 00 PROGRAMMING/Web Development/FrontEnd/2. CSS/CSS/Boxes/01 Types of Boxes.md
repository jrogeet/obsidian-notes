---
topic: javascript
---
Tags/Topics: #css #boxmodel
∗:[[01 Javascript|JavaScript]] 

---
# 01 Types of Boxes

--- 
>[!info] Block-level Elements/Boxes
> - Blocks of contents which __occupies 100% of parent's element width__
> - Stacked vertically by default
> >[!example] Default elements
> >body, main, header, footer, section, nav, aside, div, h1-h6, p, ul, ol, li, etc.
> >
> >__with CSS:__ display: block



>[!info] Inline Elements/Boxes
>- Occupies only space __necessary for its content__
>- Causes __no line-breaks__ after or before the element
>- ___Heights and Widths___ do not apply
>- __Paddings and Margins__ are applied ___only horizontally___ (left and right)
>>[!example] Default Elements
>>a, img, strong, em, button, etc.
>>
>>__with CSS__: display: inline

>[!abstract] Inline-Block Boxes
> - looks like Inline from the __outside__, behaves like block-level on the __inside__
> - Occupies only content's space
> - Causes no line-breaks
> - Box-model applies
>>[!example] 
>>__with CSS:__ display: inline-block