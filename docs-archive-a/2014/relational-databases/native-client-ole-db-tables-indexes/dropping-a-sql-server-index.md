---
title: Eliminazione di un indice di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: add3ba14-10b1-4723-b7c0-3e83689e9fdd
author: rothja
ms.author: jroth
ms.openlocfilehash: 1267cc92645ff8b28757ad2d266e58917fcb4b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629790"
---
# <a name="dropping-a-sql-server-index"></a><span data-ttu-id="915a7-102">Eliminazione di un indice di SQL Server</span><span class="sxs-lookup"><span data-stu-id="915a7-102">Dropping a SQL Server Index</span></span>
  <span data-ttu-id="915a7-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone la funzione **IIndexDefinition::D ropindex** .</span><span class="sxs-lookup"><span data-stu-id="915a7-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::DropIndex** function.</span></span> <span data-ttu-id="915a7-104">Questo consente ai consumer di rimuovere una colonna da una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="915a7-104">This allows consumers to remove an index from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="915a7-105">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone alcuni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vincoli PRIMARY KEY e Unique come indici.</span><span class="sxs-lookup"><span data-stu-id="915a7-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PRIMARY KEY and UNIQUE constraints as indexes.</span></span> <span data-ttu-id="915a7-106">Il proprietario della tabella, il proprietario del database e alcuni membri del ruolo amministrativo possono modificare una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], eliminando un vincolo.</span><span class="sxs-lookup"><span data-stu-id="915a7-106">The table owner, database owner, and some administrative role members can modify a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, dropping a constraint.</span></span> <span data-ttu-id="915a7-107">Per impostazione predefinita, solo il proprietario della tabella può eliminare un indice.</span><span class="sxs-lookup"><span data-stu-id="915a7-107">By default, only the table owner can drop an existing index.</span></span> <span data-ttu-id="915a7-108">L'esito positivo o negativo di **DropIndex** dipende quindi non solo dai diritti di accesso dell'utente dell'applicazione, ma anche dal tipo di indice indicato.</span><span class="sxs-lookup"><span data-stu-id="915a7-108">Therefore, **DropIndex** success or failure depends not only on the application user's access rights but also on the type of index indicated.</span></span>  
  
 <span data-ttu-id="915a7-109">I consumer specificano il nome della tabella come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pTableID*.</span><span class="sxs-lookup"><span data-stu-id="915a7-109">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="915a7-110">Il membro *eKind* di*pTableID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="915a7-110">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="915a7-111">I consumer specificano il nome dell'indice come stringa di caratteri Unicode nel membro *pwszName* dell'unione *uName* nel parametro *pIndexID*.</span><span class="sxs-lookup"><span data-stu-id="915a7-111">Consumers specify the index name as a Unicode character string in the *pwszName* member of the *uName* union in the *pIndexID* parameter.</span></span> <span data-ttu-id="915a7-112">Il membro *eKind* di *pIndexID* deve essere DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="915a7-112">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span> <span data-ttu-id="915a7-113">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non supporta la funzionalità OLE DB di eliminazione di tutti gli indici in una tabella quando *pIndexID* è null.</span><span class="sxs-lookup"><span data-stu-id="915a7-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support the OLE DB feature of dropping all indexes on a table when *pIndexID* is null.</span></span> <span data-ttu-id="915a7-114">Se *pIndexID* è Null, viene restituito E_INVALIDARG.</span><span class="sxs-lookup"><span data-stu-id="915a7-114">If *pIndexID* is null, E_INVALIDARG is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="915a7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="915a7-115">See Also</span></span>  
 <span data-ttu-id="915a7-116">[Tabelle e indici](tables-and-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="915a7-116">[Tables and Indexes](tables-and-indexes.md) </span></span>  
 <span data-ttu-id="915a7-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="915a7-117">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="915a7-118">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="915a7-118">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
