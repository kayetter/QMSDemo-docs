# Detailed Design Specifications

## Epic 1: Ad Hoc Subsample Management

### User Story 1: Configure Ad Hoc Subsamples

#### Class: `AddRepApi`

- **Summary**: Plugin development guide and best practices.
- **Methods**:
  - **Constructor**:
    - **Summary**: Initializes a new instance with the specified configuration.
    - **Parameters**:
      - `unsecureConfiguration`: The unsecure configuration string.
      - `secureConfiguration`: The secure configuration string.
  - **Method**: `ExecuteDataversePlugin`
    - **Summary**: Entry point for custom business logic execution.
    - **Parameters**:
      - `localPluginContext`: The local plugin context.
    - **Exceptions**: `InvalidPluginExecutionException` when the localPluginContext, context, service, or tracingService is null.
  - **Method**: `GetMethodResultCodes`
    - **Summary**: Retrieves method result codes for the specified method ID using the test service.
    - **Parameters**:
      - `methodId`: The ID of the method.
      - `testService`: The test service.
    - **Returns**: A collection of method result codes.
  - **Method**: `GetReplicatedMethodResultCodes`
    - **Summary**: Filters method result codes to include only those that are replicated.
    - **Parameters**:
      - `methodResultCodeEntities`: The collection of method result code entities.
    - **Returns**: A list of replicated method result code entities.

### User Story 2: Configure Worksheet Settings

#### Class: `SynSci.LabSci.AddTestComponents.CancelRepApi`

- **Summary**: Plugin development guide and best practices.
- **Methods**:
  - **Constructor**:
    - **Summary**: Initializes a new instance with the specified configuration.
    - **Parameters**:
      - `unsecureConfiguration`: The unsecure configuration string.
      - `secureConfiguration`: The secure configuration string.
  - **Method**: `ExecuteDataversePlugin`
    - **Summary**: Entry point for custom business logic execution.
    - **Parameters**:
      - `localPluginContext`: The local plugin context.
    - **Exceptions**: `InvalidPluginExecutionException` when the localPluginContext, context, service, or tracingService is null.
  - **Method**: `GetMethodResultCodes`
    - **Summary**: Retrieves method result codes for the specified method ID using the test service.
    - **Parameters**:
      - `methodId`: The ID of the method.
      - `testService`: The test service.
    - **Returns**: A collection of method result codes.
  - **Method**: `GetReplicatedMethodResultCodes`
    - **Summary**: Filters method result codes to include only those that are replicated.
    - **Parameters**:
      - `methodResultCodeEntities`: The collection of method result code entities.
    - **Returns**: A list of replicated method result code entities.

## Epic 2: Custom Control for Result Entry Worksheet

### User Story 1: Add Subsample Button

#### Class: `SynSci.LabSci.AddTestComponents.AddSubSampleApi`

- **Summary**: Plugin development guide and best practices.
- **Methods**:
  - **Constructor**:
    - **Summary**: Initializes a new instance with the specified configuration.
    - **Parameters**:
      - `unsecureConfiguration`: The unsecure configuration string.
      - `secureConfiguration`: The secure configuration string.
  - **Method**: `ExecuteDataversePlugin`
    - **Summary**: Entry point for custom business logic execution.
    - **Parameters**:
      - `localPluginContext`: The local plugin context.
    - **Exceptions**: `InvalidPluginExecutionException` when the localPluginContext, context, service, or tracingService is null.
  - **Method**: `AddSubsampleToTest`
    - **Summary**: Adds a subsample to a test method.
    - **Parameters**:
      - `service`: The organization service.
      - `tracingService`: The tracing service.
      - `testEntity`: The test entity.
      - `methodEntity`: The method entity.
    - **Returns**: The ID of the newly created subsample entity.
    - **Exceptions**: `System.Exception` when there is an error adding the subsample.

### User Story 2: Cancel Subsample Button

#### Class: `SynSci.LabSci.AddTestComponents.CancelSampleApi`

- **Summary**: Plugin development guide and best practices.
- **Methods**:
  - **Constructor**:
    - **Summary**: Initializes a new instance with the specified configuration.
    - **Parameters**:
      - `unsecureConfiguration`: The unsecure configuration string.
      - `secureConfiguration`: The secure configuration string.
  - **Method**: `ExecuteDataversePlugin`
    - **Summary**: Entry point for custom business logic execution.
    - **Parameters**:
      - `localPluginContext`: The local plugin context.
    - **Exceptions**: `InvalidPluginExecutionException` when the localPluginContext, context, service, or tracingService is null.
  - **Method**: `CancelSampleForSampleId`
    - **Summary**: Cancels a sample for the given sample ID.
    - **Parameters**:
      - `sampleId`: The ID of the sample to cancel.

## Epic 3: Subsample Result Association

### User Story 1: Create Results for Subsample

#### Class: `SynSci.LabSci.AddTestComponents.HelperServices.TestService`

- **Summary**: Provides services for interacting with test data in a Dataverse environment. Includes methods for retrieving failed specification results with actions and child tests for a given test.
- **Methods**:
  - **Constructor**:
    - **Summary**: Initializes a new instance of the class.
    - **Parameters**:
      - `service`: The IOrganizationService instance for Dataverse service interaction.
      - `tracingService`: The ITracingService instance for logging information during service operations.
  - **Method**: `GetMethodResultCodes`
    - **Summary**: Retrieves a collection of Entity objects representing the result codes associated with a specific method.
    - **Parameters**:
      - `methodId`: The GUID of the method for which result codes are being retrieved.
    - **Returns**: A DataCollection of Entity objects representing the result codes for the specified method.
  - **Method**: `GetMaxRep`
    - **Summary**: Retrieves the maximum replication number for a given test, sample, and method combination.
    - **Parameters**:
      - `testId`: The GUID of the test.
      - `sampleId`: The GUID of the sample.
      - `methodId`: The GUID of the method.
    - **Returns**: The maximum replication number as an integer, or 0 if no result is found.
  - **Method**: `GetLastSubsampleEntity`
    - **Summary**: Retrieves the last subsample entity associated with a given test and method.
    - **Parameters**:
      - `testId`: The GUID of the test associated with the subsample.
      - `methodId`: The GUID of the method associated with the subsample.
    - **Returns**: The last subsample entity as an Entity object.
  - **Method**: `GetLastSubsamplebyId`
    - **Summary**: Retrieves a subsample entity by its unique identifier.
    - **Parameters**:
      - `sampleId`: The unique identifier (GUID) of the subsample to retrieve.
    - **Returns**: The retrieved subsample entity as an Entity object.
  - **Method**: `GetLastSubSampleFromResult`
    - **Summary**: Determines the last subsample's unique identifier associated with a specific test and method.
    - **Parameters**:
      - `testId`: The unique identifier (GUID) of the test associated with the subsample.
      - `methodId`: The unique identifier (GUID) of the method associated with the subsample.
    - **Returns**: The unique identifier (GUID) of the last subsample associated with the specified test and method.
  - **Method**: `GetMaxSubsampleNumFromParent`
    - **Summary**: Retrieves the maximum subsample number for a given parent sample.
    - **Parameters**:
      - `parentSampleId`: The GUID of the parent sample for which the maximum subsample number is being retrieved.
    - **Returns**: The maximum subsample number as an integer, or 0 if no result is found.
  - **Method**: `GetResultsByResultCodesForTestMethodSample`
    - **Summary**: Retrieves the results by method result code for a specific test, method, sample, and list of result code IDs.
    - **Parameters**:
      - `testId`: The GUID of the test.
      - `methodId`: The GUID of the method.
      - `sampleId`: The GUID of the sample.
      - `repNumber`: The replication number.
      - `resultcodeIds`: The list of result code IDs.
    - **Returns**: A collection of Entity objects representing the results.
