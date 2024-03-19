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
### In this lab we explored mutation testing and GUI testing. Mutation testing is the process of creating many mutations and testing it with our given tests. Tests can survive or be killed depending on the results. We also utilised the selenium IDE to do the GUI testing by creating test cases regarding logout, search, add to cart, chat bot, and delete from cart. 

# Analysis of 10 Mutants of the Range class 
## Here's a brief analysis of 10 specific mutants and insights into what their survival indicates about the test suite's coverage and sensitivity to certain changes.

### Decremented -- double local variable number 1 at line 91: This suggests the test suite did not check the behavior just below the lower boundary of the range, missing a decrement scenario.

### Incremented ++ double local variable number 1 at line 91: Similarly, an increment scenario just above the lower boundary was not covered, indicating the need for finer granularity in boundary testing.

### Decremented -- double field lower at line 105: The absence of tests specifically reacting to a direct decrease of the lower bound means direct modifications to the Range object's state aren't sufficiently tested.

### Incremented ++ double field upper at line 114: Like the decrement mutants, this shows the test suite's insufficiency in capturing minor increments to the upper boundary.

### Decremented -- double field upper at line 132: The test suite likely missed edge cases where the upper bound is slightly less than its original value, suggesting a gap in coverage for decrement operations.

### Incremented ++ double field lower at line 157: This points to a lack of tests for scenarios where the lower bound is increased, emphasizing a need for more comprehensive state mutation testing.

### Changed conditional boundary at line 157: The survival of this mutant indicates that boundary conditions, especially those that are crucial for determining range inclusivity or exclusivity, are not thoroughly tested.

### Decremented -- double local variable number 3 at line 158: The survival here suggests the tests do not account for the decrement of key variables within methods, missing potential bugs.

### Substituted 1 with -1 at line 158: This implies tests are insensitive to sign changes in the values, which could affect the logic in subtle ways not captured by the current suite.

### Greater than to greater or equal at line 161: The presence of this surviving mutant underscores a lack of testing around boundary inclusivity, an area critical for correctly defining ranges.


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

### Equivalent mutants, which do not alter the functionality from the original code, inherently cannot be detected by test suites since they don't introduce detectable faults. Their presence in the mutation analysis can misleadingly lower the mutation score, suggesting a less effective test suite than it might actually be. This is because the mutation score is calculated based on the ratio of killed mutants to the total number of non-equivalent mutants. When equivalent mutants are included in this total, they artificially inflate the number of mutants that the test suite appears unable to kill, thus decreasing the mutation score.

### From the analyses presented by Pitest, it's clear that part of the effort in improving mutation scores involved identifying and enhancing test coverage to kill mutants that survived initial testing. However, the presence of equivalent mutants complicates this process. Specifically, the inability to kill certain mutants may not reflect a deficiency in the test suite but rather the benign nature of the mutations themselves. For instance, subtle changes in the Range class that don't effectively alter its boundary conditions or behavior under specific inputs might remain undetected by even a robust test suite, not due to oversight but due to the mutants' equivalence to the original code.

### The discussion emphasizes the importance of accurately identifying equivalent mutants to refine the mutation score. Removing or accounting for these mutants can provide a more accurate representation of the test suite's effectiveness. However, the process of identifying equivalent mutants often involves manual inspection and can be inherently challenging and subjective, adding complexity to mutation testing efforts.

### Thus, while the mutation testing conducted offers valuable insights into potential areas for enhancing the test suites for Range and DataUtilities, the influence of equivalent mutants highlights an inherent limitation of mutation testing. It underlines the need for careful analysis and possibly manual review to ensure the mutation score accurately reflects the test suite's capability to detect genuine faults in the code.


# A discussion of what could have been done to improve the mutation score of the test suites

## To specifically boost our mutation score for DataUtilities and Range, here’s what we can do:

### Incorporate Diverse Data Scenarios: For DataUtilities, let's include tests with various datasets, especially focusing on edge cases like empty arrays, null values, extreme values, and datasets with a mix of positive and negative numbers.

### Conduct Boundary Value Testing on Range: With Range, it's crucial that we test boundary conditions, including the limits of the range and special cases using Double.MAX_VALUE, Double.MIN_VALUE, Double.POSITIVE_INFINITY, Double.NEGATIVE_INFINITY, and Double.NaN.

### Test Against Invalid Parameters: We need to ensure our tests for both classes rigorously check how methods handle invalid parameters, ensuring that exceptions are properly thrown and handled.

### Verify State Changes Accurately: In Range, we should meticulously test state changes such as range shifts and expansions to confirm these operations maintain the range's integrity and enforce expected boundaries.

### Explore Combination Cases: We'll test methods that combine data or ranges, making sure to cover scenarios with different datasets or ranges that are overlapping, non-overlapping, or edge-adjacent.

### Ensure Floating-point Precision: For Range, it’s important that we precisely test floating-point operations, mindful of the intricacies of floating-point arithmetic, especially in methods that calculate or compare values.

### Test Under Extreme Conditions: We should push DataUtilities and Range to their limits with tests involving large datasets or ranges spanning wide or narrow bounds to verify both performance and accuracy under stress.

### Iteratively Enhance Tests: As we evolve our code, we’ll also iteratively refine our tests, using outcomes from previous mutation tests as a guide to continually target and improve areas of weak test coverage.

### By focusing on these strategies, we’re not just aiming to enhance our mutation score; we’re working toward making our test suite more comprehensive and our codebase more robust.

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

## For DataUtilities:
### Testing Array Creation: We tested the creation of number arrays from double arrays with normal values (e.g., 4.5, 5.6) to ensure that the function correctly converts these values into Number objects. This checks the functionality against typical data.

### Null and Edge Cases: We explicitly tested methods with null inputs (e.g., createNumberArray(null)) to ensure they throw the expected exceptions, safeguarding against improper use of the API.

### Cumulative Percentages: We mocked KeyedValues to test getCumulativePercentages with predefined values, ensuring the method calculates cumulative percentages accurately for a range of input values, including zeros and positive numbers.

### Total Calculations: We tested calculateRowTotal and calculateColumnTotal methods with mocked Values2D objects, supplying various scenarios, including positive values, to verify total calculations are correct. This included handling of zero rows or columns to ensure robustness in edge scenarios.

## For Range:
### Constructor Validity: Tests were conducted with valid ranges, including negative to positive ranges, zero-length ranges (e.g., new Range(1, 1)), and ranges with bounds at extreme values of double precision to ensure the constructor sets up the range correctly under diverse conditions.

### Boundary Conditions: We tested methods like contains and intersects with values at the edges of the ranges, including exact matches to the range boundaries, to ensure correct boundary inclusivity or exclusivity as per the method's contract.

### Special Values Handling: We included tests for handling Double.NaN, Double.POSITIVE_INFINITY, and Double.NEGATIVE_INFINITY within ranges, such as expanding a range to include infinity or ensuring NaN values are handled according to the method's specifications.

### State Mutation Operations: Through methods like shift and expand, we manipulated range objects with both positive and negative deltas, and scaling factors, including tests to ensure that the shift method respects zero-crossing rules and that ranges do not become invalid after operations.

### Equality and Hashing: We ensured that ranges are equal only if their lower and upper bounds are the same, tested through equals method, and verified that hashCode is consistent with equals, providing a thorough test of the object's contract.

## General Observations:
### Mocking for Isolation: Especially in DataUtilities tests, mocking (e.g., Values2D and KeyedValues) was used to isolate the method being tested, ensuring that the tests are focused on the functionality of the method itself rather than dependencies.

### Handling Exceptions: Tests were designed to ensure that methods throw exceptions under invalid input conditions, such as passing null where it’s not allowed, thereby validating the robustness of the error handling.

### Comprehensive Testing: Across both classes, a broad range of input data was used to ensure that the functionality is tested against as wide a range of conditions as possible, including positive and negative numbers, boundaries of data types, and special floating-point values.

### This approach to testing with diverse test data ensures that the functionalities of DataUtilities and Range are thoroughly vetted for correctness, robustness, and reliability across a spectrum of possible use cases.


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
