---
title: Aggiunta di una colonna a una tabella di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- columns [OLE DB]
- AddColumn function
- SQL Server Native Client OLE DB provider, columns
- adding columns
ms.assetid: 22bae18a-bc9d-4617-8660-ed8b17a468d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 97aa2656ccde662a34e1dd80fd662b22f601d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723763"
---
# <a name="adding-a-column-to-a-sql-server-table"></a><span data-ttu-id="c915e-102">Aggiunta di una colonna a una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c915e-102">Adding a Column to a SQL Server Table</span></span>
  <span data-ttu-id="c915e-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone la funzione **ITableDefinition:: AddColumn** .</span><span class="sxs-lookup"><span data-stu-id="c915e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ITableDefinition::AddColumn** function.</span></span> <span data-ttu-id="c915e-104">Questo consente ai consumer di aggiungere una colonna a una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c915e-104">This allows consumers to add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="c915e-105">Quando si aggiunge una colonna a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumer del provider di OLE DB di Native Client è vincolato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c915e-105">When you add a column to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is constrained as follows:</span></span>  
  
-   <span data-ttu-id="c915e-106">Se DBPROP_COL_AUTOINCREMENT è VARIANT_TRUE, DBPROP_COL_NULLABLE deve essere VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="c915e-106">If DBPROP_COL_AUTOINCREMENT is VARIANT_TRUE, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="c915e-107">Se la colonna viene definita usando il tipo di dati  **timestamp** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_COL_NULLABLE deve essere VARIANT_FALSE.</span><span class="sxs-lookup"><span data-stu-id="c915e-107">If the column is defined by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **timestamp** data type, DBPROP_COL_NULLABLE must be VARIANT_FALSE.</span></span>  
  
-   <span data-ttu-id="c915e-108">Per qualsiasi altra definizione di colonna, DBPROP_COL_NULLABLE deve essere VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="c915e-108">For any other column definition, DBPROP_COL_NULLABLE must be VARIANT_TRUE.</span></span>  
  
 <span data-ttu-id="c915e-109">I consumer specificano il nome della tabella come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="c915e-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="c915e-110">Il membro *eKind* di*pTableID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="c915e-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="c915e-111">Il nome della nuova colonna viene specificato come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel membro *dbcid* del parametro DBCOLUMNDESC *pColumnDesc*.</span><span class="sxs-lookup"><span data-stu-id="c915e-111">The new column name is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *dbcid* member of the DBCOLUMNDESC parameter *pColumnDesc*.</span></span> <span data-ttu-id="c915e-112">Il membro *eKind* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="c915e-112">The *eKind* member must be DBKIND_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c915e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c915e-113">See Also</span></span>  
 <span data-ttu-id="c915e-114">[Tabelle e indici](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="c915e-114">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 [<span data-ttu-id="c915e-115">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c915e-115">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
  
