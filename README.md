# ui-testing-workshop

## Audience

UI developers - anybody that works on front-end at all

## Notes / discussion with Nicholas Boll

testing is historically considered an aspect of quality control
reframe it as key to developer experience
- easier to develop new things aka "to write code"
- easier to make changes - reacquiring context - or getting the context you never had before because you didn't write it
- confidence
- codifying context -> what's in my head now
  - specifications for what the code should do
  - implies BDD
  - don't document implementation -> may help to have an example of test code that is hard to get context of
  - describing in terms of features, user experience
  - value of "should"
  - value of matchers - using the right ones or even making custom ones
  - timebomb tests - find example for a version-based one that goes away when you upgrade a dep

test from the outside perspective rather than the inside
if this fails, is it OK or not OK -> codify your assumptions, because sometimes the assumptions will change

test failure: expects (true) to be (false) -> not good
you can add context to a failure
this is also where a matcher could be useful to describe what actually "fails"
- show how this gives you more context
- show how failure is useful or not

"frontload maintenance work"

what gives us the most **meaningful** feedback - to develop as fast as possible
a little extra work to apply BDD

internals vs externals
- implemenation should be able to change - find Enzyme example
- 

what is our "environment?"
- avoid developing against SUVs
- don't develop in your full application stack, develop in a development stack
- invest into development environments
- develop in layers, not in mocks / layer your stack, don't mock your stack

Jest + React Testing Library
- mostly unit tests
- where our developer-based tests are

- always use get queries not find - why? find are asynchronous, run get under the hood
- intentionality of it should be there vs it may not be there yet
- never use query unless you have to test for the non-existance
- getByRole - cover the "order of queries" - what you should be looking things up by, i.e. data-testid is a last resort


Cypress
- integration of frontend, maybe end to end, but doesn't have to be
- where our user-based tests are
- we may get into evangelizing Cypress for more than this - failures are easier to debug
- storybook vs component runner
- cover the command queue
  - queue is maintained in state, can be queried
- context may include Selenium, what came before it
  - runs in the browser
- every query is an assertion


I used to see nested describes as a way to de-dupe code - but this can go overboard - becomes harder to understand context of what is being execute - beforeEach/beforeAll
"building & compiling in your head" - don't do it

