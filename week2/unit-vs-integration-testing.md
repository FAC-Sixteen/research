# Unit vs Integration Testing
![Dog typing](https://media.giphy.com/media/sqVGLWmCrSaBy/giphy.gif)

---

## 🍰 Unit vs Integration 🎂

- **Unit tests** ensure that individual parts of your code work as expected
- **Integration tests** ensure that those individual parts work together as expected 

---

| Unit 🍰 | Integration 🎂 |
| -------- | -------- |
| Isolated from other components|Testing how components work together|
| Faster     | Slower - more complex     |
| More unit tests     | Fewer integration tests     |
| Performed prior to integration testing|Performed once you know the individual units work|
| Used in development | Used to spot errors before deployment |

---

### What is a unit test? 👩‍💻
![slices](https://media.giphy.com/media/ADreUN1EVGkQo/giphy.gif)

---

- Unit testing is a process in which the **smallest testable parts** of an application, called units, are **individually and independently tested** for proper operation. 📝

- It involves only those characteristics that are **vital** to the performance of the unit under test

---

- Unit testing is a **component of test-driven development** (TDD) (where the developer should write failing tests first) 

- Unit test code should be **short and quick to execute**.

---


### When would you use unit testing? 
![Cat tapping on a screen](https://media.giphy.com/media/eiXQ2yop9tYPK/giphy.gif)

---

- Making sure that each unit of the code performs as designed.
- ![Unit Test Example](https://i.imgur.com/3cHKSVH.png)

---

- Test the functionality of individual units only.

- More complex functions = more unit tests

![BulletProof Code](https://media.giphy.com/media/l0HlwfPNp0zlaXfVe/giphy.gif)

bulletproofFunc()



---

### Why you should use unit testing? 🤩


---

- The earlier a problem is identified, the **fewer compound errors occur**.
- **Debugging is easy**. When a test fails, only the latest changes need to be debugged. 
- It increases **confidence in changing and maintaining code**.


---


- **Development is faster**. If you have unit testing in place, you write the test, write the code and run the test instead of opening GUI and providing random inputs. 
- **The cost (time, effort, destruction) of fixing a defect detected during unit testing is lesser** in comparison to that of defects detected at higher levels.
- Code is **more reliable**.


---


### What is an integration test? 
![use integration testing](https://cdn-images-1.medium.com/max/1200/1*xHibbXdcePT0GtpeZRgxSA.gif)

- Integration tests are for checking how well different parts of the system work together
-  e.g. seeing how your backend database interacts with your frontend user interface

---

### Integration testing can be done in 3 ways:
- Big Bang Approach 💥
- Top Down Approach 🎩
- Bottom(s) Up Approach 🍻
  

---


  
  

### Big Bang Approach 💥
- Combining all modules once and varifying the functunality after completion of individual module testing. 
- e.g If we had two modules, we'd test each separately(unit testing!!!). Then we'd test them both after combining the two.

---

### Stubs & Drivers 🚙
- Testing is carried out by *dummy modules* known as __stubs & drivers__
- These are used to stand in for missing components to simulate data communication between modules
- **Stub** - used if a page is not ready for integration testing - e.g. faking a HTTPS response (top-down)
- **Driver** - used if a process is not ready - e.g. faking a login process (bottom-up)

---

### Top Down Approach 🎩
- Testing takes place from top to bottom
- High-level modules are tested first then low-level modules
- Intergration of the low-level modules to high-level modules to ensure the system is working as intended
- Uses Stubbs

---

### Bottom Up Approach 🍻
- Opposite of __Top Down__
- Testing takes place from bottom to top
- Lowest level modules are tested first the high-level modules
- Finally, intergrating the high-level modyles to low-level modyules to ensure the system is working as intended
- Uses Drivers


---

### When would you use integration testing? 🚀

Some examples:
* using a database in your application
* pulling data from an external API (e.g. Google maps)

You would use integration testing to make sure these systems work with your code



---


### When would you use integration testing? 🚀

General situations:
* where unit testing is not enough
* need to check that two systems are working together
* writing integration tests usually requires more complexity e.g. setting up a test database, so use integration only when necessary

---


## Questions??

![](https://media.giphy.com/media/PK4XAT9Ususco/giphy.gif)



---

### 👩‍🏫 Useful resources:

https://codeutopia.net/blog/2015/04/11/what-are-unit-testing-integ
ration-testing-and-functional-testing/

https://searchsoftwarequality.techtarget.com/definition/unit-testing (Good intro to unit testing)

https://stackoverflow.com/questions/1383/what-is-unit-testing (Stack Overflow question: "I saw many questions asking 'how' to unit test in a specific language, but no question asking 'what', 'why', and 'when'.")

---

https://www.sitepoint.com/javascript-testing-unit-functional-integration/

http://softwaretestingfundamentals.com/unit-testing/ (Unit testing methods, tasks, benefits and tips)

https://www.youtube.com/watch?v=SxXd60UNllA (Short video on Integration testing 5min)

---
