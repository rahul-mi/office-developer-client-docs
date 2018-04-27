---
title: "FilterCriterion Property (RDS)"
 
 
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
  
localization_priority: Normal
ms.assetid: 51e6cb64-a404-114e-8e1a-0744cceeec3e

---

# FilterCriterion Property (RDS)

Indicates the evaluation operator to use in the filter value.
  
## Syntax

 *DataControl*  . **FilterCriterion** =  *String* 
  
## Parameters

-  *DataControl* 
    
- An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object. 
    
-  *String* 
    
- A **String** value that specifies the evaluation operator of the [FilterValue](filtervalue-property-rds.md) to the records. Can be any one of the following: <, <=, >, >=, =, or <>. 
    
## Remarks

The [SortColumn](sortcolumn-property-rds.md), [SortDirection](sortdirection-property-rds.md), [FilterValue](filtervalue-property-rds.md), **FilterCriterion**, and [FilterColumn](filtercolumn-property-rds.md) properties provide sorting and filtering functionality on the client-side cache. The sorting functionality orders records by values from one column. The filtering functionality displays a subset of records based on find criteria, while the full [Recordset](recordset-object-ado.md) is maintained in the cache. The [Reset](reset-method-rds.md) method will execute the criteria and replace the current **Recordset** with an updatable **Recordset**. 
  
The "!=" operator is not valid for **FilterCriterion**; instead, use "<>". 
  
If both the filter and sort properties are set and you call the **Reset** method, the rowset is first filtered and then it is sorted. For ascending sorts, the null values are at the top; for descending sorts, null values are at the bottom (ascending is default behavior). 
  
