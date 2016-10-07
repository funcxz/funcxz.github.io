---
layout: post
title: "Capitals & Countries <| quiz game"
tagline: "F# ++ Elm"
description: "Capitals & Countries <| quiz game"
category: "functional exercises"
tags: [f#, elm-lang, azure-functions]
---
{% include JB/setup %}

This exercise starts with F# version of quiz game (for the given country, type the name of its capital city) that is 21 lines of code placed in a single F# script file.  

The [World Bank](http://www.worldbank.org/) APIs and [F# Data: WorldBank Provider](http://fsharp.github.io/FSharp.Data/library/WorldBank.html) are used to get pairs of countries and corresponding capitals.  

<script src="https://gist.github.com/dkholod/c68d8f8517ed93f2acee1f996c877f96.js"></script>  
  
Run the script on Mac terminal:
```
fsharpi CapitalsQuiz.fsx
```

or on Windows cmd:
```
fsi CapitalsQuiz.fsx
```

The next part of the exercise is to host quiz game online. I will examine [Elm language](http://elm-lang.org/) to build the game UI.
The plan is to re-use the part of F# code which delivers random pairs of countries & capitals, and host it in [Azure Functions](https://azure.microsoft.com/en-us/services/functions/).  
  
Modified version for function app:

<script src="https://gist.github.com/dkholod/55cb33f1247f820c5d095cc8af7daaa7.js"></script>
  
Elm has great support for handling HTTP requests, though F# type provider is so easy to use that I just don't want to mess directly with World Bank APIs on UI.

Elm language promotes basic pattern that breaks up into the Model, Update, and View functions. Also, I will use The [Material Design package for Elm](https://debois.github.io/elm-mdl/#cards) to compose fancy View, but the rest is going to be _vanilla_ Elm code.

Model and Messages contract:

<script src="https://gist.github.com/dkholod/b0a183ac93f4d0dab1ca1573c81469f8.js"></script>

The prime piece of Update function:

<script src="https://gist.github.com/dkholod/415961e96fc08e801420db461e70d339.js"></script>

The View function is a simple DOM composition, but if you are interested, follow the link to a [full listing](https://github.com/dkholod/functionalexercises/blob/master/Elm/CapitalsQuizMD.elm).

The big deal about Elm is that for creating reusable views, there is no need to build components, directives, templates or other stuff which is sometimes _leaky_. Instead, we code helper functions and compose the main view from it.

Helper function example:
<script src="https://gist.github.com/dkholod/03b83f1a4f8d89b95663a16182b421e1.js"></script>

Try online how this all works together - [Capitals & Countries quiz game](https://funcxz.github.io/examples/capitalsquiz.html)