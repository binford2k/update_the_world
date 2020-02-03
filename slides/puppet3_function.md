<!SLIDE >
# Puppet 3.x functions
## An example of this in action.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen, :type => :rvalue) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end

* Designed for a simpler time.
* Environment safety wasn't yet a concern.
* Didn't understand the cost of polluting the global namespace.
    * Module ecosystem wasn't as rich, so collisions were rare.
* Manhandling arguments marshalled into an array didn't seem like a big deal.
* Weird `:rvalue` parameters were fine; bleeding edge, remember?
    * Later on we added `:arity` too. What does that even mean?

~~~SECTION:notes~~~

* rvalue and arity are well known terms to computer scientists.
    * Most of us are not computer scientists.
* Pulluting the global namespace meant that any function could easily stomp on
  any other -- or even interfere with Puppet internals.
* Leaking across environments meant that functions often leaked into production
  long before we intended them too.

~~~ENDSECTION~~~


<!SLIDE >
# Puppet 3.x functions
## An example of this in action.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen, :type => :rvalue) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end

* But they were easy to write.
* Cut & pasted boilerplate.
* We got used to the warts.


<!SLIDE huge>
# Puppet 3.x functions
## An example of this in action.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen, :type => :rvalue) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end

### 🤷‍♀️

~~~SECTION:notes~~~
Eh. They're good enough.
~~~ENDSECTION~~~
