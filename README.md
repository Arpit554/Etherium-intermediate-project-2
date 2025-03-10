# StudentGradeSystem Solidity Contract
This Solidity program is a smart contract called StudentGradeSystem. It manages student information, including name, marks, pass status, and course. The purpose of this program is to serve as a basic example of using Solidity for managing structured data on the Ethereum blockchain. This program can be a starting point for more complex student information management systems.

## Description

The StudentGradeSystem contract allows for the addition and retrieval of student information. Each student is identified by an Ethereum address, and their details are stored in a struct. The contract provides functions to add a student and to retrieve a student's name, marks, pass status, and course. This contract demonstrates the use of mappings and structs in Solidity, providing a foundation for more advanced decentralized applications.
## Getting Started

### Executing program

Installing
To run this program, you will need to use Remix, an online Solidity IDE. Follow these steps to get started:

Visit Remix: Go to https://remix.ethereum.org/.
Create a New File: Click on the "+" icon in the left-hand sidebar to create a new file.
Save the File: Save the file with a .sol extension (e.g., StudentGradeSystem.sol).
Copy and Paste Code: Copy and paste the following code into the new file:
```javascript
pragma solidity >=0.6.12 <0.9.0;

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

contract StudentGradeSystem {
    struct Student {
        string name;
        uint marks;
        bool passed;
        string course;
    }

    mapping(address => Student) public students;

    function addStudent(address _address, string memory _name, uint _marks, bool _passed, string memory _course) public {
        students[_address] = Student(_name, _marks, _passed, _course);
    }

    function getStudentName(address _address) public view returns (string memory) {
        return students[_address].name;
    }

    function getStudentMarks(address _address) public view returns (uint) {
        return students[_address].marks;
    }

    function isStudentPassed(address _address) public view returns (bool) {
        return students[_address].passed;
    }

    function getStudentCourse(address _address) public view returns (string memory) {
        return students[_address].course;
    }
}


```

Compile the Code:

Click on the "Solidity Compiler" tab in the left-hand sidebar.
Ensure the "Compiler" option is set to a compatible version, such as "0.8.7".
Click on the "Compile StudentGradeSystem.sol" button.
Deploy the Contract:

Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
Select the "StudentGradeSystem" contract from the dropdown menu.
Click on the "Deploy" button.
Interact with the Contract:

Add a Student: Call the addStudent function with the required parameters (address, name, marks, pass status, and course).
Get Student Information: Use the respective functions (getStudentName, getStudentMarks, isStudentPassed, getStudentCourse) to retrieve information about a student by their address.
Help
If you encounter common problems or issues, here are some tips:

Compiler Errors: Ensure that the Solidity version in the pragma directive matches the version set in the Remix compiler.
Function Calls: Double-check that you are passing the correct parameters to each function, especially when calling addStudent.
View Functions: Remember that view functions (getStudentName, getStudentMarks, isStudentPassed, getStudentCourse

# Author
Arpit https://github.com/Arpit554

# License
This project is licensed under the MIT License - see the LICENSE file for details
