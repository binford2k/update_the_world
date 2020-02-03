<!SLIDE >
# Easy to port
## First identify components:

.callout.info Function name.

    @@@ Ruby
    module Puppet::Parser::Functions
    *  newfunction(:strlen,
        :type => :rvalue,
        :doc  => "Just a naive strlen example",
      ) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end


<!SLIDE >
# Easy to port
## First identify components:

.callout.info Documentation.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen,
        :type => :rvalue,
    *    :doc  => "Just a naive strlen example",
      ) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end


<!SLIDE >
# Easy to port
## First identify components:

.callout.info Parameter validation and handling.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen,
        :type => :rvalue,
        :doc  => "Just a naive strlen example",
      ) do |args|
    *    raise "Wrong number of args" unless args.size == 1
    *    raise "Wrong type of args" unless args.first.is_a String

        args.first.length
      end
    end


<!SLIDE >
# Easy to port
## First identify components:

.callout.info Implementation.

    @@@ Ruby
    module Puppet::Parser::Functions
      newfunction(:strlen,
        :type => :rvalue,
        :doc  => "Just a naive strlen example",
      ) do |args|
        raise "Wrong number of args" unless args.size == 1
        raise "Wrong type of args" unless args.first.is_a String

    *    args.first.length
      end
    end

