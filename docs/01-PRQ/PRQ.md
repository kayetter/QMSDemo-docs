# Project Requirements

## Epic 1: Ad Hoc Subsample Management

**Epic Description:**
As a laboratory technician, I want the ability to add and manage subsamples ad hoc within the test form so that I can efficiently handle unexpected or additional testing requirements.

### User Stories:

1. **Configure Ad Hoc Subsamples**

   - **User Story**: As an admin, I want to configure the entity method to allow for ad hoc subsamples so that users can add subsamples to tests.
   - **Acceptance Criteria**:
     - An admin interface to enable/disable ad hoc subsamples for specific entity methods.
     - Documentation on how to configure this setting.

2. **Configure Worksheet Settings**
   - **User Story**: As an admin, I want to configure the entity worksheet settings to allow for canceling of ad hoc subsamples so that users can remove subsamples if necessary.
   - **Acceptance Criteria**:
     - An admin interface to enable/disable the cancellation of ad hoc subsamples for specific worksheet settings.
     - Documentation on how to configure this setting.

## Epic 2: Custom Control for Result Entry Worksheet

**Epic Description:**
As a laboratory technician, I want to have a custom control on the result entry worksheet to manage subsamples so that I can add or cancel subsamples easily.

### User Stories:

1. **Add Subsample Button**

   - **User Story**: As a user, I want a button on the custom control results entry worksheet to add a subsample so that I can easily include additional subsamples when required.
   - **Acceptance Criteria**:
     - A button labeled "Add Subsample" on the results entry worksheet.
     - Functionality to create a new subsample with a sequential number (e.g., maximum existing subsample number +1).
     - Confirmation message upon successful addition of a subsample.

2. **Cancel Subsample Button**
   - **User Story**: As a user, I want a button on the custom control results entry worksheet to cancel a subsample so that I can remove unnecessary subsamples.
   - **Acceptance Criteria**:
     - A button labeled "Cancel Subsample" on the results entry worksheet.
     - Functionality to remove a subsample.
     - Confirmation message upon successful cancellation of a subsample.

## Epic 3: Subsample Result Association

**Epic Description:**
As a laboratory technician, I want the corresponding results to be created and associated with the subsample when it is added so that I can ensure all subsamples have their own results.

### User Stories:

1. **Create Results for Subsample**
   - **User Story**: As a system, I want to create corresponding results associated with a new subsample so that each subsample has its own set of results.
   - **Acceptance Criteria**:
     - Automatic creation of results when a new subsample is added.
     - Association of the results with the specific subsample.

## Traceability

| Issue Key | Issue Type | Fix versions | Story Points | Priority | Assignee | Status | Summary                                   | Link   | Issue Key | Issue Type  | Fix versions | Story Points | Priority | Assignee          | Status | Summary                      |
| --------- | ---------- | ------------ | ------------ | -------- | -------- | ------ | ----------------------------------------- | ------ | --------- | ----------- | ------------ | ------------ | -------- | ----------------- | ------ | ---------------------------- |
| XU24\-23  | Epic       | \-           | \-           | Medium   | \-       | To Do  | Subsample Result Association              | Causes | XU24\-24  | Requirement | \-           | \-           | Low      | Kristin Schneider | To Do  | Create Results for Subsample |
| XU24\-20  | Epic       | \-           | \-           | Medium   | \-       | To Do  | Custom Control for Result Entry Worksheet | Causes | XU24\-21  | Requirement | \-           | \-           | Medium   | Kristin Schneider | To Do  | Add Subsample Button         |
| \-        | \-         | \-           | \-           | \-       | \-       | \-     | \-                                        | Causes | XU24\-22  | Requirement | \-           | \-           | Medium   | \-                | To Do  | Cancel Subsample Button      |
| XU24\-15  | Epic       | \-           | \-           | Medium   | \-       | To Do  | Ad Hoc Subsample Management               | Causes | XU24\-18  | Requirement | \-           | \-           | Medium   | \-                | To Do  | Configure Ad Hoc Subsamples  |
| \-        | \-         | \-           | \-           | \-       | \-       | \-     | \-                                        | Causes | XU24\-19  | Requirement | \-           | \-           | Medium   | \-                | To Do  | Configure Worksheet Settings |
