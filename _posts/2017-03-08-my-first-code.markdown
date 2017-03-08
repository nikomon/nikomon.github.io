---
layout: post
title:  "First line of code in Jekyll published!"
date:   2017-03-08 11:00:15 +0000
categories: code published
---

Function takes 2 values (elem value & elem name)

- If value is a number, func checks for dots/commas.
  - It removes dots/commas and pastes number without them to the DOM

- If value is not a number, func sets def number = 0

```javascript
function parseSum(a,b){
	c = document.getElementsByName(b)[0];
	var temp='';
	var i = 0;
	a = a.toString();
	if(Number(a)){
		if(a.indexOf('.') !== -1){
			for(i=0;i<a.length;i++){
				if(a[i]!='.'){
					temp += a[i];
				}
				else{
					i = a.length;
				}
			}
			if(Number(temp)){
				c.value = temp;
			}
			else{
				c.value = '0';
			}
		}
		else{
			c.value = a;
		}
	}
	else{
		if(a.indexOf(',') !== -1){
			for(i=0;i<a.length;i++){
				if(a[i]!=','){
					temp += a[i];
				}
				else{
					i = a.length;
				}
			}
			if(Number(temp)){
				c.value = temp;
			}
			else{
				c.value = '0';
			}
		}
		else{
		c.value = '0';
		}
		
	}

}
```
