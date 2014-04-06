popover-template support
========================

Support for **templatable popovers** (HTML with bindings) at **Angular UI Bootstrap 0.10.0** 

This is [a long awaited feature](https://github.com/angular-ui/bootstrap/issues/220).

While the official implementation is not available, I am using this custom implementation.

Usage: [identical to the offical popover](http://angular-ui.github.io/bootstrap/#/popover); the only difference is - instead of

    popover="contents"

do not provide the `popover` attribute; use `popover-template` attribute:

    popover-template="templateUrl"


Offered in three flavours, tagged as versions [0.10.0](https://github.com/jbruni/bootstrap-bower-jbruni/blob/0.10.0/ui-bootstrap-tpls.js), [0.10.1](https://github.com/jbruni/bootstrap-bower-jbruni/blob/0.10.1/ui-bootstrap-tpls.js) and [0.10.2](https://github.com/jbruni/bootstrap-bower-jbruni/blob/0.10.2/ui-bootstrap-tpls.js):

### 0.10.0

This version accepts only static strings as the templateUrl.

No parsing, no interpolation, no $eval, just the plain raw url path.

It will start loading the template at compile phase.

Example:

    <button popover-placement="bottom" popover-template="path/to/template.html" class="btn btn-default">Bottom</button>

### 0.10.1

This version will evaluate the templateUrl as an Angular expression, only once.

No interpolation. Only a single time $eval.

It will start loading the template at linking phase.

Example:

    <button popover-placement="bottom" popover-template="asset('path/to/template.html')" class="btn btn-default">Bottom</button>

### 0.10.2

This version, just like the original `popover` attribute, accepts interpolation.

This means you can change the templateUrl at any time.

It will start loading the template as soon as a change in the interpolated attribute value is observed.

Example:

    <button popover-placement="bottom" popover-template="{{ myTemplateUrl }}" class="btn btn-default">Bottom</button>


---------

implementation
==============

You can check the full diff comparing official 0.10.0 release with these custom versions at:

- [comparison of official 0.10.0 with custom 0.10.0 (static url)](https://github.com/jbruni/bootstrap-bower-jbruni/commit/1df12bba3e20e49b0ba36e6171bdba5c9255b3f7)

- [comparison of official 0.10.0 with custom 0.10.1 (one-time evaluation)](https://github.com/jbruni/bootstrap-bower-jbruni/commit/7ba84d7e660a27274e82535cd1ef7eebfd1e22d5)

- [comparison of official 0.10.0 with custom 0.10.2 (interpolation)](https://github.com/jbruni/bootstrap-bower-jbruni/commit/4a41c1e8d34ca9b4f8c7cd3862814fe4f8ae250b)

