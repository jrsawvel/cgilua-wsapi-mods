# cgilua-wsapi-mods


August 2018 update.

In the spring of 2018, I used Lua to create a simple, web-based, static site generator, called [Sora](https://github.com/jrsawvel/Sora) that relies on the old fashioned Common Gateway Interface.

I installed the following modules.

`luarocks install cgilua`

`luarocks install wsapi`

Repos for those projects are found at these locations.

<https://github.com/keplerproject/cgilua>

<https://github.com/keplerproject/wsapi>

Although probably unnecessary, I created Sora with an API. I needed to change a few files from the above two modulesto make my code function the way that I desired.

It seems that cgilua returns only one HTTP status code: 200. I found no way to set the status code to something else, such 400-something to indicate a type of error.

cgilua relies on wsapi. I modified the following files. My changes can be found by searching for "jrs".

wsapi/sapi.lua - Added one line of code to support setting the returned HTTP status code

cgilua.lua - Added the new function `jrStatus` that takes one argument, which is the status code to return. To this file, I added code to support the PUT request type, which is used by my API code to indicate an update.

cgilua/post.lua



