# JeffersonCountyLibrary

## Setup
* Fork and Clone this repository
* Run `update-database`

## Exercise (12 points)

Check out a new branch and complete the following tasks **in order**:
* 2 points - There is a bug in our authentication!  Identity looks like it is set up, but we can't register users.  Find and fix this bug! (Hint: this should only take one line of code)
* 2 points - Right now, anyone can 'check out' a book.  Update the application so that only a logged in user can check out a book.
* 4 points - In this application, we have the ability to create new books.  Improve this functionality by:
  * Add a link from the nav-bar to add a book
  * Make sure only Librarians can add a book
* 2 points - Create a descriptive pull request and merge this branch into main
* 2 points - Take a screenshot of a database query result from pgAdmin that clearly shows which users in your database are librarians.  Update this README to include your screenshot below:
<br></br>
Roles Table - "AspNetRoles"
<br></br>
![image](https://github.com/jeremy-kimball/Launch_Mod5Week3Assessment/assets/130601077/34e5f368-c7d2-461a-97e6-dc0b107ec0d5)
<br></br>
Join Table - "AspNetUserRoles"
<br></br>
![image](https://github.com/jeremy-kimball/Launch_Mod5Week3Assessment/assets/130601077/0e8ba2b8-5428-425f-ae9e-b6d978ed0d33)
<br></br>
Users Table - "AspNetUsers"
<br></br>
![image](https://github.com/jeremy-kimball/Launch_Mod5Week3Assessment/assets/130601077/c0e40337-59e9-4fd6-9293-78d50e8724cf)

## Questions (6 points)

Answer the questions below in this README.  Answer these questions as if you are in an interview!

1. What are roles and claims as they relate to Authentication and Authorization?
<br></br>
Roles and claims both relate to authorization, for instance as we have done in this project. We have the ability to create books for our libraries but we don't want to let just anyone create books. So we create a role named "Librarian" and only allow access to this functionality to those users that have this role. This is done by using the `[Authorize(Roles = "Librarian")]` above the controller action we want to restrict. Claims work in a similar way but are less static. For example we may want to restrict users from purchasing certain things on our website based on their age. If the user enters that they are above 21 then that claim can be applied to their user account allowing them access to purchase whatever needs to be restricted in this way. Authentication does play a role as it relates to having a user account and users will need to have an account first for us to be able to make these authorization determinations.
<br></br>
3. How do cookies play a role in authentication and authorization?
<br></br>
Cookies can store a value that we are then able to link to the server and match the users credentials and roles, such as in our library app when a user tries to add a book, if they are logged in a cookie is created that we can then cross reference server-side to make sure that the person trying to do so has the appropriate role. Below is a picture of my cookies when I am logged in to a user. The second picture shows when I am logged out, as you can see we are missing a cookie here. The cookie that is missing is the one that is most likely responsible for this functionality.
![image](https://github.com/jeremy-kimball/Launch_Mod5Week3Assessment/assets/130601077/203a3e4d-b8c1-49d6-bf07-8250360e41a2)
![image](https://github.com/jeremy-kimball/Launch_Mod5Week3Assessment/assets/130601077/a363e87b-1ad2-4606-a2a1-3b82c89fb7e9)
<br></br>
5. If asked to implement Auth in a new .NET application, would you use the Identity framework?
<br></br>
Yes, you could create your own implementation to achieve this functionality, but the Identity framework is easy to implement in projects due to it being just nuget package, and it provides a ton of functionality if desired when scaffolding your project. There seems to be a lot to take into account when you want to have secure applications and Identity Framework is pre-built with functionalities like authentication, authorization, 2FA, and many other features to achieve this additional security.
<br></br>
## Rubric

This assessment has a total of 18 points.  Earning 12 or higher is a pass!
