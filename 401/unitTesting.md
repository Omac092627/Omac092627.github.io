# Unit Testing and Documentation


1. You Still Don’t Know How to Do Unit Testing (and Your Secret is Safe with Me)
    - Erik Dietrich


    What Unit Testing Isn’t

            First, let’s clear up any misconceptions by talking about what doesn’t count.  Not every test you could conceivably write qualifies as a unit test.

            If you write code that stuffs things into a database or that reads a file from disk, you have not written a unit test.  Unit tests don’t deal with their environment and with external systems to the codebase.  If it you’ve written something that can fail when run on a machine without the “proper setup,” you haven’t written a unit test.

            Unit tests also don’t count as other sorts of tests.  If you create some sort of test that throws thousands of requests for a service you’ve written, that qualifies as a smoke test and not a unit test.  Unit tests don’t generate random data and pepper your application with it in unpredictable sequences.  They’re not something that QA generally executes.

            And, finally, unit tests don’t exercise multiple components of your system and how they act.  If you have a console application and you pipe input to it from the command line and test for output, you’re executing an end-to-end system test — not a unit test.

            Make no mistake — tests that do these things add value.  They should be part of your general approach to code quality.  They just don’t fall under the heading of unit tests.




        Etymology
            Where does the term "README" come from?

            The nomenclature dates back to at least the 1970s and the PDP-10, though it may even harken back to the days of informative paper notes placed atop stacks of punchcards, "READ ME!" scrawled on them, describing their use.

            A reader1 suggested that the title README may be a playful nudge toward Lewis Carroll's Alice's Adventures in Wonderland, which features a potion and a cake labelled "DRINK ME" and "EAT ME", respectively.

            The pattern of README appearing in all-caps is a consistent facet throughout history. In addition to the visual strikingness of using all-caps, UNIX systems would sort capitals before lower case letters, conveniently putting the README before the rest of the directory's content2.

            The intent is clear: "This is important information for the user to read before proceeding." Let's explore together what constitutes "important information" in this modern age.


            Many modules: some good, some bad
                The Node ecosystem is powered by its modules. npm is the magic that makes it all go. In the course of a week, Node developers evaluate dozens of modules for inclusion in their projects. This is a great deal of power being churned out on a daily basis, ripe for the plucking, just as fast as one can write npm install.

                Like any ecosystem that is extremely accessible, the quality bar varies. npm does its best to nicely pack away all of these modules and ship them far and wide. However, the tools found are widely varied: some are shining and new, others broken and rusty, and still others are somewhere in between. There are even some that we don't know what they do!

                For modules, this can take the form of inaccurate or unhelpful names (any guesses what the fudge module does?), no documentation, no tests, no source code comments, or incomprehensible function names.

                Many don't have an active maintainer. If a module has no human available to answer questions and explain what a module does, combined with no remnants of documentation left behind, a module becomes a bizarre alien artifact, unusable and incomprehensible by the archaeologist-hackers of tomorrow.

                For those modules that do have documentation, where do they fall on the quality spectrum? Maybe it's just a one-liner description: "sorts numbers by their hex value". Maybe it's a snippet of example code. These are both improvements upon nothing, but they tend to result in the worst-case scenario for a modern day module spelunker: digging into the source code to try and understand how it actually works. Writing excellent documentation is all about keeping the users out of the source code by providing instructions sufficient to enjoy the wonderful abstractions that your module brings.

                Node has a "wide" ecosystem: it's largely made up of a very long list of independent do-one-thing-well modules flying no flags but their own. There are exceptions, but despite these minor fiefdoms, it is the single-purpose commoners who, given their larger numbers, truly rule the Node kingdom.

                This situation has a natural consequence: it can be hard to find quality modules that do exactly what you want.

                This is okay. Truly. A low bar to entry and a discoverability problem is infinitely better than a culture problem, where only the privileged few may participate.

                Plus, discoverability -- as it turns out -- is easier to address.




        Readme Best Practices
            A place to copy-paste your README.md from

            One of the most crucial things in your open source project is the README.md file. This repository has a ready-to-copy-paste template you can use for all your projects.

            Getting started
            Copy the README-default.md file for yourself and start editing! At the root of your project, run:

            curl https://raw.githubusercontent.com/jehna/readme-best-practices/master/README-default.md > README.md
            The code above fetches the README-default.md file from this repository and renames it to README.md.

            Fill with your own text
            The default template has some guiding text to get you started. However you'll need to edit the file with your own text to use it with your project.

            atom README.md
            If you're using Atom code editor, the code above opens the file for editing. If necessary, substitute with your preferred markdown editor.

            Add to git and push
            After you've filled your README.md file with your own project's text, you should push it to your GitHub project:

            git add README.md
            git commit -m "Added: README"
            git push
            This adds the README.md file to your git repository, creates a commit for it and pushes it to GitHub (or other preferred remote repository).


            About xUnit.net

                xUnit.net is a free, open source, community-focused unit testing tool for the .NET Framework. Written by the original inventor of NUnit v2, xUnit.net is the latest technology for unit testing C#, F#, VB.NET and other .NET languages. xUnit.net works with ReSharper, CodeRush, TestDriven.NET and Xamarin. It is part of the .NET Foundation, and operates under their code of conduct. It is licensed under Apache 2 (an OSI approved license).