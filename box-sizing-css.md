# Box-Sizing Property in CSS
## tags
#css #property #box #model

## explanation
The CSS [basic box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model) describes the layout of elemnts on the DOM via content, padding, borders, and margins. The basic model is shown below.

```
+---------------------+
|       Margin        |
| +-----------------+ |
| |     Border      | |
| | +-------------+ | |
| | |   Padding   | | |
| | | +---------+ | | |
| | | | Content | | | |
| | | +---------+ | | |
| | +-------------+ | |
| +-----------------+ |
+---------------------+
```

In the basic model, the width of an element refers only to its content box. However, with the css property `box-sizing` you can change this. By setting `box-sizing: border-box` you can directly set the width of the border box and the content box will change its size to accommodate. The default CSS box model can be used with `box-sizing: content-box`.

Some [developers](https://css-tricks.com/international-box-sizing-awareness-day/) seem to recommend setting all elements in your CSS to use the border box formatting. Putting the below styles into your stylesheets would affect all elements on your page.

```css
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
```

## sources
* https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing
* https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model
* https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model
* https://css-tricks.com/international-box-sizing-awareness-day/
* https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/
* http://asciiflow.com/ <-- ASCII Charting Webtool
