---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713188"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="42c90-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="42c90-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="42c90-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="42c90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42c90-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="42c90-104">Product Name</span></span>|<span data-ttu-id="42c90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42c90-105">SQL Server</span></span>|  
|<span data-ttu-id="42c90-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="42c90-106">Event ID</span></span>|<span data-ttu-id="42c90-107">2570</span><span class="sxs-lookup"><span data-stu-id="42c90-107">2570</span></span>|  
|<span data-ttu-id="42c90-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="42c90-108">Event Source</span></span>|<span data-ttu-id="42c90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42c90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42c90-110">Componente</span><span class="sxs-lookup"><span data-stu-id="42c90-110">Component</span></span>|<span data-ttu-id="42c90-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42c90-111">SQLEngine</span></span>|  
|<span data-ttu-id="42c90-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="42c90-112">Symbolic Name</span></span>|<span data-ttu-id="42c90-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="42c90-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="42c90-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="42c90-114">Message Text</span></span>|<span data-ttu-id="42c90-115">Pagina P_ID, slot S_ID nell'oggetto con ID O_ID, ID di indice I_ID, ID di partizione PN_ID, ID di unità di allocazione A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="42c90-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="42c90-116">Il valore della colonna COLUMN_NAME non è compreso nell'intervallo consentito per il tipo di dati "DATATYPE".</span><span class="sxs-lookup"><span data-stu-id="42c90-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="42c90-117">Aggiornare la colonna a un valore valido.</span><span class="sxs-lookup"><span data-stu-id="42c90-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42c90-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="42c90-118">Explanation</span></span>  
 <span data-ttu-id="42c90-119">Il valore contenuto nella colonna specificata non è compreso nell'intervallo dei valori possibili per il tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="42c90-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42c90-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="42c90-120">User Action</span></span>  
 <span data-ttu-id="42c90-121">L'errore non è reversibile.</span><span class="sxs-lookup"><span data-stu-id="42c90-121">The error is not repairable.</span></span> <span data-ttu-id="42c90-122">Aggiornare la colonna a un valore compreso nell'intervallo consentito per il tipo di dati della colonna ed eseguire di nuovo il comando.</span><span class="sxs-lookup"><span data-stu-id="42c90-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="42c90-123">Per altre informazioni, vedere l'articolo [923247](https://support.microsoft.com/kb/923247) della Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="42c90-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c90-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42c90-124">See Also</span></span>  
 <span data-ttu-id="42c90-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="42c90-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="42c90-126">Tipi di dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="42c90-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
