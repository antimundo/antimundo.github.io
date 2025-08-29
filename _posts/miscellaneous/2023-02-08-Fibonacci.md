---
layout: post
title:  "Fibonacci"
categories: miscellaneous
permalink: /:categories/:title
teaser: /assets/images/posts/miscellaneous/fibonacci.jpg

excerpt: Genera los números de la espiral de Fibonacci.
---

<script>
window.onload = function() {
    fibonacci(1478, document.getElementById("fibonacci"));
}

function fibonacci(numero, element)
{
    let printText = "";
    var var1 = 0;
    var var2 = 1;
    var var3;

    printText += var1 + "\n";
    printText +=  var2 + "\n";

    for(var i=3; i <= numero;i++)
    {
        var3 = var1 + var2;
        var1 = var2;
        var2 = var3;
        printText += var3 + "\n";
    }
    element.innerText = printText;
}
</script>


Este programa genera los números de la espiral de Fibonacci, no tiene ningun uso, pero mola.

<code id="fibonacci"><code>