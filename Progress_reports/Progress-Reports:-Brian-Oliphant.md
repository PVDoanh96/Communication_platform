##11/18/2012

**What you said you were going to do this week.**

Fix the old tests to keep up with the updates to the code. Implement more tests with the new features. Investigate testing the email confirmations somehow.

**What you did this week.**

Fixed the broken old tests. Implemented some more tests (some unit tests, some functional tests). Updated the other tests. Tests tests tests. As far as testing emails - doesn't seem to be possible to test automatically (can obviously manually check receipt of email). Read receipts can be sent - but they aren't mandatory responses. Instead currently testing of email confirmation just ignores the actual email part and uses the tokens from the email to complete testing. None of this is live though because other updates are breaking these tests too.

**What you are going to do next week.**

Look into stress testing. Keep up to date on tests and features (editing groups, comments, anything else). Fix the new tests. Add more tests. Investigate other ways to test.

**Issues.**

New tests broke with more updates. So I haven't pushed anything right now - I think someone removed some stuff from requirements.txt - will need to investigate before I push.


##11/12/2012

**What you said you were going to do this week.**

Need to write some functional tests as well as updating any tests we have with the addition of new features. I've been investigating the use of Selenium, and I think that's going to be a powerful testing tool moving forward for upper level testing. Also should start looking at features for the next release.

**What you did this week.**

Got Selenium up and running (kind of) - has been a very cool learning experience. Functional tests are getting implemented. We should now be much more aware of cross browser issues. Kind of looked at other features, didn't really do anything with them though. I've also been keeping track of where the old tests are now breaking - need to update them though.

**What you are going to do next week.**

Fix the old tests to keep up with the updates to the code. Implement more tests with the new features. Investigate testing the email confirmations somehow.

**Issues.**

Old tests broke with new updates. Not sure how/if I should stress test.


##11/4/2012

**What you said you were going to do this week.**

Bring the prototype forward to a testable state. Right now it uses some 'framework' stuff that isn't super conducive to testing. Need to flesh that stuff out. Also should pair up and get a testing suite not just started but decently developed.

**What you did this week.**

Wrote unit testing for the models. Making sure the foundation stuff worked. The code at this point is pretty testable at a lower level (groups, posts) - and I think it's mostly covered now. Just tried to make sure things were properly functioning for the first release.

**What you are going to do next week.**

Need to write some functional tests as well as updating any tests we have with the addition of new features. I've been investigating the use of Selenium, and I think that's going to be a powerful testing tool moving forward for upper level testing. Also should start looking at features for the next release.

**Issues.**

None at the moment.



##10/28/2012

**What you said you were going to do this week.**

First week I have made an individual status report, so nothing here I guess.

**What you did this week.**

Wrote some stuff for the section assignment, just a dummy list generator (for testing) and then a testing method to check that our sorting algorithms work. Also there was our presentation that I did a slide for on our process.

**What you are going to do next week.**

Bring the prototype forward to a testable state. Right now it uses some 'framework' stuff that isn't super conducive to testing. Need to flesh that stuff out. Also should pair up and get a testing suite not just started but decently developed.

**Issues.**

None at the moment. Just need to get down and code.