# Continuous Integration

![corgo enjoying spring](https://media.giphy.com/media/q4YpWTDb6xEha/giphy.gif)

---

WHAT IS IT????
![whaaaaat?](https://media.giphy.com/media/fpXxIjftmkk9y/giphy.gif)

---

:sunflower: Continuous Integration (CI) is a development practice that requires developers to integrate code into a shared repository/main branch early and often, several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early. :sunflower: 

---

WHO AND WHY????
![who is that?](https://media.giphy.com/media/sw7KSBKL3yme4/giphy.gif)

---

Grady Booch

![grady booch](https://www.azquotes.com/picture-quotes/quote-the-function-of-good-software-is-to-make-the-complex-appear-to-be-simple-grady-booch-60-26-39.jpg)

---

So... Continuous Integration!

![martin fowler quote](https://i.imgur.com/bqyVuQ6.jpg)

---

| Pros | Cons |
| -------- | -------- |
| free     | can go down     |
| easy to see conflicts     |      |
| remote work     |      |
| ~merge hell~     |      |
| save time |

---

Shall we try?

![travis](https://travis-ci.org/images/logos/TravisCI-Mascot-1.png)

---

[![Build Status](https://api.travis-ci.org/FAC-Sixteen/travis-practice.svg?branch=master)](https://travis-ci.org/FAC-Sixteen/travis-practice)

[![Build Status](https://travis-ci.org/hrmstockdale/test.svg?branch=master)](https://travis-ci.org/hrmstockdale/test)


---

END - QUIZ TIME

---

![kahoot](https://i.imgur.com/PQjiMNH.png)
![kahooot](https://i.imgur.com/M5EgMwI.png)



---

**What is it?**
- **Continuous Integration (CI) is a development practice that requires developers to integrate code into a shared repository/main branch early and often, several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early.**
- originally (big up Grady Booch) CI was intended to be used in combo with tests
- idea: iff working copies run and pass all unit test, then merge to the mainline
- Later concepts inc _build servers_ to implement CONTINUOUS processes running unit/integration test
- Later later came additional CONTINUOUS processes
    - static/dynamic tests
    - measure/ profile performance
    - other processes that fall under the umbrella of Quality Assurance

**What is Continuous Deployment?**
- CI is slightly different to CD. CD involves the server being set to continuously deploy successful merges to master

**Pros**

- (often) free!
- where and when changes that do/ could break the application were intro'd
- publish when ready, no need to pre-empt merge issues
- assists in dev teams ft remote members
- reduce likelihood of side-effects
- reduce likelihood of "merge hell" and SAVE TIME
    - the longer branches are checked out, greater liklihood of merge conflicts
    - integrating branches can take time, this time is not easily accounted for at the start of projects += stress. 

**CONS**

- Travis and others req maintenance and _can_ go down
    - https://www.traviscistatus.com for Travis status, the little fella is seems mighty reliable

[![Build Status](https://api.travis-ci.org/FAC-Sixteen/travis-practice.svg?branch=master)](https://travis-ci.org/FAC-Sixteen/travis-practice)

[![Build Status](https://travis-ci.org/hrmstockdale/test.svg?branch=master)](https://travis-ci.org/hrmstockdale/test)




BENEFITS

"Investing in CI results in fast feedback on code changes. Fast as in "within minutes" fast. A team that relies primarily on manual testing may get feedback in a couple hours, but in reality, comprehensive test feedback comes a day–or several days–after the code gets changed."


![martin fowler quote](https://i.imgur.com/bqyVuQ6.jpg)



**PB & J**:
"Continuous builds: Building the project as soon as a change is made. Ideally, the delta between each build is a single change-set.

Test automation: Programatic validation of the software to ensure quality. Tests can initiate actions in the software from the UI (more on that in a moment), or from within the backend services layer.

Think of these two practices like peanut butter and jelly: taste good separately, taste great together! Continuous integration pairs continuous builds with test automation to ensure that each build also assesses the quality of the code base."



---

## Useful links

https://www.atlassian.com/continuous-delivery/continuous-integration
https://www.thoughtworks.com/continuous-integration
https://travis-ci.org/
https://github.com/dwyl/learn-travis#pre-requisites

## PICS
![travis](https://images-na.ssl-images-amazon.com/images/I/B1LvPdCMfQS._SL1000_.png)

![also travis](https://travis-ci.com/images/logos/TravisCI-Full-Color-light.png)

![](https://i.imgur.com/syeoy09.png)
