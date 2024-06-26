# User Management Interface Specification

## Erkin Yapıcı
## Overview
What this document does is outlining the specifications for the user management screen and hence making this code a guideline for the administration dashboard. It will allow the admins to to the CRUD operation using the panel.

## Components
### 1. User List
- **Description**: Table which displays the users
- **Columns**:
  - ID (non-editable)
  - User Name (non-editable)
  - Email (non-editable)
  - Enabled (boolean-checkbox)

- **Behavior**:
  - Each row represents a different user.
  - Loader should be loading the table with the existing users each time the page is being loaded.
  - If the user account is active, the 'enabled' column displays 'true'. If not, it simply displays false.
  - If the number of the users exceed a determined limit, the scrollbar should appear.

### 2. New User Form
- **Fields**:
  - Username (input as text)
  - Display Name (input as text)
  - Phone (input as text)
  - Email (input as email)
  - User Roles (dropdown / multi-select -opt-)
  - Enabled (checkbox)
- **Behavior**:
  - For the creation of a new user, allow the entry of details.
  - The button called 'Save User' will be enabled only when mandatory fields are filled.
  - On submission, validates input -such as email's @ and name fields- hence adds a new user to the system.
  - Upon submission, displays an error or success message.
  - Fields are being reset after succesful user creation. This allows to create new user easier.

### 3. User Roles Dropdown - Multi Select

- **Options**:
  - Guest
  - Admin
  - Super-Admin

- **Behavior**:
  - Multiple role selection is enabled.
  - Default state is not being displayed. It is unselected. No situation is shown until a state is being selected.

### 4. Buttons
- **New User**: To create a new user, opens the form.
- **Hide Disabled User**: Toggles the visibility of the users that are disabled.
- **Save User**: Saves the new user information within the form to the system/database.

## Page Behavior

- **On Load**:
  - The user list is populated by the active users
  - The 'New User' form is empty and ready for the input.

- **Data Validation**:
  - 'New User' form input fields have client-side validation.
  - Email field should validate for proper email format. -should include @ and not more special characters.

- **Error Handling**:
  - Displays error messages for the invalid inputs.
  - Incomplete form submission triggers highlighting and the error showing of the mandatory fields.

- **Success Handling**:
  - Display a success message when a user is successfully created. -a toast can also work.

## Technical Requirements
- The page must be responsive, working on both desktop, mobile and tablet devices.
- Implement front-end validation which are stated above, before submitting the form.
- AJAX can be used for form submission to prevent page reload.
- Your browser choice must be up-to-date with since all the components should be compatible with the newest versions.

## Accessibility
- Ensure that the interface is accessible in order with the WCAG standards.
- All form inputs should have corresponding labels.
- Using keyboard shortcuts, the interactive components must be controlled.

## Additional Notes on the Optimal Positioning
- The user list should be at the left side of the page.
- The new user adding form should be always visible (even though a new user is not being created at the time) and it should be at the right side of the page.

- **Top Bar of the Page**
- The New User should be at the most left of the top bar with a slight padding, marginLeft %5 should be enough.
- With a %3 margin left, Hide Disabled User checkbox can be positioned with a text right aligned to it.
- With a marginRight of %5 with a slight padding, at the right side of the top bar there should be Save User button and it should stay disabled until the all input fields are filled. When an error occurs and fields do not get validated, the Save User button should be enabled again.