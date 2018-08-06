# CCM SDK API Reference

## CCMInitialize

Initializes the CCM SDK. This is the pre-requisite to use any other CCM SDK API.

### Calling Convention

```
LONG CCMInitialize(STRING pConnectionName);
```

### Parameters

`STRING pConnectionName[in]`: Connection name to initialize the application.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Use this API to initialize CCM SDK. SDK should be initialized in the first place before calling any other API of CCM SDK.

See “Type Definition” section in Appendix to know about Data type definitions used in this document.

## CMUninitialize

Un-initialize CCM SDK.

### Calling Convention

```
LONG CCMUninitialize (Void);
```

### Parameters

None.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Use this API to uninitialized/unload CCM SDK. The API should be used only if SDK has been initialized already.

## CCMGetCCMAttributes

Returns name value pair of attributes of CCMSDK such as INFO, VERSION

### Calling Convention

```
LONG CCMGetCCMAttributes (
                 unsigned long* pCount,
                 PCCM_Name_Value_Pair *ppAttributes
);
```

### Parameters

`Long pCount [out]`: Out parameter having total number of attributes in ppAttributes.

`PCCM_Name_Value_Pair* ppAttributes [out]`: CCM SDK Attributes

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to get details about CCM SDK

### Example

```
  Name    Value
 ----    -----
 INFO    Citrix Common Connection Manager
 VERSION 1.0
```

After using `ppAttributes`, the process needs to call `CCMFreeNameValuePair` method on `ppAttributes` to free the memory.

## CCMGetMyConnectionID

The API to retrieve the connection ID.

### Calling Convention

```
LONG CCMEnumerateConnections (
          unsigned long* pCount,
          CCMConnectionID** ppConnections
)
```

### Parameters

`long* pCount [out]`: Total number of connections.
`CCMConnectionID** ppConnections [out]`: Connection ID.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to enumerate connections.

After using ppConnections, the process needs to call CCMFreeMemory method on ppConnections to free the memory.

## CCMSetConnectionAttributes

Sets connection attributes for a session that is running.

### Calling Convention

```
LONG CCMSetConnectionAttributes (
         CCMConnectionID hConnection,
         unsigned long count,
         const PCCM_Name_Value_Pair pAttributes
)
```

### Parameters

`CCMConnectionID hConnection [in]`: Connection ID.

`unsigned long count[in]`: Total number of attributes, which has been set.

`const PCCM_Name_Value_Pair pAttributes[in]`: Name value pair for attributed. For more information, see PCCM_Name_Value_Pair.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to set or update the connection attributes.

## CCMGetConnectionAttributes

Retrieves connection attributes in name value pair.

### Calling Convention

```
LONG CCMGetConnectionAttributes (
     CCMConnectionID hConnection,
               unsigned long* pCount,
               PCCM_Name_Value_Pair* ppAttributes
)
```

### Parameters

`CCMConnectionID hConnection [in]`: Connection ID.
`unsigned long* pCount [out]`: Total number of attributes in ppAttributes.
`PCCM_Name_Value_Pair* ppAttributes[out]`: Connection attributes.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to get the connection attributes such as, Connection Name.

After using ppAttributes, the process needs to call CCMFreeNameValuePair method on ppAttributes to free the memory.

## CCMDeleteConnectionAttribute

Deletes the connection attribute.

### Calling Convention

```
LONG CCMDeleteConnectionAttribute (
         CCMConnectionID hConnection,
         const PCCM_Name_Value_Pair pAttribute
)
```

### Parameters

`CCMConnectionID hConnection [in]`: Connection ID.

`const PCCM_Name_Value_Pair pAttribute[in]`: Name value pair, the attributes need to be deleted.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to delete the connection attributes.

## CCMLaunchApplication

Launches the application.

### Calling Convention

```
LONG CCMLaunchApplication (
            unsigned long count,
            const PCCM_Name_Value_Pair pParams,
            CCMSessionID* hSession
)
```

### Parameters

`unsigned long count [in]`: Total number of Name value pair in pParams.
`const PCCM_Name_Value_Pair pParams[in]`: Name value pair which has the session information.
`CCMSessionID* hSession[out]`: Session ID.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to launch application.

### Example

```
Name Value of Pair
--- --------------
Name - ICA_FILE_PATH
Value - <Path_To_Ica_File>
```

## CCMLaunchPublishedApplication

Launches published application for a user.

### Calling Convention

```
LONG CCMLaunchPublishedApplication (
           CCMSessionID hSession,
           const CCMChar* pAppName,
           const CCMChar* pArguments
)
```

### Parameters

`CCMSessionID hSession [in]`: Session ID.

`const CCMChar* pAppName[in]`: Name of the application.

`const CCMChar* pArguments[in]`: Arguments with which application has to be launched.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to launch published application for a user.

## CCMEnumerateApplications

Enumerates the launched application and gets application information.

### Calling Convention

```
LONG CCMEnumerateApplications (
 unsigned long* pCount,
      PCCM_ICAApplication* ppICAApplications
)
```

### Parameters

`unsigned long* pCount[out]`: Total number of session launched.

`PCCM_ICAApplication* ppICAApplications[out]`: launched application information.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

The purpose of this API is to enumerates all the launched application for a session.

After using ppICAApplications, the process needs to call CCMFreeICAApplication method on ppICAApplications to free the memory.

## CCMGetApplicationInfo

Provides information for a launched application.

### Calling Convention

```
LONG CCMGetApplicationInfo (
              CCMApplicationID hApplication,
              PCCM_ICAApplication* ppICAApplication
)
```

### Parameters

`CCMApplicationID hApplication[in]`: Application Id, for which the information is needed.

`PCCM_ICAApplication* ppICAApplication[out]`: Retrieves application information.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Application Id can be found by calling the CCMEnumerateApplications and getting the corresponding Application Id of Application.

Provides information for a launched application.

After using ppICAApplications, the process needs to call CCMFreeICAApplication method on ppICAApplications to free the memory.

## CCMTerminateApplication

Terminates an application.

### Calling Convention

```
LONG CCMTerminateApplication (
           CCMApplicationID hApplication
)
```

### Parameters

`CCMApplicationID hApplication [in]`: Application ID, which needs to be terminated.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Application Id can be found by calling the CCMEnumerateApplications and getting the corresponding Application Id of Application.

Terminates an application with the matching application id in the parameter.

## CCMSetSessionAttributes

Sets session attributes.

### Calling Convention

```
LONG CCMSetSessionAttributes (
         CCMSessionID hSession,
         unsigned long count,
         const PCCM_Name_Value_Pair pAttributes
)
```

### Parameters

`CCMSessionID hSession[in]`: Session Id for which attributes needs to be set.

`unsigned long count[in]`: Total number of attributes, which needs to be set.

`const PCCM_Name_Value_Pair pAttributes[in]`: Attributes which should be set.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Sets session attributes.

## CCMGetSessionAttributes

Retrieves session attributes of the running session.

### Calling Convention

```
LONG CCMGetSessionAttributes (
             CCMSessionID hSession,
             unsigned long* pCount,
             PCCM_Name_Value_Pair* ppAttributes
)
```

### Parameters

`CCMSessionID hSession [in]`: Session ID.

`unsigned long* pCount[out]`: Total number of session attributes in ppAttributes parameter.

`PCCM_Name_Value_Pair* ppAttributes`: Attributes with name-value pair.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Session Id can be found by calling the CCMEnumerateSessions and getting the corresponding Session Id of Application.

Retrieves session attributes.

After using ppAttributes, the process needs to call CCMFreeNameValuePair method on ppAttributes to free the memory.

## CCMDeleteSessionAttribute

Deletes session attribute of the running session.

### Calling Convention

```
LONG CCMDeleteSessionAttribute (
       CCMSessionID hSession,
             const PCCM_Name_Value_Pair pAttribute

)
```

### Parameters

CCMSessionID hSession [in]: Session ID.

`const PCCM_Name_Value_Pair pAttribute[in]`: session attribute that needs to be deleted.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Deletes session attribute.

## CCMEnumerateSessions

Enumerates sessions. Retrieves all the session related information of all the running sessions.

### Calling Convention

```
LONG CCMEnumerateSessions (
 unsigned long* pCount,
 PCCM_ICASession* ppICASessions
)
```

### Parameters

`unsigned long* pCount[out]`: Total number of sessions.

`PCCM_ICASession* ppICASessions[out]`: Session information.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Enumerates sessions.

After using ppICASessions, the process needs to call CCMFreeICASession method on ppICASessions to free the memory.

## CCMGetSessionInfo

Retrieves session information.

### Calling Convention

```
LONG CCMGetSessionInfo (
  CCMSessionID hSession,
 PCCM_ICASession* ppICASession
)
```

### Parameters

`CCMSessionID hSession [in]`: Session ID.

`PCCM_ICASession* ppICASession [out]`: Session information.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Retrieves session information of a session using session Id.
After using ppICASession, the process needs to call CCMFreeICASession method on ppICASession to free the memory.

## CCMDisconnectSession

Disconnects a running session.

### Calling Convention

```
LONG CCMDisconnectSession (
    CCMSessionID hSession
)
```

### Parameters

CCMSessionID hSession[in]: Session id that needs to be disconnected.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Disconnects a running session for a session using the session id.

## CCMLogoffSession

Log-off a running session.

### Calling Convention

```
LONG CCMLogoffSession (
 CCMSessionID hSession
)
```

### Parameters

`CCMSessionID hSession [in]`: Session id that needs to be logged-off.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Log-off a running session.

## CCMDisconnectAllSessions

Disconnects all the running session.

### Calling Convention

```
LONG CCMDisconnectAllSessions ()
```

### Parameters

None.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Disconnects all the running session.

## CCMLogoffAllSessions

Log-off all the running sessions.

### Calling Convention

```
LONG CCMLogoffAllSessions ()
```

### Parameters

None.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Log-off all the running sessions.

## CCMFullScreenSession

Sets session screen to full screen mode.

### Calling Convention

```
LONG CCMFullScreenSession (
 CCMSessionID hSession
)
```

### Parameters

`CCMSessionID hSession [in]`: Session ID.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Sets session screen to full screen mode. Takes the application to non-seamless mode

## CCMForeGroundApplication

Makes application to foreground.

### Calling Convention

```
LONG CCMForeGroundApplication (
  CCMApplicationID hApplication
)
```

### Parameters

`CCMApplicationID hApplication [in]`: Application ID.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Makes application to foreground. It sets the focus for a launched session

## CCMGetErrorMessageStringForCode

Returns message string for a given CCM error code.

### Calling Convention

```
LONG CCMGetErrorMessageStringForCode (
CCMSessionID hSession,
 unsigned long errorCode,
 CCMChar** ppErrorString
)
```

### Parameters

`CCMSessionID hSession[in]`: Session ID.

`unsigned long errorCode[in]`: Error code for which error string needed.

`CCMChar** ppErrorString[out]`: Error string.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Returns message string for a given CCM error code.

After using ppErrorString, the process needs to call CCMFreeMemory method on ppErrorString to free the memory.

## CCMGetActiveSessionCount

Retrieves all the active session count.

### Calling Convention

```
LONG CCMGetActiveSessionCount (
 unsigned long *pCount
)
```

### Parameters

`unsigned long *pCount[out]`: Total number of active session count.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Retrieves all the active session count.

## CCMFreeNameValuePair

Frees name value pair memory that retrieved via out parameter for an API.

### Calling Convention

```
LONG CCMFreeNameValuePair (
         unsigned long count,
         PCCM_Name_Value_Pair pNVP
)
```

### Parameters

`unsigned long count[in]`: Total number of name value pair in pNVP parameter.

`PCCM_Name_Value_Pair pNVP[in]`: Pointer to PCCM_Name_Value_Pair structure.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Frees name value pair memory that retrieved via out parameter for an API. The methods need to be called after all the APIs where PCCM_Name_Value_Pair object used to retrieve the information.

## CCMFreeICASession

Frees memory consumed by PCCM_ICASession object.

### Calling Convention

```
LONG CCMFreeICASession (
unsigned long count,
PCCM_ICASession pSession
)
```

### Parameters

`unsigned long count[in]`: Size of pSession array object.

`PCCM_ICASession pSession [in]`: Pointer to PCCM_ICASession structure.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Frees memory consumed by PCCM_ICASession object. The methods needs to be called after all the APIs where PCCM_ICASession  object used to retrieve information

## CCMFreeICAApplication

Frees memory consumed by PCCM_ICAApplication object.

### Calling Convention

```
LONG CCMFreeICAApplication (
 unsigned long count,
 PCCM_ICAApplication pApplication
)
```

### Parameters

`unsigned long count[in]`: Size of pApplication array object.

`PCCM_ICAApplication pApplication [in]`: Pointer to PCCM_ICAApplication structure.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Frees memory consumed by PCCM_ICAApplication object. The methods need to be called after all the APIs where PCCM_ICASession object used to retrieve information.

## CCMFreeMemory

Frees memory using CoTaskMemFree method.

### Calling Convention

```
void CCMFreeMemory (void *pVoid)
```

### Parameters

`void *pVoid[in]`: Pointer to memory location which needs to freed.

### Returns

Void.

### Call Time

Run-time

### Remarks

Frees memory using CoTaskMemFree method.

## CCMDisconnectUserSessions

Disconnects user session for a given user.

### Calling Convention

```
LONG CCMDisconnectUserSessions (
const CCMChar* pUserName,
 const CCMChar* pDomainName
)
```

### Parameters

`const CCMChar* pUserName[in]`: Pointer to CCMChar having User name.

`const CCMChar* pDomainName[in]`: Pointer to CCMChar having domain name.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Disconnects user session for a given user. The Arguments needs to be passed to this API are user name and domain name.

## CCMGetActiveSessionCountForUser

Gets active session count for a user.

### Calling Convention

```
LONG CCMGetActiveSessionCountForUser (
const CCMChar *pUserName,
const CCMChar *pDomainName,
unsigned long *pCount
)
```

### Parameters

`const CCMChar* pUserName[in]`: Pointer to CCMChar having User name.

`const CCMChar* pDomainName[in]`: Pointer to CCMChar having domain name.

`unsigned long *pCount[out]`: Number of total active session for a user.

### Returns

CCMResult: Zero if succeeded otherwise error code. For more information about the error code, please see the appendix.

### Call Time

Run-time

### Remarks

Gets active session count for a user. The Arguments needs to be passed to this API are user name and domain name.