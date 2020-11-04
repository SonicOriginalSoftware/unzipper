# Unzipper

# What is this?

This package is meant as a library and toolkit to build single-page progressive web applications.

# Another unzipper?

I wrote this library from scratch and submitted it back to the community to do with what they see fit, seeing as the node maintainers are too preoccupied to build something into the standard library.

"Why didn't you just use an existing library!?!?!?!" Well, because the ones that are popular are abandoned and the ones that aren't abandoned I don't like! Simple as that!

And when I say simple - I do mean...simple. The unzipper doesn't handle _every_ possible zip file case; but what it does handle it handles using about 550 LOC, >450 of which are boilerplate data structure code to represent the zip data structures. The actual unzipping behavior is all of ~80 LOC! All using pure, easy to understand async javascript!

# NIH syndrome, much?

The world needs to stop relying on libraries that throw in everything including the kitchen sink to do something as simple as logging. It bloats up apps and hard drive space and install times and is not good for _anybody_. Yes, even you!


# What dependencies does this require?

Only a recent version of `npm`/`npx` (`13.5`+, ideally `14.0`+)

# Fine. How do I use it?

See the [docs](docs/UNZIPPER.md)

© 2020 Nathan Blair
