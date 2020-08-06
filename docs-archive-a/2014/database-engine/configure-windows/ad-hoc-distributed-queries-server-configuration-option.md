---
title: Opzione di configurazione del server ad hoc distributed queries | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- OPENROWSET function, ad hoc distributed queries option
- Ad Hoc Distributed Queries option
- ad hoc distributed queries
- 7415 (Database Engine Error)
- OPENDATASOURCE function, ad hoc distributed queries option
- ad hoc access
ms.assetid: 5b982015-e196-44c3-83b8-275fb9d769b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d07b3c038597916cdaf026e24e90aab9d6b61616
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623489"
---
# <a name="ad-hoc-distributed-queries-server-configuration-option"></a><span data-ttu-id="2c42c-102">Opzione di configurazione del server ad hoc distributed queries</span><span class="sxs-lookup"><span data-stu-id="2c42c-102">ad hoc distributed queries Server Configuration Option</span></span>
  <span data-ttu-id="2c42c-103">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non prevede l'utilizzo query distribuite ad hoc contenenti le funzioni OPENROWSET e OPENDATASOURCE.</span><span class="sxs-lookup"><span data-stu-id="2c42c-103">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc distributed queries using OPENROWSET and OPENDATASOURCE.</span></span> <span data-ttu-id="2c42c-104">Quando questa opzione è impostata su 1, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile l'accesso ad hoc.</span><span class="sxs-lookup"><span data-stu-id="2c42c-104">When this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows ad hoc access.</span></span> <span data-ttu-id="2c42c-105">Quando questa opzione non è impostata o è impostata su 0, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile l'accesso ad hoc.</span><span class="sxs-lookup"><span data-stu-id="2c42c-105">When this option is not set or is set to 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc access.</span></span>  
  
 <span data-ttu-id="2c42c-106">Le query distribuite ad hoc utilizzano le funzioni OPENROWSET e OPENDATASOURCE per connettersi alle origini dei dati remote che utilizzano OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2c42c-106">Ad hoc distributed queries use the OPENROWSET and OPENDATASOURCE functions to connect to remote data sources that use OLE DB.</span></span> <span data-ttu-id="2c42c-107">È consigliabile utilizzare le funzioni OPENROWSET e OPENDATASOURCE solo per fare riferimento a origini dei dati OLE DB a cui si accede raramente.</span><span class="sxs-lookup"><span data-stu-id="2c42c-107">OPENROWSET and OPENDATASOURCE should be used only to reference OLE DB data sources that are accessed infrequently.</span></span> <span data-ttu-id="2c42c-108">Per le origini dei dati a cui è necessario accedere con maggiore frequenza, è possibile definire un server collegato.</span><span class="sxs-lookup"><span data-stu-id="2c42c-108">For any data sources that will be accessed more than several times, define a linked server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2c42c-109">Se si consente l'utilizzo dei nomi ad hoc, tutti gli account di accesso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticati potranno accedere al provider.</span><span class="sxs-lookup"><span data-stu-id="2c42c-109">Enabling the use of ad hoc names means that any authenticated login to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can access the provider.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2c42c-110">richiede che gli amministratori abilitino questa funzionalità per i provider a cui è possibile accedere in modo sicuro tramite qualsiasi account di accesso locale.</span><span class="sxs-lookup"><span data-stu-id="2c42c-110">administrators should enable this feature for providers that are safe to be accessed by any local login.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c42c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c42c-111">Remarks</span></span>  
 <span data-ttu-id="2c42c-112">Se si prova a eseguire una connessione ad hoc con l'opzione **Query distribuite ad hoc abilitate** non abilitata, viene restituito l'errore: Messaggio 7415, livello 16, stato 1, riga 1</span><span class="sxs-lookup"><span data-stu-id="2c42c-112">Attempting to make an ad hoc connection with **Ad Hoc Distributed Queries** not enabled results in error: Msg 7415, Level 16, State 1, Line 1</span></span>  
  
 <span data-ttu-id="2c42c-113">L'accesso ad hoc al provider OLE DB "Microsoft.ACE.OLEDB.12.0" è stato negato.</span><span class="sxs-lookup"><span data-stu-id="2c42c-113">Ad hoc access to OLE DB provider 'Microsoft.ACE.OLEDB.12.0' has been denied.</span></span> <span data-ttu-id="2c42c-114">Accedere al provider tramite un server collegato.</span><span class="sxs-lookup"><span data-stu-id="2c42c-114">You must access this provider through a linked server.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2c42c-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="2c42c-115">Examples</span></span>  
 <span data-ttu-id="2c42c-116">Nell'esempio seguente viene abilitata l'opzione ad hoc distributed queries e, successivamente, viene eseguita una query su un server denominato `Seattle1` utilizzando la funzione `OPENROWSET` .</span><span class="sxs-lookup"><span data-stu-id="2c42c-116">The following example enables ad hoc distributed queries and then queries a server named `Seattle1` using the `OPENROWSET` function.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
sp_configure 'Ad Hoc Distributed Queries', 1;  
RECONFIGURE;  
GO  
  
SELECT a.*  
FROM OPENROWSET('SQLNCLI', 'Server=Seattle1;Trusted_Connection=yes;',  
     'SELECT GroupName, Name, DepartmentID  
      FROM AdventureWorks2012.HumanResources.Department  
      ORDER BY GroupName, Name') AS a;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c42c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c42c-117">See Also</span></span>  
 <span data-ttu-id="2c42c-118">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2c42c-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="2c42c-119">[Server collegati &#40;Motore di database&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="2c42c-119">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="2c42c-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c42c-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="2c42c-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c42c-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span></span>  
 [<span data-ttu-id="2c42c-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2c42c-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)  
  
  
