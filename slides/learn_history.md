<!SLIDE >
# Getting better over time
## We've got a small history of these things now

* Manually fixed 5-10 modules broken by a `puppetlabs/mysql` update.
* Discovered a crashing bug when a module had a zero-byte `init.pp` file.
    * Identified all the 218 modules affected.
    * Ranked and evaluated by usage and ecosystem impact.
    * Scripted pull request run instead of yanking the release.
    * Fun fact: I ran this from the floor of *Puppetize Live: Amsterdam*.
* We're doing this 2-3 times a year now.
* Learning each time, maybe we can do more?
