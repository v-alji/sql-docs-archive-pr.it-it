---
title: Recupero di una sola riga con IRow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fetching rows
- IRow interface
- single row fetching [SQL Server Native Client]
- OLE DB rowsets, fetching
- rowsets [OLE DB], fetching
- SQL Server Native Client OLE DB provider, fetching
ms.assetid: 07c803ca-299a-42c5-ba02-360b9631d15f
author: rothja
ms.author: jroth
ms.openlocfilehash: b5573fe1fef39f29329e373323f5f8aaf15f2c58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636040"
---
# <a name="fetching-a-single-row-with-irow"></a><span data-ttu-id="877ba-102">Recupero di una sola riga utilizzando IRow</span><span class="sxs-lookup"><span data-stu-id="877ba-102">Fetching a Single Row with IRow</span></span>
  <span data-ttu-id="877ba-103">L'implementazione dell'interfaccia **IRow** nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client è stata semplificata per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="877ba-103">The **IRow** interface implementation in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider is simplified to increase performance.</span></span> <span data-ttu-id="877ba-104">**IRow** consente l'accesso diretto alle colonne di un singolo oggetto riga.</span><span class="sxs-lookup"><span data-stu-id="877ba-104">**IRow** allows direct access to columns of a single row object.</span></span> <span data-ttu-id="877ba-105">Se si prevede che il risultato dell'esecuzione di un comando produca esattamente una riga, **IRow** recupererà le colonne della riga in questione.</span><span class="sxs-lookup"><span data-stu-id="877ba-105">If you know beforehand that the result of a command execution will produce exactly one row, **IRow** will retrieve the columns of that row.</span></span> <span data-ttu-id="877ba-106">Se il set di risultati include più righe, **IRow** esporrà solo la prima.</span><span class="sxs-lookup"><span data-stu-id="877ba-106">If the result set includes multiple rows, **IRow** will expose only the first row.</span></span>  
  
 <span data-ttu-id="877ba-107">L'implementazione dell'interfaccia **IRow** non consente la navigazione all'interno della riga.</span><span class="sxs-lookup"><span data-stu-id="877ba-107">The **IRow** implementation does not allow any navigation of the row.</span></span> <span data-ttu-id="877ba-108">A ogni colonna della riga è possibile accedere una sola volta, con un'eccezione. È infatti possibile accedere a una colonna una volta per trovarne le dimensioni e una seconda volta per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="877ba-108">Each column in the row is accessed only one time with one exception: A column can be accessed one time to find the column size and again to fetch the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="877ba-109">**IRow::Open** supporta solo i tipi DBGUID_STREAM e DBGUID_NULL di oggetti da aprire.</span><span class="sxs-lookup"><span data-stu-id="877ba-109">**IRow::Open** supports only DBGUID_STREAM and DBGUID_NULL type of objects to be opened.</span></span>  
  
 <span data-ttu-id="877ba-110">Per ottenere un oggetto riga utilizzando il metodo **ICommand::Execute**, è necessario passare IID_IRow.</span><span class="sxs-lookup"><span data-stu-id="877ba-110">To obtain a row object using **ICommand::Execute** method, IID_IRow must be passed.</span></span> <span data-ttu-id="877ba-111">L'interfaccia **IMultipleResults** deve essere utilizzata per gestire più set di risultati.</span><span class="sxs-lookup"><span data-stu-id="877ba-111">The **IMultipleResults** interface must be used to handle multiple result sets.</span></span> <span data-ttu-id="877ba-112">**IMultipleResults** supporta **IRow** e **IRowset**.</span><span class="sxs-lookup"><span data-stu-id="877ba-112">**IMultipleResults** supports **IRow** and **IRowset**.</span></span> <span data-ttu-id="877ba-113">**IRowset** viene utilizzata per le operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="877ba-113">**IRowset** is used for bulk operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="877ba-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="877ba-114">In This Section</span></span>  
  
-   [<span data-ttu-id="877ba-115">Utilizzo di IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="877ba-115">Using IRow::GetColumns</span></span>](using-irow-getcolumns.md)  
  
-   [<span data-ttu-id="877ba-116">Recupero di dati BLOB tramite IRow</span><span class="sxs-lookup"><span data-stu-id="877ba-116">Fetching BLOB Data Using IRow</span></span>](../../database-engine/dev-guide/fetching-blob-data-using-irow.md)  
  
## <a name="see-also"></a><span data-ttu-id="877ba-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="877ba-117">See Also</span></span>  
 [<span data-ttu-id="877ba-118">Set di righe</span><span class="sxs-lookup"><span data-stu-id="877ba-118">Rowsets</span></span>](rowsets.md)  
  
  
