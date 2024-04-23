# User Management Interface Specification

## Overview
What this document does is outlining the specifications for the user management screen and hence making this code a guideline for the administration dashboard. It will allow the admins to to the CRUD operation using the panel.

## Components
### 1. User List
- **Description**: Table which displays the users
- **Columns**:
  - ID (non-editable)
  - User Name (non-editable)
  - Email (non-editable)
  - Enabled (boolean indicator-checkbox)

- **Behavior**:
  - Each row represents a different user.
  - Loader should be loading the table with the existing users each time the page is being loaded.
  - The 'Enabled' column displays 'true' if the user account is active, 'false' otherwise. 
  - If the number of the users exceed a determined limit, the scrollbar should appear.

### 2. New User Form
- **Fields**:
  - Username (text input)
  - Display Name (text input)
  - Phone (text input)
  - Email (email input)
  - User Roles (dropdown, multi-select)
  - Enabled (checkbox)
- **Behavior**:
  - Allows entry of details for the creation of a new user.
  - The 'Save User' button is enabled only when mandatory fields are filled.
  - On submission, validates input and adds a new user to the system.
  - Displays a success or error message upon submission.
  - Resets fields after successful user creation.

### 3. User Roles Dropdown
- **Options**:
  - Guest
  - Admin
  - Super-Admin
- **Behavior**:
  - Allows selection of multiple roles.
  - Default state is unselected.

### 4. Buttons
- **New User**: Opens the form for creating a new user.
- **Hide Disabled User**: Toggles the visibility of users who are not enabled.
- **Save User**: Saves the new user information into the system.

## Page Behavior
- **On Load**:
  - The user list is populated with active users.
  - The 'New User' form is empty and ready for input.
- **Data Validation**:
  - All input fields in the 'New User' form have client-side validation.
  - Email field should validate for proper email format.
- **Error Handling**:
  - Display error messages for invalid inputs.
  - Incomplete form submission triggers highlighting of the mandatory fields.
- **Success Handling**:
  - Display a success message when a user is successfully created.

## Technical Requirements
- The page must be responsive, working on both desktop and mobile devices.
- Implement front-end validation before submitting the form.
- Use AJAX for form submission to prevent page reload.
- Ensure compatibility with the latest versions of Chrome, Firefox, and Safari.

## Accessibility
- Ensure that the interface is accessible according to WCAG 2.1 standards.
- All form inputs should have corresponding labels.
- Interactive elements must be navigable using keyboard shortcuts.

