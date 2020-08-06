---
title: MSSQLSERVER_1793 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715348"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="681d2-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="681d2-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="681d2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="681d2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="681d2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="681d2-104">Product Name</span></span>|<span data-ttu-id="681d2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="681d2-105">SQL Server</span></span>|  
|<span data-ttu-id="681d2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="681d2-106">Event ID</span></span>|<span data-ttu-id="681d2-107">1793</span><span class="sxs-lookup"><span data-stu-id="681d2-107">1793</span></span>|  
|<span data-ttu-id="681d2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="681d2-108">Event Source</span></span>|<span data-ttu-id="681d2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="681d2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="681d2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="681d2-110">Component</span></span>|<span data-ttu-id="681d2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="681d2-111">SQLEngine</span></span>|  
|<span data-ttu-id="681d2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="681d2-112">Symbolic Name</span></span>|<span data-ttu-id="681d2-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="681d2-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="681d2-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="681d2-114">Message Text</span></span>|<span data-ttu-id="681d2-115">Impossibile eliminare l'indice '%.\*ls'. Schema di partizione non specificato per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="681d2-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="681d2-116">Explanation</span></span>  
 <span data-ttu-id="681d2-117">Questo messaggio viene visualizzato quando si tenta di eliminare un indice cluster in una tabella che contiene dati FILESTREAM e si specifica una clausola **MOVE TO** per i dati di base, ma non si specifica una clausola **FILESTREAM_ON** per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="681d2-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="681d2-118">User Action</span></span>  
 <span data-ttu-id="681d2-119">Quando si elimina un indice cluster in una tabella che contiene dati FILESTREAM, utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="681d2-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="681d2-120">Specificare sia una clausola **MOVE TO** per i dati di base sia una clausola **FILESTREAM_ON** per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="681d2-121">Non specificare una clausola **MOVE TO** per i dati di base né una clausola **FILESTREAM_ON** per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="681d2-122">L'esempio seguente ha esito negativo in quanto viene specificato uno schema di partizione per i dati di base, ma non per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="681d2-123">L'esempio seguente ha esito positivo in quanto viene specificata sia una clausola **MOVE TO** per i dati di base sia una clausola **FILESTREAM_ON** per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="681d2-124">L'esempio seguente ha anch'esso esito positivo in quanto non viene specificata né una clausola **MOVE TO** per i dati di base né una clausola **FILESTREAM_ON** per i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="681d2-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
