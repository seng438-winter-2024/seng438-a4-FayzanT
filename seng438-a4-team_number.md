**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report \#4 – Mutation Testing and Web app testing**

| Group \#: 17      |     |
| -------------- | --- |
| Student Names: |     |
|  Shayyan Asim    |     |
|  Fayzan Toor     |     |
|   Qazi Ali  |     |
|  Rohan Kapila

# Introduction


# Analysis of 10 Mutants of the Range class 

# Report all the statistics and the mutation score for each test class



# Analysis drawn on the effectiveness of each of the test classes

# A discussion on the effect of equivalent mutants on mutation score accuracy

# A discussion of what could have been done to improve the mutation score of the test suites

# Why do we need mutation testing? Advantages and disadvantages of mutation testing
Mutation testing is a technique used to evaluate the quality of software tests. It involves modifying a program's source code in small ways (creating mutants) to create new versions of the program. Each change is designed to test different aspects of the original test suite's ability to detect errors. The main goal is to assess the effectiveness of test cases in finding potential bugs.

Advantages of Mutation Testing
High Test Effectiveness: Mutation testing helps in identifying specific weaknesses in the test suite, allowing developers to improve test cases by covering missing paths and conditions.
Quality Assurance: It provides a quantitative measure of the quality of the test suite and indirectly the reliability of the software under test.
Detailed Insight: Offers detailed insights into the test suite's capability to detect different types of errors, helping in understanding how well the software is tested.
Forces Test Improvements: Encourages developers to write more effective and comprehensive test cases, as mutation testing can reveal inadequacies in existing tests.
Disadvantages of Mutation Testing
High Computational Cost: Generating and testing all mutants can be very time-consuming, especially for large projects, making mutation testing expensive in terms of computational resources.
Equivalent Mutants Issue: Identifying equivalent mutants (mutants that do not change the program's external behavior) can be difficult and sometimes undecidable, leading to false positives in test results.
Complexity in Understanding: The concept and process of mutation testing can be complex for newcomers, requiring a significant learning curve to effectively utilize it in a project.
Tool Support and Scalability: While there are tools available for mutation testing, their effectiveness can vary, and scaling mutation testing for large and complex software systems can be challenging.
Despite its disadvantages, mutation testing is considered a powerful tool for enhancing the quality of software testing by systematically evaluating and improving test coverage and effectiveness. It pushes for a higher standard in software testing practices, albeit at the cost of increased resource consumption.






# Explain your SELENUIM test case design process

# Explain the use of assertions and checkpoints

# how did you test each functionaity with different test data

# Discuss advantages and disadvantages of Selenium vs. Sikulix
Selenium:

Advantages:

Supports multiple programming languages and browsers.
Has a large community and extensive integration options.
Precisely interacts with web elements.
Disadvantages:

Steep learning curve due to the need for programming knowledge.
Limited to web applications only.
Struggles with highly dynamic web pages.
SikuliX:

Advantages:

Uses visual matching, making it versatile for web and desktop applications.
Easy to use for beginners with a more visual approach to scripting.
Can automate any application visible on the screen.
Disadvantages:

Test stability can be affected by screen resolution or GUI layout changes.
Visual matching can be slower and may not scale well for large tests.
Image recognition's accuracy may vary, affecting test reliability.

# How the team work/effort was divided and managed


# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
