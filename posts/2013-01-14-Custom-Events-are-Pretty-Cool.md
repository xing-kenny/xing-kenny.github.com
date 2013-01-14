<h2 align="center"><font size="16" color="blue">Custom Events are Pretty Cool</font></h2>

Compare 'Callbacks' and 'Custom Event',the latter is nore Flexible.

Callback:

	// Do callback
	options.qOpen.call();

	$("dl").faq({
	qOpen: myQuestionOpenCallback,
	qClose: myQuestionCloseCallback
	});

Custom Event ...

	// Do callback
	ans.trigger("ansOpen");

	$("dd").on("ansOpen", function() {
	alert("answer opened!");
	});
	$("dd").on("ansOpen", function() {
	alert("another things!");
	});

By trigger,other developers can bind their stuff to this custom event and do their own thing.

[Callback demo],
[Custom Event demo]

see more :
[Custom Events are Pretty Cool]

[Callback demo]: ./posts/ansCallback.html
[Custom Event demo]: ./posts/ansCustomEv.html
[Custom Events are Pretty Cool]: http://css-tricks.com/custom-events-are-pretty-cool/
