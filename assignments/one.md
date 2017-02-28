# Ticktastic - Assignment One

## What we have seen in the workshop.

In our last adventure, we concocted a lo-fi prototype of an app. We sketched out some markup in HTML and gently styled it in CSS before moving on to some Javascript basics. Using events, we hooked into the browsers form-submission, and replaced it's usual behaviour with something more to our liking, by storing the contents of the form to localStorage. Once we'd captured this innocent form-data, we reflected it back to the user by pulling it from localStorage, and writing it to the DOM.

We've seen and used: events, reading from the DOM with jQuery, writing to the DOM with jQuery and linking scripts to a page. We've also hurriedly used the mysterious `JSON` object to both `stringify()` and `parse()` data. Finally, we've declared arbitrary objects, such as `values = {}`, and assigned arbitrary data to those objects, which we've later recalled. Not bad for less than fifty lines of code.

But not good enough yet for our purposes!

## Whatever next?

There are many issues with our app as it now stands, but the next one I wish to address is this; when one reports an issue, any previous issues are displaced and overwritten. unless IT works _very_ quickly indeed, this will swiftly cause tension in our offices.

We need to adjust the application in such a way that more than one issue can be written at a time.

## But how?

Firstly, we need to *store* multiple tickets, instead of just a single ticket, and secondly we need to *recall* those tickets, and output them to the DOM.

For the first issue, we should look to where in the JS we are writing to localStorage, and instead of simply writing, we will need to look up existing items and add to them, if they exist. An example from a similar system I'm working on would look like this:

    function storeWorkout(name, intervals) {
        var newItem = {name: name, intervals: intervals};
        var currentItems = JSON.parse(window.localStorage.getItem('workouts'));
        if (!currentItems) {
            currentItems = [];
        }
        currentItems.push(newItem);
        window.localStorage.store(JSON.stringify(currentItems));
    }

Although this won't work exactly in your code, it should give you a flavour for what your code should look like.

Recalling and displaying the new array of tickets, instead of the previous single ticket, can be carried out in a similar manner.

Handy terms to Google for this problem are `Array` and `loop` or `forEach`. These are common programming constructs, so ensure any documentation you work from is javascript based! (Although the general principles are common across languages, the syntax us very different.)

Have a go. If you get stuck and Google fails you, drop me a line on slack and I'll give you a few hints and tips.

## The Admin Stuff

I've bought all of your current 'ticktastic' repos into line with the end of the workshop, so you're all starting from the same place. You should be able to simply `git pull` and all my changes will be there.

You'll need to work on your changes and commit, then push to github. Once on github, notify me and I'll pull in your changes and give you feedback.

If you need a quick refresher on git, give this a go: https://try.github.io/levels/1/challenges/1 or drop me a line on slack.

Try to enjoy yourselves and I'll have another assignment for you in a week.
