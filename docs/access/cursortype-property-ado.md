---
title: "CursorType Property (ADO)"
  
  
manager: soliver
ms.date: 3/9/2015
ms.audience: Developer
 
  
localization_priority: Normal
ms.assetid: f42ded8f-9f92-ef03-a198-ffb892324611
---

# CursorType Property (ADO)

Indicates the type of cursor used in a [Recordset](recordset-object-ado.md) object. 
  
## Settings and Return Values

Sets or returns a [CursorTypeEnum](cursortypeenum.md) value. The default value is **adOpenForwardOnly**. 
  
## Remarks

Use the **CursorType** property to specify the type of cursor that should be used when opening the **Recordset** object. 
  
Only a setting of **adOpenStatic** is supported if the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**. If an unsupported value is set, then no error will result; the closest supported **CursorType** will be used instead. 
  
If a provider does not support the requested cursor type, it may return another cursor type. The **CursorType** property will change to match the actual cursor type in use when the [Recordset](recordset-object-ado.md) object is open. To verify specific functionality of the returned cursor, use the [Supports](supports-method-ado.md) method. After you close the **Recordset**, the **CursorType** property reverts to its original setting. 
  
The following chart shows the provider functionality (identified by **Supports** method constants) required for each cursor type. 
  
|**For a Recordset of this CursorType**|**The Supports method must return True for all of these constants**|
|:-----|:-----|
|**adOpenForwardOnly** <br/> |none  <br/> |
|**adOpenKeyset** <br/> |**adBookmark**, **adHoldRecords**, **adMovePrevious**, **adResync** <br/> |
|**adOpenDynamic** <br/> |**adMovePrevious** <br/> |
|**adOpenStatic** <br/> |**adBookmark**, **adHoldRecords**, **adMovePrevious**, **adResync** <br/> |
   
> [!NOTE]
> Although **Supports** ( **adUpdateBatch** ) may be true for dynamic and forward-only cursors, for batch updates you should use either a keyset or static cursor. Set the [LockType](locktype-property-ado.md) property to **adLockBatchOptimistic** and the **CursorLocation** property to **adUseClient** to enable the Cursor Service for OLE DB, which is required for batch updates. 
  
The **CursorType** property is read/write when the **Recordset** is closed and read-only when it is open. 
  
 **Remote Data Service Usage** When used on a client-side Recordset object, the **CursorType** property can be set only to **adOpenStatic**. 
  
