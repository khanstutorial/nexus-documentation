## _/profile/:id_

## Description:
Shows the profile page of a user containing following information:
* First Name 
* Last Name 
* Email Address
* Job Title
* Department 
* Phone Number
* User Description 
* Last Logged In 

## Expected Response Structure
```sh
{
    user:{
        userID: 123,
        userName: 'Test User',
        firstName: 'Test',
        lastName: 'User',
        emailID: 'test@gmail.com',
        cellNumber: '+532 451 7583',
        lastLoggedIn: 'June 05, 2022. 12:24:55 GMT +5',
        department: 'IT',
        departmentID: 345,
        jobTitle: 'Software Engineer',
        userDescription: 'Lorem Ipsum is simply dummy text of the printing.'
    }
}
```

## Expected Response Variables

| Variable | Description |
| ------ | ------ |
| userID | User ID |
| userName | username of the user |
| firstName | first name of the user |
| lastName | last name of the user |
| emailID | email address of the user |
| cellNumber | contact number of the user |
| lastLoggedIn | last logged in details of the user |
| department | department of the user |
| departmentID | department id of the user |
| jobTitle | designation of the user |
| userDescription | user description |
