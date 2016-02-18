# Cardiff School of Mathematics Code Club
[![Build Status](https://travis-ci.org/CardiffMathematicsCodeClub/CardiffMathematicsCodeClub.github.io.svg?branch=master)](https://travis-ci.org/CardiffMathematicsCodeClub/CardiffMathematicsCodeClub.github.io)

A repository for the Cardiff School of Mathematics Code Club: an extra
curricular club open to all.

The website for code club is located here -
http://cardiffmathematicscodeclub.github.io/

Meeting time: Thursday's 16:00-18:00 in room M/0.33.

## Runing the website locally

In order to run the website locally you need to make sure you have all the
dependencies installed. This repository uses the [Bundle](http://bundler.io/)
ruby gem to manage it's dependencies. To install bundle run the following

```
$ gem install bundle
```

Next you need to have forked this repository, you can do that by clicking the
`Fork` button in upper right part of this webpage. Then clone your fork to your
computer by running

```
$ git clone https://github.com/<your_user_name>/CardiffMathematicsCodeClub.github.io
```

Then once you are in the same folder as this README run

```
$ bundle install
```

That will install everything you need to run this site and the tests. To view
your local copy of the website run

```
$ jekyll serve 
```
 
Then open the url given in a web browser to view the site.

Any changes you make to a page should automatically updated when viewing
locally. If nothing changes, check the terminal from where jekyll has been run
to see if there are any errors.

## Contributing

### Pull Requests

Contributions are made to this site by making
[pull requests](https://help.github.com/articles/using-pull-requests/)
if you followed the installation guide above then you should already have your
own fork of this repository. You make changes to you fork and then make a pull
request against this repository containing your changes.

### Tests

There are a number of tests that we run on the site to (at least try to) ensure
that changes to the website don't break anything.

The tests check:

- That generated HTML is sensible
- Links on the website actually link to something

So *please* when you are making changes to the website and *before* you open a
pull request, run the tests to make sure you haven't broken anything which was
previously working.

You can run the tests using the following command
```
$ rake test
```
### Draft Posts

If you are making a draft post (you can do this by editing a \*.md file in the
`_drafts` folder) and want to preview it locally you can run the following.

```
$ jekyll serve --drafts
```

The draft blog post will appear as the latest post.

### Code snippets

If you wanted to highlight several lines of code and also have syntax
highlighting then you have triple back-ticks.

We do it like this (ignore the \ at the beginning of the triple back-ticks):

```
\```NAME-OF-LANGUAGE
Put the code here.
\```
```

For example, if I wanted to input the code from Q1 of the 2015/16 Computing for
Mathematics class test, I would type (again ignoring the \ before the triple
back-ticks):

```
\```python
def mysqrt(K, epsilon=.001):
    X = K / 4.0
    while abs(X ** 2 - K) > epsilon:
        X = (X + K / X) / 2
    return X

for n in range(1, 10001):  # A loop to test a bunch of values
    approx = mysqrt(n)
    true = n ** .5
    print approx, true, approx - true  # Printing the 3 results
\```
```

And in a blog it would look like:

```python
def mysqrt(K, epsilon=.001):
    X = K / 4.0
    while abs(X ** 2 - K) > epsilon:
        X = (X + K / X) / 2
    return X

for n in range(1, 10001):  # A loop to test a bunch of values
    approx = mysqrt(n)
    true = n ** .5
    print approx, true, approx - true  # Printing the 3 results
```

### Writing tests

The functional tests are class based and all classes include a 'User Story'.
Whenever a new feature/page is added to the site a corresponding test should be
written (note that at present not all tests that are needed are written).
In fact 'Test Driven Development' is the correct way to write any code:

1. Write a test
2. Check that tests fails
3. Write feature that stops test from failing

> Obey the Testing Goat! Do Nothing Until You Have a Test

![](http://orm-chimera-prod.s3.amazonaws.com/1234000000754/images/twdp_0101.png)

A great explanation of this process is given in
[this book](http://chimera.labs.oreilly.com/books/1234000000754/ch01.html)
(free to read online and where the goat image is taken from).
