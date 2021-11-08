# Some Practical Points on Programming Languages

## REPL...
... is an acronym that stands for Read Evaluate Print Loop. It's a great way to toy with a language, test out an idea. Find the REPL for the language you are using. Use it often. Test things out.

## Documentation 
It is the source of truth for the features, syntax, and behavior of a language.

Every language has its own official documentation. Getting to know the documentation of a given langugae is an essential part of learning the language itself. Spend some time searching around the documentation, become familiar with it, try to understand how it is organized and structured.

When you have a question about a language, (e.g.: "what does `.reduce` do?") you might find a lot of different resources. Blog posts, tweets, tutorials, books, etc. All of those resources can be great for different reasons. But the official documentation is the ultimate source of truth.

PRO TIP: Languages evolve. Unlike English, when significant changes are made in a programming language, those changes are recorded in the documenttaion and changelog. Make sure the documentation you are working with matches the version of the langauge you are using.

## Testing
Testing is a big deal. A great developer will be able to write a suite of automated tests for their code to make sure (1) it does what they think it's doing and (2) it doesn't break while other changes are being made.
Note!
- Writing tests is often harder than making the code work in the browser. 
- Especially when you're new to a testing framework, it often takes longer than writing the code for the intended behavior. The "when" and "how" of testing can become sort of philosophical. Here, try to stay practical:
  - Test for expected behavior
  - Test how common errors are handled
  - If you're awesome, when you see a bug, write a test that would protect against that bug, then write the code to pass the test.
- Don't test other people's code. Open source libraries are well tested. Figure out where the library ends and your code begins.
