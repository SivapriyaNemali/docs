page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.recompute_grad


<table class="tfo-notebook-buttons tfo-api" align="left">

<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/tree/r2.0/tensorflow/python/ops/custom_gradient.py#L360-L405">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td></table>



An eager-compatible version of recompute_grad.

### Aliases:

* `tf.compat.v1.recompute_grad`
* `tf.compat.v2.recompute_grad`


``` python
tf.recompute_grad(f)
```



<!-- Placeholder for "Used in" -->

For f(*args, **kwargs), this supports gradients with respect to args, or to
gradients with respect to any variables residing in the kwarg 'variables'.
Note that for keras layer and model objects, this is handled automatically.

Warning: If `f` was originally a tf.keras Model or Layer object, `g` will not
be able to access the member variables of that object, because `g` returns
through the wrapper function `inner`.  When recomputing gradients through
objects that inherit from keras, we suggest keeping a reference to the
underlying object around for the purpose of accessing these variables.

#### Args:


* <b>`f`</b>: function `f(*x)` that returns a `Tensor` or sequence of `Tensor` outputs.


#### Returns:

A function `g` that wraps `f`, but which recomputes `f` on the backwards
pass of a gradient call.