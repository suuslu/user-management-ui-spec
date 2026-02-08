# User Management UI Specification

## 1. Purpose
This screen allows administrators to view, create, edit, enable, and disable users in the system.
The document defines UI components, behaviors, validations, and states required to implement the screen.

## 2. Page Layout Overview
The page is divided into two main sections:
- Left panel: User list table
- Right panel: User detail / create form

A global action bar is displayed at the top.

## 3. Initial State
When the page loads:
- The user list is displayed on the left
- The first enabled user is selected by default
- The user detail form is populated with the selected user
- Disabled users are visible unless "Hide Disabled User" is checked

## 4. Top Action Bar
### Components
- **New User** button
- **Hide Disabled User** checkbox
- **Save User** button

### Behavior
- Clicking **New User** clears the form and switches to creation mode
- **Hide Disabled User** filters disabled users from the table
- **Save User** persists changes for create or edit actions

## 5. User List Table
### Columns
- ID
- Username
- Email
- Enabled (boolean)

### Behavior
- Clicking a row selects the user
- Selected row is visually highlighted
- Table supports column sorting and filtering
- Disabled users are visually muted

## 6. User Form Fields
### Fields
- Username (text, required, unique)
- Display Name (text, required)
- Phone (text, optional)
- Email (email format, required)
- User Roles (multi-select dropdown)
  - Guest
  - Admin
  - SuperAdmin
- Enabled (checkbox)

### Behavior
- Selecting a user populates all fields
- Role dropdown allows multiple selections
- Enabled checkbox controls user activation state

## 7. Validation Rules
- Username must be unique
- Email must be valid format
- Required fields must be filled
- At least one role must be selected

## 8. Save Behavior
- If validation fails, inline error messages are shown
- If save succeeds, user list refreshes
- New users appear immediately in the table
- Edit mode updates the existing row

## 9. Error and Edge States
- Empty state: show message if no users exist
- Loading state: show spinner while data loads
- Error state: show non-blocking error message on failure

## 10. Non-Functional Requirements
- Responsive layout
- Keyboard navigation support
- Consistent styling with admin UI theme
