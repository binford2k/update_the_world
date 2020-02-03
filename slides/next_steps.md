<!SLIDE >
# Next steps
## Finishing the port

.callout.thumbsup The automated pull request included links to the
[accompanying tutorial](https://binford2k.com/2019/11/27/automagic-function-port/)
that describes these steps on how to finish the port.

## Left as an exercise for the author:

* Port manifests to use the namespaced function name.
    * Or change it back to top-level (only if you're `stdlib`!)
* Add one or more dispatches with proper data types.
* Convert (or write) documentation to `puppet-strings` format.
* Write more tests following the example provided.

~~~SECTION:notes~~~

* The port is effectively bug-for-bug.
* Can't magically infer the parameter handling.
* Just copied docs straight over.
* Validated code, but doesn't take advantage of new features.
* Note that changing the function name makes it a ***semver breaking change***
  even if functionality is exactly the same.

https://binford2k.com/2019/11/27/automagic-function-port/

~~~ENDSECTION~~~
