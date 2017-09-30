---
layout: post
title: (jQuery) keypress vs keydown vs keyup SIMPLIFIED
---

So you’re learning jQuery and you just got to events. Congrats! But now this whole keypress, keydown, keyup thing is throwing you off. Don’t worry, I can help you separate those ideas.
Let’s first start with keydown and keyup since they are easier. They are pretty self-explanatory. When a key is pressed DOWN, the keydown event is sent to an element. If the key is kept down, that event is sent to the element each time the character is repeated. This means if you have a text box and you hold down the ‘a’ key for two seconds and five a’s appear, a keydown event would have been sent 5 times if it had been listening properly to that textbox. Keyup works much in the same way except the keyup event is only sent when a key is let go of.
Now the tricky part, on to the keypress event. The keypress event is sent to an
element when a key pressed. For example, I can add a listener for the key ‘A’
rather than ‘a’. The keypress allows the user to listen for other characters
that may be modified using other keys such as the shift key. Take a look at this
html/js snippet:

{% highlight javascript %}
<body>
	<input type='text'/>
<!-- watches input and logs to
	console when 'a' or 'A' is pressed-->
	<script>
	$('input').on('keypress',function(e){
		if(e.which == 97){
			console.log('a');
		} else if(e.which == 65){
			console.log('A');
		}
	});

	$('input').on('keydown',function(e){
		if(e.which == 97||e.which == 65) {
			console.log('v');
		}
	});

	$('input').on('keyup',function(e){
		if(e.which == 97||e.which == 65) {
			console.log('^');
		}
	});
	</script>
</body>
{% endhighlight %}
