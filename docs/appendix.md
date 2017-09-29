# Appendix## Type Definitions| Data Type | Definition |
|---|---|| Long | CCMResult || Char | CCMBool || Char | CCMChar || Long | CCMConnectionID || Long | CCMSessionID || Long | CCMApplicationID || Long | CCMPid || unsigned int | CCMWindowID |

## Structures```typedef struct _CCM_Name_Value_Pair_{	IDL_STRING CCMChar* Name; //Name	IDL_STRING CCMChar* Value; // value} CCM_Name_Value_Pair, *PCCM_Name_Value_Pair;```
```
typedef struct _CCM_ICASession_{	CCMSessionID        SessionID;	CCMConnectionID     ConnectionID;	IDL_STRING CCMChar* FriendlyName;	IDL_STRING CCMChar* NonSeamlessAppTitle;	unsigned long       IsFullScreen;	unsigned long       Ssl;	IDL_STRING CCMChar* EncryptionLevel;	IDL_STRING CCMChar* EngineVersion;	IDL_STRING CCMChar* ServerName;	IDL_STRING CCMChar* UserName;	IDL_STRING CCMChar* DomainName;	unsigned long       RxFrameCount;	unsigned long       TxFrameCount;	unsigned long       RxByteCount;	unsigned long       TxByteCount;	unsigned long       RxFrameErrorCount;	unsigned long       TxFrameErrorCount;	unsigned long       SeamlessMode;	unsigned long       ZlMode;	unsigned long       CGP;	unsigned long       SpeedBrowseEnabled;	unsigned long       LastLatency;	unsigned long       AverageLatency;	unsigned long       RoundTripDeviation;	unsigned long       HRes;	unsigned long       VRes;	unsigned long       ColorDepth;	unsigned long       AudioEnabled;	unsigned long       PdaEnabled;	unsigned long       TwnEnabled;	unsigned long       PnpEnabled;} CCM_ICASession, *PCCM_ICASession;
```

```
typedef struct _CCM_ICAApplication_{	CCMApplicationID    ApplicationID;	CCMSessionID        SessionID;	IDL_STRING CCMChar* FriendlyName;	IDL_STRING CCMChar* Title;	IDL_STRING CCMChar* ClassName;	unsigned long       IconSize;#ifdef CCM_IDL	[size_is(IconSize)]#endif	unsigned char*      IconData;     unsigned long       hIcon;} CCM_ICAApplication, *PCCM_ICAApplication;```

## CCM SDK Error Codes and macros| Error No | Define Name                      | Ver |
|----------|----------------------------------|-----|
| 0        | CCM\_OK                           | 1   |
| 65535    | CCM\_ERROR\_BASE                   | 1   |
| 65534    | CCM\_ERROR\_UNEXPECTED             | 1   |
| 65533    | CCM\_ERROR\_UNINITIALIZED          | 1   |
| 65532    | CCM\_ERROR\_COMMUNICATION          | 1   |
| 65531    | CCM\_ERROR\_OUT\_OF\_MEMORY          | 1   |
| 65530    | CCM\_ERROR\_INVALID\_ARGUMENT       | 1   |
| 65529    | CCM\_ERROR\_AUTHORIZATION\_FAILED   | 1   |
| 65528    | CCM\_ERROR\_CONNECTION\_NOT\_FOUND   | 1   |
| 65527    | CCM\_ERROR\_SESSION\_NOT\_FOUND      | 1   |
| 65526    | CCM\_ERROR\_APPLICATION\_NOT\_FOUND  | 1   |
| 65525    | CCM\_ERROR\_ATTRIBUTE\_NOT\_FOUND    | 1   |
| 65524    | CCM\_ERROR\_SRP\_NOT\_ENABLED        | 1   |
| 65523    | CCM\_ERROR\_DEAD                   | 1   |
| 65522    | CCM\_ERROR\_INITIALIZATION\_FAILED  | 1   |
| 65521    | CCM\_ERROR\_ALREADY\_INITIALIZED    | 1   |
| 61440    | CCM\_ERROR\_BOTTOM                 | 1   |
| 61439    | CCMSE\_ERROR\_BASE                 | 1   |
| 61439    | CCMSE\_ERROR\_WINDOW\_POSITION      | 1   |
| 61438    | CCMSE\_ERROR\_RESIZING\_APPLICATION | 1   |
| 61437    | CCMSE\_ERROR\_DRIVER\_NOT\_LOADED    | 1   |
| 61436    | CCMSE\_ERROR\_PROPERTY             | 1   |
| 61435    | CCMSE\_ERROR\_SCALING              | 1   |
| 61434    | CCMSE\_ERROR\_KB                   | 1   |
| 61433    | CCMSE\_ERROR\_MOUSE                | 1   |
| 61432    | CCMSE\_ERROR\_HEADLESS\_DISABLED    | 1   |
| 61431    | CCMSE\_ERROR\_POST\_MESSAGE         | 1   |
| 16383    | CCM\_CLIENT\_ERROR\_BASE            | 1   |
| 16382    | CCM\_CLIENT\_RSTRAY\_ERROR          | 1   |
| 1        | CCM\_CLIENT\_ERROR\_BOTTOM          | 1   |