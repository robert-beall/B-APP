# Software Requirements Specification
## Purpose
The purpose of this application is to provide a test-bed for better understanding the full lifecycle of application development from planning to deployment. 

## Description
The application should provide a web-based user interface that will allow a user to register and authenticate.

## Requirements
### Users
- The application should store user information.
- User Information:
  - username
  - password (hashed with salt)
  - email
  - Name
  - Birthdate
  - Profile Picture
  - Blurb
- New users should be able to register through the frontend web application.
- Existing users should be able to login using username and password credentials.
- Existing users should be able to update their profile information.
- Existing users should be able to reset their password using their email if they forgot their previous one.
- Alternatively, a user can update their password on the application, but will need to provide their old password in order to do so.

### Administrators
- Administrators should be able to perform the same tasks as regular users.
- Administrators should be able to access a list of all users.
- Administrators can update information for any user in the system.
- Administrators can update information about any user.
- Administrators can lock or unlock the account of any user. A locked user cannot login or perform any action on the site.
- Administrators can elevate a regular user to administrator permissions, or revoke admin permissions.

### Security
- Password Strength:
  - Between 12 and 18 characters
  - At least one special character (!@#$%^&*)
  - At least one uppercase character
  - At least one number
- Password should be stored as a salted hash.
- Communications should be sent encrypted using HTTPS. 

### Hosting
- The application should be hosted on a cloud platform and accessible from the outside internet.
- The application should be highly available and performant. 

### Pipeline
- A CI/CD pipeline should be developed which ensures quality control for the application before deploying to the cloud. 

### Testing
- The application should reach at least 80% code coverage.
- E2E tests should cover each major function, including error cases