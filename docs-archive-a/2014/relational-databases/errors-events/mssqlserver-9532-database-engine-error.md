---
title: MSSQLSERVER_9532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627741"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="69df9-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="69df9-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="69df9-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="69df9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69df9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="69df9-104">Product Name</span></span>|<span data-ttu-id="69df9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="69df9-105">SQL Server</span></span>|  
|<span data-ttu-id="69df9-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="69df9-106">Event ID</span></span>|<span data-ttu-id="69df9-107">9532</span><span class="sxs-lookup"><span data-stu-id="69df9-107">9532</span></span>|  
|<span data-ttu-id="69df9-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="69df9-108">Event Source</span></span>|<span data-ttu-id="69df9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="69df9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="69df9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="69df9-110">Component</span></span>|<span data-ttu-id="69df9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="69df9-111">SQLEngine</span></span>|  
|<span data-ttu-id="69df9-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="69df9-112">Symbolic Name</span></span>|<span data-ttu-id="69df9-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="69df9-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="69df9-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="69df9-114">Message Text</span></span>|<span data-ttu-id="69df9-115">Conversione non riuscita del tipo di dati '%ls' nel tipo di dati '%ls' per la colonna '%.\*ls' durante l'operazione query/DML che interessa il set di colonne '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="69df9-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69df9-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="69df9-116">Explanation</span></span>  
 <span data-ttu-id="69df9-117">Un set di colonne è una rappresentazione XML non tipizzata che combina alcune colonne di una tabella in un output strutturato.</span><span class="sxs-lookup"><span data-stu-id="69df9-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="69df9-118">Quando i valori di una colonna di tipo sparse vengono inseriti o aggiornati utilizzando il set di colonne XML, i valori inseriti nelle colonne di tipo sparse sottostanti vengono convertiti implicitamente dal tipo di dati `xml`.</span><span class="sxs-lookup"><span data-stu-id="69df9-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="69df9-119">Non è stato possibile convertire un valore specificato nel tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="69df9-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69df9-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="69df9-120">User Action</span></span>  
 <span data-ttu-id="69df9-121">Poiché il valore specificato non è stato convertito implicitamente, potrebbe costituire una voce non valida.</span><span class="sxs-lookup"><span data-stu-id="69df9-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="69df9-122">Correggere l'errore e riprovare.</span><span class="sxs-lookup"><span data-stu-id="69df9-122">Correct the error and retry.</span></span> <span data-ttu-id="69df9-123">Se il valore è corretto, modificare l'istruzione per utilizzare le colonne singole anziché il set di colonne.</span><span class="sxs-lookup"><span data-stu-id="69df9-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="69df9-124">In questo modo sarà possibile eseguire esplicitamente il cast del valore nel tipo di dati corretto.</span><span class="sxs-lookup"><span data-stu-id="69df9-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
