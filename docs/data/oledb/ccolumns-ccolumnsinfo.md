---
title: "CColumns、CColumnsInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szDomainSchema"
  - "CColumns"
  - "m_guidType"
  - "COLLATION_CATALOG"
  - "m_szTableSchema"
  - "COLUMN_DEFAULT"
  - "IS_NULLABLE"
  - "m_nColumnPropID"
  - "ORDINAL_POSITION"
  - "m_szColumnDefault"
  - "m_szCollationCatalog"
  - "m_nDateTimePrecision"
  - "m_szDomainCatalog"
  - "m_nOrdinalPosition"
  - "m_szDomainName"
  - "COLUMN_GUID"
  - "CHARACTER_SET_NAME"
  - "m_nColumnFlags"
  - "DOMAIN_NAME"
  - "m_szCollationName"
  - "m_szColumnName"
  - "CHARACTER_SET_SCHEMA"
  - "COLUMN_FLAGS"
  - "m_szCharSetName"
  - "NUMERIC_PRECISION"
  - "DOMAIN_SCHEMA"
  - "DOMAIN_CATALOG"
  - "m_nDataType"
  - "m_szTableCatalog"
  - "CHARACTER_SET_CATALOG"
  - "m_szCharSetSchema"
  - "CHARACTER_OCTET_LENGTH"
  - "NUMERIC_SCALE"
  - "m_nNumericScale"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "m_szCharSetCatalog"
  - "m_nMaxLength"
  - "CHARACTER_MAXIMUM_LENGTH"
  - "COLLATION_NAME"
  - "COLLATION_SCHEMA"
  - "m_bColumnHasDefault"
  - "m_szTableName"
  - "m_nNumericPrecision"
  - "DATA_TYPE"
  - "m_nOctetLength"
  - "CColumnsInfo"
  - "m_szCollationSchema"
  - "m_bIsNullable"
  - "COLUMN_HASDEFAULT"
  - "DATETIME_PRECISION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumns TYPEDEF クラス"
  - "CColumnsInfo パラメーター クラス"
  - "CHARACTER_MAXIMUM_LENGTH"
  - "CHARACTER_OCTET_LENGTH"
  - "CHARACTER_SET_CATALOG"
  - "CHARACTER_SET_NAME"
  - "CHARACTER_SET_SCHEMA"
  - "COLLATION_CATALOG"
  - "COLLATION_NAME"
  - "COLLATION_SCHEMA"
  - "COLUMN_DEFAULT"
  - "COLUMN_FLAGS"
  - "COLUMN_GUID"
  - "COLUMN_HASDEFAULT"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "DATA_TYPE"
  - "DATETIME_PRECISION"
  - "DESCRIPTION クラスのデータ メンバー"
  - "DOMAIN_CATALOG"
  - "DOMAIN_NAME"
  - "DOMAIN_SCHEMA"
  - "IS_NULLABLE"
  - "m_bColumnHasDefault"
  - "m_bIsNullable"
  - "m_guidColumn"
  - "m_guidType"
  - "m_nColumnFlags"
  - "m_nColumnPropID"
  - "m_nDataType"
  - "m_nDateTimePrecision"
  - "m_nMaxLength"
  - "m_nNumericPrecision"
  - "m_nNumericScale"
  - "m_nOctetLength"
  - "m_nOrdinalPosition"
  - "m_szCharSetCatalog"
  - "m_szCharSetName"
  - "m_szCharSetSchema"
  - "m_szCollationCatalog"
  - "m_szCollationName"
  - "m_szCollationSchema"
  - "m_szColumnDefault"
  - "m_szColumnName"
  - "m_szDescription"
  - "m_szDomainCatalog"
  - "m_szDomainName"
  - "m_szDomainSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "NUMERIC_PRECISION"
  - "NUMERIC_SCALE"
  - "ORDINAL_POSITION"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 7a4ca8e8-e041-4def-8c1a-00c211f7da0b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CColumns、CColumnsInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パラメーター **CColumnsInfo**クラスを実装するに **CColumns** typedef クラスを呼び出します。  
  
## 解説  
 typedef クラスの使用の詳細については、" [スキーマ行セット クラスと Typedef クラス](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) を参照してください。  
  
 カタログで定義されています。このクラスは、特定のユーザーがアクセスできるテーブルの列を識別します。  
  
 次の表は、クラスのデータ メンバーとそれらに該当する OLE DB の列の一覧です。  スキーマと列の詳細については、" *OLE DB Programmer's Reference* の [列の行セット](https://msdn.microsoft.com/en-us/library/ms723052.aspx) を参照してください。  
  
|データ メンバー|OLE DB の列|  
|--------------|---------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_nOrdinalPosition|ORDINAL\_POSITION|  
|m\_bColumnHasDefault|COLUMN\_HASDEFAULT|  
|m\_szColumnDefault|COLUMN\_DEFAULT|  
|m\_nColumnFlags|COLUMN\_FLAGS|  
|m\_bIsNullable|IS\_NULLABLE|  
|m\_nDataType|DATA\_TYPE|  
|m\_guidType|TYPE\_GUID|  
|m\_nMaxLength|CHARACTER\_MAXIMUM\_LENGTH|  
|m\_nOctetLength|CHARACTER\_OCTET\_LENGTH|  
|m\_nNumericPrecision|NUMERIC\_PRECISION|  
|m\_nNumericScale|NUMERIC\_SCALE|  
|m\_nDateTimePrecision|DATETIME\_PRECISION|  
|m\_szCharSetCatalog|CHARACTER\_SET\_CATALOG|  
|m\_szCharSetSchema|CHARACTER\_SET\_SCHEMA|  
|m\_szCharSetName|CHARACTER\_SET\_NAME|  
|m\_szCollationCatalog|COLLATION\_CATALOG|  
|m\_szCollationSchema|COLLATION\_SCHEMA|  
|m\_szCollationName|COLLATION\_NAME|  
|m\_szDomainCatalog|DOMAIN\_CATALOG|  
|m\_szDomainSchema|DOMAIN\_SCHEMA|  
|m\_szDomainName|DOMAIN\_NAME|  
|m\_szDescription|DESCRIPTION|  
  
## 要件  
 **ヘッダー:** atldbsch.h  
  
## 参照  
 [CatDB サンプル : データ ソース スキーマ ブラウザー](../../top/visual-cpp-samples.md)   
 [CRestrictions クラス](../Topic/CRestrictions%20Class.md)