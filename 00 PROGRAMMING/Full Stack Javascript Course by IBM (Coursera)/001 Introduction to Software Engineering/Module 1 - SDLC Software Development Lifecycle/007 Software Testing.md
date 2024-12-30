- Integrating quality checks throughout SDLC
- Purpose:
	- Ensure software meets requirements
	- Error-free software

> [!TIP] Test Cases
> - To test software, team writes __Test Cases__
> - Writen to verify functionality of software and ensure requirements have been satisfied
> 
> Test cases contains:
> - Steps
> - Data
> - Inputs
> - Expected Output
>   
> ![[Pasted image 20241210205855.png]]

---

> [!info] Three Types of  Testing
> - Functional Testing
> - Non-functional Testing
> - Regression Testing
> 
> ![[Pasted image 20241210205941.png]]

> [!example] Functional Testing
> Includes a method of __Black Box__ Testing:
> - without looking at Source Code / Internal Structure
> - Only concerned with Input and Output
> 
> ![[Pasted image 20241210221011.png]]
> 
>> [!info] Purpose of functional testing
>> - Usability
>> - Accessibility
>> 
>> Ensures that software handles exceptions/errors well(showing error messages).

> [!example] Non-functional testing attributes
>  Includes testing the application for attributes:
> - Performance
> - Security
> - Scalability
> - Availability
> 
> Checks if S.U.T.'s non-functional behavior is performing properly.
> 
>> [!info] Non-functional testing questions
>> - How does the application behave under stress?
>> - What happens when many users log in at the same time?
>> - Are instructions consistent with behavior?
>> - How does the application behave under different OSs?
>> - How does the application handle disaster recovery?
>> - How secure is the application?
>
>

> [!example] Regression testing (Maintenance Testing)
> - Confirms changes don't break the application
> - Occurs after fixes such as a change in requirements or when defects are fixed
> 
>> [!info] Choosing test cases for regression testing
>> Choose test cases that contain:
>> - Frequent defects
>> - Frequently used functionality
>> - Features with recent changes
>> - Complex cases
>> - Edge cases
>> - Randomly successful or failed cases


---

> [!abstract] Testing Levels
> 1. Unit
> 2. Integration
> 3. System
> 4. Acceptance
> 
>> [!example] Unit Testing
>> - Test a module of code
>> - Occurs during the __build phase__ of the SDLC
>> - Eliminate errors before integration with other modules
>
>> [!example] Integration testing
>> - Identify errors introduced when two or more modules are combined
>> - Type of __black-box test__
>> - Occurs after modules are combined into the larger application
>> 
>>> [!info] Purpose of Integration testing
>>> Exposes bugs that occurs when those small units of code interacts with another.
>>> ![[Pasted image 20241210222954.png]]
>
>
>> [!example] System Testing
>> - Occurs after Integration Testing
>> 	- Conducted on a complete integrated system
>> - Compliance with SRS
>> - Validate the system
>> - is both Functional and Non-Functional
>> - Staging Environment
>
>
>> [!example] Acceptance Testing
>> - Is done by the users
>> - Determines if a software satisfies the needs of customers, users and other stakeholders.



