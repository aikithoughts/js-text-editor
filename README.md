# js-text-editor

In this tutorial, we have a fairly basic text editor. I must admit, I think it has a bit of a wow factor. I mean, look at all the buttons!

When I started the tutorial, I wondered if there was going to be a lot of code. After all, each of the buttons must require an event listener to keep track of everything, right?
And then you have to have a lot of code to manipulate the text--change it to bold, italics, and so on. It sounded like a lot of work.

Well, it turns out it wasn't a lot of work. But the *reason* behind that fact was troublesome.

It turns out that this particular code example relies heavily on the command, [document.execCommand](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand). Using this
command meant that you didn't need a lot of code. All that was needed was to align the button ids to the commands `document.execCommand` supported. So if you want to change the text
to bold, you could just click the **Bold** button, which has an ID of `bold`. That value gets passed into the `document.execCommand` function, which handles the rest.

Great, right?

Well, sure. Except for two things:

First, you're obviously limited to whatever `document.execCommand` supports. So if you wanted to do something fancy, you'd have to rewrite your code.

Second, it turns out `document.execCommand` is a deprecated feature. When I saw that, I thought that I'd finish the tutorial, then see what I need to do to replace the deprecated feature.
Only, it turns out that there isn't a really good option (that I could find within a few minutes of Internet sleuthing) for replacing the `document.execCommand`.  Now, the good news is that
most major browsers still support the command. But I don't like building something *knowing* that it's deprecated. That seems to be a recipe for disaster.

I did some additional digging, and it seems that you can clearly work around this obsolete command. But it means this quick and easy tutorial no longer remains quick and easy. 

I think, in this case, that's okay. I didn't want to build a text editor. But I did learn a lot about deprecated commands, and found an interesting pattern that might help me avoid writing a lot of
extra code in the future.

Time will tell.