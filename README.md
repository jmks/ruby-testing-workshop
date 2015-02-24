Ruby Testing Workshop
=====================

This repo contains an exercise for our fourth workshop presented by me, David Andrews. This workshop is about core Ruby and testing (although not TDD directly). For this session we have based our activities on Neo/Jim Weirich's Neo Ruby Koans project.

We've stepped away from our standard "quick start" setup for TDD, and have used Neo's simpler testing framework. This will allow us to focus more on the writing correct tests and less on the larger code structure. It will allow new programmers to quickly get up to speed, and the sheer number  and variety of exercises should be enough to challenge advanced devs.

###Setup

Here are the steps to get you started with the repo. We assume, naturally, that you have a working development machine with Ruby 1.9 or better on it (there are some parts of this repo that *require* Ruby 2+). At Ryatta Group we use rbenv, and so we've included some optional elements - just skip them if you're using rvm or are not versioning your Ruby.

```sh
% git clone git@github.com:k00ka/ruby-testing-workshop.git
% cd ruby-testing-workshop
% gem install bundler
Fetching: bundler-1.7.4.gem (100%)
Successfully installed bundler-1.7.4
1 gem installed
% bundle
Fetching gem metadata from https://rubygems.org/.........
Resolving dependencies...
Installing rake 10.3.2
...
Using bundler 1.7.4
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
```
######Note: if you use rbenv...
```sh
% rbenv rehash
```
You are ready!

###The Exercise

The exercises are broken out into areas by file, hashes are covered in ``about_hashes.rb``, order in the ``path_to_enlightenment.rb`` file.

Each exercise builds up your knowledge of Ruby and builds upon itself. The tests will stop at the first place you need to correct.

Some exercises simply need to have the correct answer substituted for an incorrect one.
Some, however, require that you to supply more of your own code.  If you see the method ``__`` (a double underscore) in the source, it is a hint to you to supply your own code in order to make it work correctly.

The goal is to learn the Ruby language, syntax, structure, and some common functions and libraries. By basing the exercises on tests, you'll get practice with test writing while expanding your Ruby knowledge. Testing is essential in your quest to learn and do great things in Ruby.

### Red, Green, Refactor

In TDD the mantra is <em>red, green, refactor</em>.
Write a failing test based on a requirement and watch it fail (i.e. <em>red</em>), write the simplest code possible to make the test pass (<em>green</em>), then examine the code and consider if you can make it any better (<em>refactor</em>).

When doing these exercises, the code being tested is demonstrating basic building blocks of Ruby, and therefore is already correct. Your job is to rework the tests to make them pass. Do not get confused - this is not TDD where the tests asses the correctness of the code, but an exercise designed to teach you similar useful skills where the tests need to be filled in by you.
While doing these exercises you'll run the code and identify the first test which fails (<em>red</em>), correct the test so that it passes (<em>green</em>), and then take a moment to reflect on the specifics to see what it is teaching you and improve the code to better communicate its intent (<em>refactor</em>).

## Running the tests

You can run the tests through ``rake``.
```
% cd ruby-testing-workshop
% rake
```
The very first time you run the exercises you will see the following output:
```
% rake
(in ruby-testing-workshop)
    AboutAsserts#test_assert_truth has damaged your karma.

    The Master says:
    You have not yet reached enlightenment.

    The answers you seek...
    <false> is not true.

    Please meditate on the following code:
    about_asserts.rb:10:in `test_assert_truth'
    path_to_enlightenment.rb:38:in `each_with_index'
    path_to_enlightenment.rb:38

    mountains are merely mountains
    your path thus far [X_________________________________________________] 0/280
```
You have come to your first stage. Notice it is telling you where to look for
the first solution:
```
    Please meditate on the following code:
    about_asserts.rb:10:in `test_assert_truth'
    path_to_enlightenment.rb:38:in `each_with_index'
    path_to_enlightenment.rb:38
```
Open the ``about_asserts.rb`` file and look at the first test:
```
    # We shall contemplate truth by testing reality, via asserts.
    def test_assert_truth
      assert false                # This should be true
    end
```
Change the ``false`` to ``true`` and re-run the test.  After you are
done, think about what you are learning.  In this case, ignore everything except
the method name (``test_assert_truth``) and the parts inside the method (everything
before the ``end``).

In this case the goal is for you to see that if you pass a value to the ``assert``
method, it will either ensure it is ``true`` and continue on, or fail if
the statement is ``false``.

### Running the tests automatically

<em>This section is optional.</em>

Normally the path to enlightenment looks like this:
```
% rake
 # edit file
% rake
 # edit file
% rake
 # etc...
```
If you prefer, you can keep the koans running in the background so that after you
make a change in your editor, the koans will immediately run again. This will
hopefully keep your focus on learning Ruby instead of on the command line.
```
% watchr rake-source.watchr
```
###Final Notes
If you want to learn (more) about TDD, check out our blog posts from previous workshops: [http://www.ryatta.com/refactoring-in-context/]


RubyKoans is released under a Creative Commons,
Attribution-NonCommercial-ShareAlike, Version 3.0
(http://creativecommons.org/licenses/by-nc-sa/3.0/) License.
