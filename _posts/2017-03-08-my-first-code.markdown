---
layout: post
title:  "First line of code in Jekyll published!"
date:   2017-03-08 11:00:15 +0000
categories: code published
---


```javascript
var validationCheck = function() {
  var isEmpty = false;
  $(".data-required").each(function() {
    if (!$(this).is(":hidden")) {

      var isChecked = {
        radio: function(ele) {
          if (ele.type == "radio") {
            $("input[name='" + ele.name + "']").each(function() {
              if (ele.checked) {
                return false;
              }
            });

            return true;

          }
        },
        text: function(ele) {
          if (ele.value.length != 0) {
            console.log()
            return false;
          } else {
            return true;
          }
        }
      };

      switch (this.type) {
        case 'text':
          isChecked.text = isChecked.text(this);
          console.log(isChecked.text);
          break;
        case 'radio':
          isChecked.radio = isChecked.radio(this);
          break;
        default:
          break;
      }

      if (isChecked.text == true || isChecked.radio == true) {
        return isEmpty = true;
      }
    }
  });

  if (isEmpty) {
    return false;
  } else {
    return true;
  }
}();

console.log(validationCheck);

```
