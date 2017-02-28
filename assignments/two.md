# Ticktastic - Assignment One

## Where we have come.

In the last small assignment you had a go at editing javascript unsupervised and you did it! You're web developers now! But not very thorough ones I'm afraid. The department is demanding more features, and even worse it has come to the attention of your QA department that there is _already_ a security hole in your brand new application. Oh noes!

Before we can start layering in new features we need to patch this up!

## What has gone wrong?

Up until now we've been reading from and writing to the DOM in a rather cavalier fashion, forgetting the number one rule of user input: "The User is Hostile". We can even extend this to "The World is Hostile" and we should never, ever trust any data we did not explicitly write or generate ourselves. Especially when working clientside, as with JS in the browser.

Your application has a problem known as a "Cross Site Scripting" vulnerability and we need to defened against it.

## How do we plug this leak?

The problem has arisen in these lines of code:

    template = template.replace('{{ title }}', values.details);
    template = template.replace('{{ name }}', values.name);

    $list.html(template);

The data stored in `values` has come from the user, and we're injecting it into our document for them 'unescaped'. Your job is to replace these lines of code with... something else. Like the last assignment, only a few lines of code will need changing in your app, but there's a wealth of new knowledge to be had around those lines. Unlike the lat assignment, this one is part code based, and part written submission. Here's how I'd like you to approach this:

  1. Read around cross site scripting (XSS) attacks a bit.
  2. Attack your own site and demonstrate that users can execute arbitrary scripts on your page, by getting the browser to pop up an alert window. Then note down how you did it and send that to me. (In as few words as you can manage, no need to write an essay!)
  3. Install Mustache using npm. (Make sure you save it to your package.json!)
  4. Replace the above lines with something smarter, and push to github when you're happy it all works, then let me know.
  5. YEAH! You're XSS free, well done! But, why does it matter? I can open my console in Chrome and run code locally, so how is XSS different from that? A surprising number of professional developers are unaware of how XSS can be used as an attack vector, and so fail to consider it. It is one of the most commonly exploited weaknesses on the web. To make sure *you're* a true pro, please write up one example of how a XSS vulnerability may be exploited by a hacker, to demonstrate that you fully understand the dangers. Any will do, but the more serious the better.

## Some resources / Further reading

This is a hard concept to get up to speed on, so it's good to start with the absolute basics; here's Tom Scott in a noisy hotel lobby explaining those basics: https://www.youtube.com/watch?v=L5l9lSnNMxg And (Tom again) explaining a real world XSS exploit: https://www.youtube.com/watch?v=zv0kZKC6GAM

Once you've seen those, sites like this can give you a more in-depth version: https://excess-xss.com/

After this you should all be able to defeat puzzle one here: https://xss-game.appspot.com The other puzzles are a bit trickier, but very valuable if you have the time.
