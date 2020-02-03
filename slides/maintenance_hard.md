<!SLIDE >
# Maintenance is really hard
## For projects and for infrastructures both

* Cost of supporting old features grows exponentially over time.
* Reduces the pace for improvements.
* Means that new features are harder to use.
    * Convoluted to continue supporting old functionality too.
* Breaking changes break infrastructure.
    * Must expend effort just to get back to where you were.

-----------

.callout.meh Example:<br />
it's hard to make collectors work better when people depend on the old
behaviour and weird side effects!

    @@@ Puppet
    # Inadvertently realizes every single virtual package in the catalog!
    Yumrepo <| |> -> Package<| |>

<!SLIDE >
# Maintenance is really hard

.callout.warning Sometimes it feels like we're paddling really hard just to stay where we are.

![Dog paddling ](/_images/dog_paddle.jpg)
