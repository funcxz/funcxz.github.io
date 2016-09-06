---
layout: post
title: "Size of blobs in Azure Storage account"
tagline: "F# vs Scala vs Clojure"
description: "Calculate size of blobs in Azure Storage account using Microsoft SDK"
category: "functional exercises" 
tags: [lists, f#, scala, clojure, exercises, azure, storage]
---
{% include JB/setup %}

In this functional exercise, I'm studying Azure Storage SDK to accomplish a storage size space calculation used by blobs.

**F#** AzureTypeProvider hides boilerplate code
<script src="https://gist.github.com/dkholod/0af9b17821169007cbcea34dfb028f46.js"></script>

**Scala** No build in sumBy, but sortBy, groupBy are avaliable
<script src="https://gist.github.com/dkholod/0d9793b62de05ad93f1b7ce5bb63cc44.js"></script>
 
**Clojure** Using Java interop ..
<script src="https://gist.github.com/dkholod/849ee1b8294561061c0d9c30a834bc07.js"></script>
