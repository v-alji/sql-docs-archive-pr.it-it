---
title: Tabelle e indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629786"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="34f8d-102">Tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="34f8d-102">Tables and Indexes</span></span>
  <span data-ttu-id="34f8d-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone le interfacce **IIndexDefinition** e **ITableDefinition** , consentendo agli utenti di creare, modificare ed eliminare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelle e indici.</span><span class="sxs-lookup"><span data-stu-id="34f8d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="34f8d-104">La validità delle definizioni di tabelle e indici dipende dalla versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8d-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="34f8d-105">La possibilità di creare o eliminare tabelle e indici dipende dai diritti di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di cui dispone l'utente dell'applicazione consumer.</span><span class="sxs-lookup"><span data-stu-id="34f8d-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="34f8d-106">L'eliminazione di una tabella può essere vincolata ulteriormente dalla presenza di vincoli di integrità referenziale dichiarativa o da altri fattori.</span><span class="sxs-lookup"><span data-stu-id="34f8d-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="34f8d-107">La maggior parte delle applicazioni destinate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a usano SQL-DMO invece di queste [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfacce del provider OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="34f8d-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="34f8d-108">SQL-DMO è una raccolta di oggetti di automazione OLE che supportano tutte le funzioni amministrative di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8d-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="34f8d-109">Le applicazioni destinate a più provider OLE DB utilizzano queste interfacce OLE DB generiche supportate dai diversi provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="34f8d-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="34f8d-110">Nel set di proprietà DBPROPSET_SQLSERVERCOLUMN specifico del provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definisce la proprietà seguente.</span><span class="sxs-lookup"><span data-stu-id="34f8d-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="34f8d-111">ID proprietà</span><span class="sxs-lookup"><span data-stu-id="34f8d-111">Property ID</span></span>|<span data-ttu-id="34f8d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34f8d-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="34f8d-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="34f8d-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="34f8d-114">Digitare: VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="34f8d-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="34f8d-115">L/S: Scrittura</span><span class="sxs-lookup"><span data-stu-id="34f8d-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="34f8d-116">Valore predefinito: Null</span><span class="sxs-lookup"><span data-stu-id="34f8d-116">Default: Null</span></span><br /><br /> <span data-ttu-id="34f8d-117">Descrizione: questa proprietà viene utilizzata solo in **ITableDefinition**.</span><span class="sxs-lookup"><span data-stu-id="34f8d-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="34f8d-118">La stringa specificata in questa proprietà viene utilizzata per la creazione di un'istruzione [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="34f8d-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="34f8d-119">.</span><span class="sxs-lookup"><span data-stu-id="34f8d-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="34f8d-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="34f8d-120">In This Section</span></span>  
  
-   [<span data-ttu-id="34f8d-121">Creazione di tabelle di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="34f8d-122">Aggiunta di una colonna a una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="34f8d-123">Rimozione di una colonna da una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="34f8d-124">Eliminazione di una tabella di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="34f8d-125">Creazione di indici SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="34f8d-126">Eliminazione di un indice di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34f8d-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="34f8d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34f8d-127">See Also</span></span>  
 <span data-ttu-id="34f8d-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="34f8d-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="34f8d-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34f8d-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="34f8d-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34f8d-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="34f8d-131">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34f8d-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
