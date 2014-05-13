popover-template support
========================

Support for **templatable popovers** (HTML with bindings) at **Angular UI Bootstrap 0.11.0** 

This is [a long awaited feature](https://github.com/angular-ui/bootstrap/issues/220).

While the official implementation is not available, I am using this custom implementation.

Usage: [identical to the offical popover](http://angular-ui.github.io/bootstrap/#/popover); the only difference is - instead of

    popover="contents"

do not provide the `popover` attribute; use `popover-template` attribute:

    popover-template="templateUrl"


### 0.11.0

Just like the original `popover` attribute, the `popover-template` attribute accepts interpolation.

This means you can change the templateUrl at any time.

It will start loading the template as soon as a change in the interpolated attribute value is observed.

Example:

    <button popover-placement="bottom" popover-template="{{ myTemplateUrl }}" class="btn btn-default">Bottom</button>
