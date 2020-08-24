# Unzipper as a backend/library/API

It was my intention when creating this to keep it extensible. Which is to say: there is quite a bit I left on the table. Chiefly: all the intracies of what the zip file format is capable of (other compression methods, zip64, encryption, etc.).

Why? I just don't have the time or need of those features currently. But if the community wants to submit PRs for these extra features I would be happy to look into including them. See the [Contributing Doc](./CONTRIBUTING.md) for more information.

In addition to not implementing quite a few more capabilities of the zip file spec, I also didn't make this a front-end package (something that could be used on the command-line, or included any native GUI for it). I don't believe in housing those relationships in the same package for something as essential as a zip library. Instead, I may in the future provide a front-end/CLI that utilizes the library and release that separately. Or someone else is more than welcome to! Mostly I don't see the value in this as a substantial number of people already have a preferred system-accessible unzipping tool (`unzip`, `7zip`, `tar`, etc.).

This does also leave on the table some things you should be aware of before using:

- There are no protections against _zip bombs_. Not that I think its a bad idea to have them. I just didn't have time to think about how to protect against them in a good way and actually implement it.
- File modification times are not preserved. Again, this is more just a lack of time for implementation.

# The API

There is but one function exposed as the API: `unzip`. It accepts a buffer of the zip binary data and the root directory for where to extract the zip contents. The function parses the zip data, creates the necessary data structures, and writes the files and content to the file system asynchronously. The return of the async function is a Promise that resolves to an array of the files that were extracted.

That's it. Its about 80 LOC total and if you look at it yourself it should be pretty clear what is roughly happening even if you don't know the Zip file spec from back to front.
