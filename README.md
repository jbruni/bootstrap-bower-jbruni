bootstrap-bower-jbruni
======================

Support for **templatable popovers** (HTML with bindings) at Angular UI Bootstrap 0.10.0 

This is [a long awaited feature](https://github.com/angular-ui/bootstrap/issues/220).

While the official implementation is not available, I am using this custom implementation.

Usage: identical to the offical popover; the only difference is - instead of

    popover="contents"

do not provide the `popover` attribute; use `popover-template` attribute:

    popover-template="templateUrl"


Offered in three flavours, tagged as versions 0.10.0, 0.10.1 and 0.10.2:

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
