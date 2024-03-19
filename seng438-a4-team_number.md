**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report \#4 – Mutation Testing and Web app testing**

| Group \#:      |     |
| -------------- | --- |
| Student Names: |     |
|     Qazi Ali           |     |
|     Shayyan Asim          |     |
|     Rohan Kapila           |     |
|     Fayzan Toor           |     |


# Introduction
In this lab we explored mutation testing and GUI testing. Mutation testing is the process of creating many mutations and testing it with our given tests. Tests can survive or be killed depending on the results. We also utilised the selenium IDE to do the GUI testing by creating test cases regarding logout, search, add to cart, chat bot, and delete from cart. 

# Analysis of 10 Mutants of the Range class 

# Report all the statistics and the mutation score for each test class


## DataUtilities Mutation Coverage 
### Increased from 32% to 59%
<img width="961" alt="image" src="https://github.com/seng438-winter-2024/seng438-a4-FayzanT/assets/113921998/048a9b27-2ee5-4cb5-84ab-7b4e19f41c74">
<img width="953" alt="image" src="https://github.com/seng438-winter-2024/seng438-a4-FayzanT/assets/113921998/faf6d822-4aac-4279-a55c-c2b11987c0e6">

## Range Mutation Coverage 
### Increased from 59% to 69%
<img width="954" alt="image" src="https://github.com/seng438-winter-2024/seng438-a4-FayzanT/assets/113921998/ac1ac714-2f90-40a0-8e4d-2b0eb42dd452">
<img width="959" alt="image" src="https://github.com/seng438-winter-2024/seng438-a4-FayzanT/assets/113921998/1e4a0310-4def-4eaa-8ccd-13660a15f9cf">


# Analysis drawn on the effectiveness of each of the test classes

# A discussion on the effect of equivalent mutants on mutation score accuracy

# A discussion of what could have been done to improve the mutation score of the test suites

# Why do we need mutation testing? Advantages and disadvantages of mutation testing
### Mutation testing is a technique used to evaluate the quality of software tests. It involves modifying a program's source code in small ways (creating mutants) to create new versions of the program. Each change is designed to test different aspects of the original test suite's ability to detect errors. The main goal is to assess the effectiveness of test cases in finding potential bugs.

## Advantages of Mutation Testing
### High Test Effectiveness: Mutation testing helps in identifying specific weaknesses in the test suite, allowing developers to improve test cases by covering missing paths and conditions.
### Quality Assurance: It provides a quantitative measure of the quality of the test suite and indirectly the reliability of the software under test.
### Detailed Insight: Offers detailed insights into the test suite's capability to detect different types of errors, helping in understanding how well the software is tested.
### Forces Test Improvements: Encourages developers to write more effective and comprehensive test cases, as mutation testing can reveal inadequacies in existing tests.
## Disadvantages of Mutation Testing
### High Computational Cost: Generating and testing all mutants can be very time-consuming, especially for large projects, making mutation testing expensive in terms of computational resources.
### Equivalent Mutants Issue: Identifying equivalent mutants (mutants that do not change the program's external behavior) can be difficult and sometimes undecidable, leading to false positives in test results.
### Complexity in Understanding: The concept and process of mutation testing can be complex for newcomers, requiring a significant learning curve to effectively utilize it in a project.
### Tool Support and Scalability: While there are tools available for mutation testing, their effectiveness can vary, and scaling mutation testing for large and complex software systems can be challenging.
### Despite its disadvantages, mutation testing is considered a powerful tool for enhancing the quality of software testing by systematically evaluating and improving test coverage and effectiveness. It pushes for a higher standard in software testing practices, albeit at the cost of increased resource consumption.






# Explain your SELENUIM test case design process


### In our Selenium test case design process, we began by identifying and prioritizing common functionalities that required testing. This initial step involved a collaborative discussion within the team, focusing on essential features of Samsung's website, such as navigating to the homepage, adding items to the cart, removing items from the cart, and interacting with the navigation bar.

### To ensure thorough coverage and reliability, we adopted a systematic approach, emphasizing the individual testing of each functionality. This isolation strategy allows for precise identification of issues related to specific features, enhancing the effectiveness of our testing efforts. By meticulously designing our test cases to target these key functionalities, we aimed to comprehensively evaluate the website's performance and usability, ensuring a seamless user experience.

### Furthermore, to refine our process and outcomes, we incorporated best practices in test case design, such as defining clear and concise test steps, establishing expected results for each action, and employing assertions to validate the correctness of the application's behavior. This structured approach not only facilitated a more organized testing workflow but also improved the maintainability and scalability of our test suite, enabling us to adapt quickly to changes in the application's features or functionality.
# Explain the use of assertions and checkpoints

### Assertions and checkpoints are used in automated testing to verify that the software behaves as expected at specific points during a test. Assertions evaluate conditions to be true or false, ensuring the application meets certain criteria. Checkpoints verify specific aspects of the application's state, like the presence of UI elements or the correctness of data output. Both are crucial for identifying defects and ensuring software quality.

# how did you test each functionaity with different test data

# Discuss advantages and disadvantages of Selenium vs. Sikulix
## Selenium:

## Advantages:

### Supports multiple programming languages and browsers.
### Has a large community and extensive integration options.
### Precisely interacts with web elements.
## Disadvantages:

### Steep learning curve due to the need for programming knowledge.
### Limited to web applications only.
### Struggles with highly dynamic web pages.
## SikuliX:

## Advantages:

### Uses visual matching, making it versatile for web and desktop applications.
### Easy to use for beginners with a more visual approach to scripting.
### Can automate any application visible on the screen.
## Disadvantages:

### Test stability can be affected by screen resolution or GUI layout changes.
### Visual matching can be slower and may not scale well for large tests.
### Image recognition's accuracy may vary, affecting test reliability.

# How the team work/effort was divided and managed
### The team work was divided in group of twos. Where each group took over one class for mutant testing. Qazi and Rohan did DataUtilities mutant coverarage where as Fayzan and Shayyan did Range mutant coverage. For GUI testing, we took over samsung's web page and each member tested two functionalities with the help of Selenium. For group report everyone did it together , we discussed each question as a group before answering it.

# Difficulties encountered, challenges overcome, and lessons learned
 ### The PITest took a long time to run for each of the cases. This made increasing the mutation coverage a bit difficult due to having to decide if we should create an abundance of test cases to test at once, or risk testing a couple and not having any increase in our coverage. We also had to make sure all our test cases passed before we ran the PITest, so this made us abandon a couple of cases that could've increased the coverage. To overcome this, we made sure to double check all our cases to make sure they passed and had meaningful additions before running the test. For Selenium, we also had some issues with having our scripts work in the recording, but not while replaying. We solved this issue by making sure we tested the function as quickly as possible to avoid delays.


# Comments/feedback on the lab itself

  ### The lab itself went pretty smooth and was staraightfoward, we learned more about mutation testing while presenting to the TA and the TA also explained some features of Selenium to us and how it is used in the industry. One feedback that we would like to give is that the lab ended really late compared to the other labs we had to wait to 2 hours to present it to the TA but overall it was a pretty good experince.
