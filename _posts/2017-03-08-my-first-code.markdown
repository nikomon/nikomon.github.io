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
          var radioIsChecked = false;
          if (ele.type == "radio") {
            $("input[name='" + ele.name + "']").each(function() {
              console.log(this.checked);
              if (this.checked) {
                radioIsChecked = true;
                return true;
              }
            });

            return (radioIsChecked) ? true : false;

          }
        },

        text: function(ele) {
          if (ele.value.length != 0) {
            return false;
          } else {
            return true;
          }
        }
      };

      switch (this.type) {
        case 'text':
          isChecked.text = isChecked.text(this);
          break;
        case 'radio':
          isChecked.radio = isChecked.radio(this);
          break;
        default:
          break;
      }

      if (isChecked.text == true || isChecked.radio == false) {
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
```
