---
title: Rimozione di una colonna da una tabella di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- removing columns
- DropColumn function
- SQL Server Native Client OLE DB provider, columns
ms.assetid: 210811b7-cbd6-421e-bc6e-df9482236768
author: rothja
ms.author: jroth
ms.openlocfilehash: 8f40c466910aae7e0d349cd4a65ab265282bc8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629788"
---
# <a name="removing-a-column-from-a-sql-server-table"></a><span data-ttu-id="8d644-102">Rimozione di una colonna da una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d644-102">Removing a Column from a SQL Server Table</span></span>
  <span data-ttu-id="8d644-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone la funzione **ITableDefinition::D ropcolumn** .</span><span class="sxs-lookup"><span data-stu-id="8d644-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::DropColumn** function.</span></span> <span data-ttu-id="8d644-104">Questo consente ai consumer di rimuovere una colonna da una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d644-104">This allows consumers to remove a column from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="8d644-105">I consumer specificano il nome della tabella come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="8d644-105">Consumers specify the table name as a Unicode character string in the *pwszName*member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="8d644-106">Il membro *eKind* di *pTableID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="8d644-106">The *eKind*member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="8d644-107">Il consumer indica un nome di colonna nel membro *pwszName* dell'unione *uName* nel parametro *pColumnID*.</span><span class="sxs-lookup"><span data-stu-id="8d644-107">The consumer indicates a column name in the *pwszName*member of the *uName* union in the *pColumnID* parameter.</span></span> <span data-ttu-id="8d644-108">Il nome di colonna è una stringa di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="8d644-108">The column name is a Unicode character string.</span></span> <span data-ttu-id="8d644-109">Il membro *eKind* di *pColumnID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="8d644-109">The *eKind* member of *pColumnID* must be DBKIND_NAME.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d644-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d644-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="8d644-111">Codice</span><span class="sxs-lookup"><span data-stu-id="8d644-111">Code</span></span>  
  
```  
DBID TableID;  
DBID ColumnID;  
HRESULT hr;  
  
TableID.eKind = DBKIND_NAME;  
TableID.uName.pwszName = L"MyTableName";  
  
ColumnID.eKind = DBKIND_NAME;  
ColumnID.uName.pwszName = L"MyColumnName";  
  
hr = m_pITableDefinition->DropColumn(&TableID, &ColumnID);  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d644-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d644-112">See Also</span></span>  
 [<span data-ttu-id="8d644-113">Tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="8d644-113">Tables and Indexes</span></span>](tables-and-indexes.md)  
  
  
