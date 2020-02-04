<!SLIDE >
# Yes we can!
## (well mostly)

.callout.info It turns out that identifying the parts of a Puppet 3.x function
that we care about is almost completely automatable.

* Over the American Thanksgiving holiday, I had a little free time.
* This was a problem that had intruiged me so I dove in.
* Ruby makes it surprisingly easy to introspect into source code.
* As is tradition, I built a cleverly named tool to assist in the update.
    * https://github.com/binford2k/puppet-function-updater
    * https://binford2k.com/2019/11/27/automagic-function-port/


<!SLIDE >
# Parses function source files
## Generates replacement modern API function

    @@@ Console
    [~/Projects/puppetlabs-stdlib]$ puppet_function_updater --verbose
    INFO: Creating lib/puppet/functions/stdlib/abs.rb
    INFO: Creating lib/puppet/functions/stdlib/any2array.rb
    INFO: Creating lib/puppet/functions/stdlib/any2bool.rb
    INFO: Creating lib/puppet/functions/stdlib/assert_private.rb
    INFO: Creating lib/puppet/functions/stdlib/base64.rb
    INFO: Creating lib/puppet/functions/stdlib/basename.rb
    [...]
    INFO: Creating lib/puppet/functions/stdlib/values_at.rb
    INFO: Creating lib/puppet/functions/stdlib/zip.rb
    INFO: Functions generated. Please inspect for suitability and then
    INFO: update any Puppet code with the new function names.
    INFO: See https://puppet.com/docs/puppet/latest/custom_functions_ruby.html
    INFO: for more information about Puppet's modern Ruby function API.

* Ports old patterns to new patterns
* Generates a basic spec test for each function
* Validates each function and warns on invalid output


~~~SECTION:notes~~~

* I'm sure that some of you will be disappointed that I'm not going into tech
  details about how this thing works.
* But my slot doesn't give me time for it.
* I'll be happy to talk later, or tomorrow at our Contributor session.

~~~ENDSECTION~~~


<!SLIDE >
# Ports *most* of the function cleanly
## Legacy API doesn't capture the function signature

.callout.info Remember that the legacy API just passed all arguments as a single
untyped array and relied on the programmer to know what to do with that.

* The only part of the function that I cannot infer reliably.
* So instead, I create a `dispatch` that does the same thing.

.break

    @@@ Ruby
    dispatch :default_impl do
      # Call the method named 'default_impl' when this is matched
      # Port this to match individual params for better type safety
      repeated_param 'Any', :args
    end

.break

    @@@ Ruby
    def default_impl(*args)
        # paraeter handling and implementation copied in
    end
