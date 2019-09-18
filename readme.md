# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:

1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
1. Why the test failed at first?
1. Why you corrected the test that way?
1. Do you have further questions on this knowledge point?

## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`

Learnings:
a) BooleanOperatorsTest
- The point of this exercise is to be familiarized with boolean operator and bitwise operation.
  In this exercise i learned how to use bitwise operations such as & (AND), | (OR), and ~ (COMPLEMENT).
  
* should_perform_logical_boolean_operations()
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
 - The use of boolean operators.
2. Why the test failed at first?
 - The expected result is empty wherein an array of boolean operators is expected.
3. Why you corrected the test that way?
 - It is the answer for the Actualresult.
4. Do you have further questions on this knowledge point?
 - None.
 
* should_do_bitwise_and_boolean_operation()
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
 - To be familiar with bitwise operation & (AND).
2. Why the test failed at first?
 - The expected result is 0 wherein an integer is expected.
3. Why you corrected the test that way?
 - It is the answer for the Actualresult.
4. Do you have further questions on this knowledge point?
 - None.
 
* should_do_bitwise_or_boolean_operation()
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
 - To be familiar with bitwise operation | (OR).
2. Why the test failed at first?
 - The expected result is 0 wherein an integer is expected.
3. Why you corrected the test that way?
 - It is the answer for the Actualresult.
4. Do you have further questions on this knowledge point?
 - None.
 
 * should_do_bitwise_not_operation()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with bitwise operation ~ (NOT/COMPLEMENT).
 2. Why the test failed at first?
  - The expected result is 0 wherein an integer is expected.
 3. Why you corrected the test that way?
  - It is the answer for the Actualresult.
 4. Do you have further questions on this knowledge point?
  - None.
 
b) CharTypeTest
 - This exercise aims to familiarize us the different types of escape characters. 
   For this exercise, i didn't knew that there are other escape characters such as Carriage Return and i am not also familiar with the other term of newline (linefeed).
   
 * should_describe_escaped_chars()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with different type of escape characters in Java.
 2. Why the test failed at first?
  - The expected result is blank for all the escape characters.
 3. Why you corrected the test that way?
  - It is the appropriate escape character.
 4. Do you have further questions on this knowledge point?
  - None.
   
c) FloatingTypeTest
 - This exercise aims to familiarize us with the numerical float types (double/float). 
   For this exercise, I learned the new methods of checking if infinity, nan and rounding up float numbers.
   
 * should_not_get_rounded_result_if_convert_floating_number_to_integer()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with type casting from double to int.
 2. Why the test failed at first?
  - The expected result is not 0.
 3. Why you corrected the test that way?
  - It is the appropriate answer for type casting double to int.
 4. Do you have further questions on this knowledge point?
  - None.

 * should_judge_special_double_cases()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with methods of double for checking if NAN or INFINITE number.
 2. Why the test failed at first?
  - Method for checking throws exception. No appropriate handling inside the method yet.
 3. Why you corrected the test that way?
  - It is the appropriate answer for checking if NAN or INFINITE.
 4. Do you have further questions on this knowledge point?
  - None.
  
 * should_not_round_number_when_convert_to_integer()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with type casting from double to int.
 2. Why the test failed at first?
  - The expected result is not 0.
 3. Why you corrected the test that way?
  - It is the appropriate answer for type casting double to int.
 4. Do you have further questions on this knowledge point?
  - None.
  
 * should_round_number()
 1. What is the knowledge point of the test? Where is the official document to the knowledge point?
  - To be familiar with pre-defined method for rounding up numbers.
 2. Why the test failed at first?
  - The expected result is not 0.
 3. Why you corrected the test that way?
  - It is the appropriate answer for rounding up number.
 4. Do you have further questions on this knowledge point?
  - None.
  
  
d) IntegerTypeTest
 - This exercise aims to familiarize us different methods that can be used for the Integer type such as getting maximum,minimum,etc.
   This exercise is quite challenging for me since i am not that familiar with java and its methods. I've learned how to use predefined MAXIMUM and MINIMUM value of long and shot data type.
   
     * should_get_range_of_primitive_int_type()
     1. What is the knowledge point of the test? Where is the official document to the knowledge point?
      - To be familiar with pre-defined constant for getting maximum and minimum limit of an integer.
     2. Why the test failed at first?
      - The expected result is not 0.
     3. Why you corrected the test that way?
      - It is the appropriate answer for getting the minimum and maximum limit of an integer.
     4. Do you have further questions on this knowledge point?
      - None.
  
    * should_get_range_of_primitive_short_type()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
    - To be familiar with pre-defined constant for getting maximum and minimum limit of a short data type.
    2. Why the test failed at first?
    - The expected result is not 0.
    3. Why you corrected the test that way?
    - It is the appropriate answer for getting the minimum and maximum limit of a short data type.
    4. Do you have further questions on this knowledge point?
    - None.
   
   * should_get_range_of_primitive_long_type()
   1. What is the knowledge point of the test? Where is the official document to the knowledge point?
    - To be familiar with pre-defined constant for getting maximum and minimum limit of a long data type.
   2. Why the test failed at first?
    - The expected result is not 0.
   3. Why you corrected the test that way?
    - It is the appropriate answer for getting the minimum and maximum limit of a long data type.
   4. Do you have further questions on this knowledge point?
    - None.
    
   * should_get_range_of_primitive_byte_type()
   1. What is the knowledge point of the test? Where is the official document to the knowledge point?
    - To be familiar with pre-defined constant for getting maximum and minimum limit of a byte data type.
   2. Why the test failed at first?
    - The expected result is not 0.
   3. Why you corrected the test that way?
    - It is the appropriate answer for getting the minimum and maximum limit of a byte data type.
   4. Do you have further questions on this knowledge point?
    - None.
    
    * should_get_range_of_primitive_byte_type()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To be familiar with pre-defined constant for getting maximum and minimum limit of a byte data type.
    2. Why the test failed at first?
     - The expected result is not 0.
    3. Why you corrected the test that way?
     - It is the appropriate answer for getting the minimum and maximum limit of a byte data type.
    4. Do you have further questions on this knowledge point?
     - None.
      
    * should_overflow_silently()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To be familiar with the value of integer when it overflows or exceed maximum.
    2. Why the test failed at first?
     - The expected result is not 0.
    3. Why you corrected the test that way?
     - It is the appropriate answer for when integer exceeds its maximum.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_underflow_silently()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To be familiar with the value of integer when it underflow or exceed minimum.
    2. Why the test failed at first?
     - The expected result is not 0.
    3. Why you corrected the test that way?
     - It is the appropriate answer for when integer exceeds its minimum.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_throw_exception_when_overflow()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To be familiar with the exception thrown when integer reached its maximum or overflow.
    2. Why the test failed at first?
     - The expected result did not throw an exception.
    3. Why you corrected the test that way?
     - It is the appropriate answer for when integer exceeds its maximum.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * just_prevent_lazy_implementation()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To check if method still works when the sum of two integer did not overflow/underflow.
    2. Why the test failed at first?
     - The expected result is not correct.
    3. Why you corrected the test that way?
     - It is the appropriate answer when adding two integer.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_take_care_of_number_type_when_doing_calculation()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - Application of MDAS.
    2. Why the test failed at first?
     - The expected result is not correct.
    3. Why you corrected the test that way?
     - It is the appropriate answer.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_truncate_number_when_casting()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - Type casting from integer to short.
    2. Why the test failed at first?
     - The expected result is not correct.
    3. Why you corrected the test that way?
     - It is the appropriate answer.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_increment()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - incrementing integer after.
    2. Why the test failed at first?
     - The expected result is not correct.
    3. Why you corrected the test that way?
     - It is the appropriate answer.
    4. Do you have further questions on this knowledge point?
     - None.
     
    * should_increment()
    1. What is the knowledge point of the test? Where is the official document to the knowledge point?
     - incrementing integer before.
    2. Why the test failed at first?
     - The expected result is not correct.
    3. Why you corrected the test that way?
     - It is the appropriate answer.
    4. Do you have further questions on this knowledge point?
     - None.