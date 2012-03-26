# YAOF - Yet Another Observer Framework

Welcome to Yet Another Observer Framework... err... framework. This JavaScript component
provides a means to implement the [Observer pattern](http://en.wikipedia.org/wiki/Observer_pattern)
in your JavaScript objects.


### Getting Started
First things first. After downloading YAOF place a copy of the YAOF.js or YAOF.min.js file
into whatever place you have for JavaScript resources and include it on your pages, like so:

```
<script type="text/javascript" src="/resources/js/YAOF.min.js"></script>
```

You now have access to the YAOF object which provides what you need to begin
Observer pattern goodness. How? Here is a sample object in JavaScript that 
uses the YAOF object to publish and subscribe to events.

```
<script type="text/javascript" src="/resources/js/YAOF.min.js"></script>

<script type="text/javascript">
	var MyObjectDefinition1 = function() {
		this.DoSomethingFun = function() {
			/* Look out, I'm doing something fun. */
			this.publish("some.fun.message", { name: "SomethingFun", key: "Whatever", otherwise: "Put what you want", count: 15 });
		};
	};
	YAOF.attach(MyObjectDefinition1);


	var MyObjectDefinition2 = function() {
		this.subscribe("some.fun.message", this.IListenWell);

		this.IListenWell = function(data) {
			alert(data.name);
			alert(data.key);
			alert(data.otherwise);
			alert(count);
		};
	};
	YAOF.attach(MyObjectDefinition2);
</script>
```


### License (BSD 2-clause)
Copyright 2012 Adam Presley. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY Adam Presley "AS IS" AND ANY EXPRESS OR IMPLIED
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
EVENT SHALL Adam Presley OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR
PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE
OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
