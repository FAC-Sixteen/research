# TEST COVERAGE

![cover](https://media.tenor.com/images/10599cbc5ab58bfedacc017c07ad667a/tenor.gif)

---

#### What is test coverage?

* measures the amount of testing performed by a set of test.
* information about which parts of a program are actually executed when running the test


---

#### Why is test coverage useful?
* Identifies meaningless test cases that do not increase coverage
* It can assure the quality of the test
* The 100% code coverage problem.


---

#### What's istanbul?
* a code coverage utility written in js

`npm install istanbul -D`

![Istanbul](https://media.giphy.com/media/ngjisbfyGSGPe/giphy.gif)

---

#### What's nyc?
* nyc makes istanbul more readable, and tells you exactly where your issues are (with line references!)

`npm install nyc -g`

![NYC](https://media.giphy.com/media/3oFyD4xKncK6ptR7qg/giphy.gif)


---

![all tests pass](https://i.imgur.com/JUjjd68.png)

---

![the four coverages](https://i.imgur.com/ONMxUaa.png)
![coverage summary](https://i.imgur.com/BIL83FW.png)

---

![untested function](https://i.imgur.com/FMl0kBG.png)

---

![untested if statement](https://i.imgur.com/oddLGcA.png)

---

![false positive](https://i.imgur.com/3FFWD6Z.png)

---

![a bit of testing](https://i.imgur.com/mdD2IPK.png)

---

![no testing](https://i.imgur.com/nuDvNSL.png)

---

![nyc](https://i.imgur.com/0RrNPfj.png)

---

![nyc with spotty coverage](https://i.imgur.com/dDiabRm.png)

---

![that's all](https://media.giphy.com/media/3o6gDY8zzwvNQdFCaQ/giphy.gif)

---

#### Useful links

https://istanbul.js.org/ istanbul home page

https://www.guru99.com/test-coverage-in-software-testing.html good concise descriptions of what test coverage is, what it does, and some benefits to it

https://github.com/istanbuljs/nyc github for nyc, which is a command line interface for istanbul.

https://blog.cloudboost.io/the-importance-of-code-coverage-9b4d513f39b4 blog post explaining basic code coverage

---




Statement Coverage concerns the smallest possible units available to a programmer, such as assignments, assertions, return statements, loops, and conditionals.

Branch Coverage is an evaluation of the number of logical branches evaluated in your code. For example, in an if-else block, both conditions are considered a branch.

Function Coverage refers to the number of functions in your code that were tested.

Line Coverage is straightforward — its the number of lines of code your tests evaluated.

---

code coverage utility: hook into your source code and your test suite and return statistics on how much of your code is actually covered by your tests

"it is the measure of the effectiveness of the testing by providing data on different items"

"Amount of testing performed by a set of test cases is called Test Coverage. By amount of testing we mean that what parts of the application program are exercised when we run a test suite. In other words, test coverage is defined as a technique which determines whether our test cases are actually covering the application code and how much code is exercised when we run those test cases. When we can count upon some things in an application and also tell whether the test cases are covering those things of application, then we can say that we measure the coverage. So basically the coverage is the coverage items that we have been able to count and see what items have been covered by the test. The test coverage by two test cases executed can be the same but the input data of 1 test case can find a defect while the input data of 2 nd cannot. So with this we understand the 100% coverage does not mean 100% tested."

![three software abstractions](https://i.imgur.com/UQf62Mp.png)

"A program with high test coverage, measured as a percentage, has had more of its source code executed during testing, which suggests it has a lower chance of containing undetected software bugs compared to a program with low test coverage."

github can show a codecov badge in the readme -- codecov.

aim for 100%, but it still doesn't mean your code is bulletproof
OR SHOULD YOU
![the 100% code coverage problem](https://i.imgur.com/hDD2AYi.png)
"code coverage doesn’t tell you anything about the quality of your tests"


---

Why do we do Test Coverage?
We perform Test coverage analysis for the following reasons.

To find the areas in specified requirement which is not covered by the test scenarios and cases.
By determining the test coverage we can create more test cases to increase our test coverage.
By performing the test coverage we can measure how much modafinil online from india testing is covered. This indirectly means the check on quality of the application.
We can also identify some useless test cases which don’t have meaning in being executed and thus omit them.
Testing Life becomes smooth by managing the risk based testing approach.
Traceability between the requirements and the test cases can be achieved by this technique.
Impact analysis and change tracking can be determined if we have proper test coverage.

---
![advantages and disadvantages](https://i.imgur.com/rp5liCy.png)

---
### How do we perform Test Coverage Analysis?
* Test Coverage can be implemented by Static testing techniques. (Static testing -> https://www.tutorialspoint.com/software_testing_dictionary/static_testing.htm) These test techniques include peer reviews, code inspections and code walkthroughs.
* We can convert the adhocs defects into test cases and analyse test coverage.
* We can use code level tools and automation to achieve test coverage at unit level.
* We can use test management tools to perform functional test coverage which will establish traceability between, requirements, defects and test cases.
* We can use Bi- directional traceability matrix to achieve test coverage.

---

### Best Practices of Test Coverage in Software Testing!

* We should perform maintenance activities and cleanup activities at frequent intervals of time.
* We should maintain metrics to measure the test coverage percent.
* Usage of test management tools is good practice to have control over all aspects of coverage from requirements, test cases and defects.
* Quality gate mechanism should be proper to verify the results.
