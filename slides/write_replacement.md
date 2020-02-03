<!SLIDE >
# Easy to port
## Then write replacements:

.callout.info Function name.

    @@@ Ruby
    # @summary
    #   Just a naive strlen example
    * Puppet::Functions.create_function(:'mymod::strlen') do
      # @param value
      #   The string to calculate the length of
      # @return [Integer]
      #   The length of the input string
      dispatch :default_impl do # invoke default_impl method when matched
        param 'String', :value
      end

      def default_impl(value)
        value.length
      end
    end


<!SLIDE >
# Easy to port
## Then write replacements:

.callout.info Documentation.

    @@@ Ruby
    * # @summary
    * #   Just a naive strlen example
    Puppet::Functions.create_function(:'mymod::strlen') do
    *  # @param value
    *  #   The string to calculate the length of
    *  # @return [Integer]
    *  #   The length of the input string
      dispatch :default_impl do # invoke default_impl method when matched
        param 'String', :value
      end

      def default_impl(value)
        value.length
      end
    end


<!SLIDE >
# Easy to port
## Then write replacements:

.callout.info Parameter validation and handling.

    @@@ Ruby
    # @summary
    #   Just a naive strlen example
    Puppet::Functions.create_function(:'mymod::strlen') do
      # @param value
      #   The string to calculate the length of
      # @return [Integer]
      #   The length of the input string
    *  dispatch :default_impl do # invoke default_impl method when matched
    *    param 'String', :value
    *  end

      def default_impl(value)
        value.length
      end
    end


<!SLIDE >
# Easy to port
## Then write replacements:

.callout.info Implementation.

    @@@ Ruby
    # @summary
    #   Just a naive strlen example
    Puppet::Functions.create_function(:'mymod::strlen') do
      # @param value
      #   The string to calculate the length of
      # @return [Integer]
      #   The length of the input string
      dispatch :default_impl do # invoke default_impl method when matched
        param 'String', :value
      end

    *  def default_impl(value)
    *    value.length
    *  end
    end
