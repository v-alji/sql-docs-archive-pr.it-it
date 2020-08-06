---
title: Esportare e importare oggetti di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [Analysis Services]
- exporting mining models
- exporting mining structures
- mining structures [Analysis Services], creating
- mining structures [DMX], exporting
- mining models [Analysis Services], migration
ms.assetid: 10a83b13-2640-4ff5-80c8-a35e1d692908
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01e8651dd7e9d59012b0ba065bccb9ea62a1ee54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635265"
---
# <a name="export-and-import-data-mining-objects"></a><span data-ttu-id="ea898-102">Esportare e importare gli oggetti di data mining</span><span class="sxs-lookup"><span data-stu-id="ea898-102">Export and Import Data Mining Objects</span></span>
  <span data-ttu-id="ea898-103">Oltre alle funzionalità fornite in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per il backup, il ripristino e la migrazione di soluzioni, il componente Data mining di SQL Server offre la possibilità di trasferire rapidamente strutture e modelli di data mining tra server diversi tramite DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="ea898-103">In addition to the functionality provided in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up, restoring, and migrating solutions, SQL Server Data Mining provides the ability to quickly transfer data mining structures and models between different servers by using Data Mining Extensions (DMX).</span></span>  
  
 <span data-ttu-id="ea898-104">Se la soluzione di data mining utilizza dati relazionali anziché un database multidimensionale, il trasferimento dei modelli mediante `EXPORT` e `IMPORT` risulta molto più veloce e semplice rispetto all'utilizzo della funzione di ripristino del database o alla distribuzione di un'intera soluzione.</span><span class="sxs-lookup"><span data-stu-id="ea898-104">If your data mining solution uses relational data instead of a multidimensional database, transferring models by using `EXPORT` and `IMPORT` is much faster and easier than either using database restore or deploying an entire solution.</span></span>  
  
 <span data-ttu-id="ea898-105">In questa sezione viene fornita una panoramica di come trasferire strutture e modelli di data mining mediante istruzioni DMX.</span><span class="sxs-lookup"><span data-stu-id="ea898-105">This section provides an overview of how to transfer data mining structures and models by using DMX statements.</span></span> <span data-ttu-id="ea898-106">Per informazioni dettagliate sulla sintassi con relativi esempi, vedere [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) e [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).</span><span class="sxs-lookup"><span data-stu-id="ea898-106">For details of the syntax, together with examples, see [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) and [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea898-107">Per esportare o importare oggetti da un database di Microsoft SQL Server Analysis Services, è necessario essere un amministratore del server o del database.</span><span class="sxs-lookup"><span data-stu-id="ea898-107">You must be a database or server administrator to export or import objects from a Microsoft SQL Server Analysis Services database.</span></span>  
  
## <a name="exporting-data-mining-structures"></a><span data-ttu-id="ea898-108">Esportazione di strutture di data mining</span><span class="sxs-lookup"><span data-stu-id="ea898-108">Exporting Data Mining Structures</span></span>  
 <span data-ttu-id="ea898-109">Quando si esporta una struttura di data mining, l'istruzione EXPORT esporta automaticamente tutti i modelli associati.</span><span class="sxs-lookup"><span data-stu-id="ea898-109">When you export a mining structure, the EXPORT statement automatically exports all associated models.</span></span> <span data-ttu-id="ea898-110">Se si desidera controllare gli oggetti esportati, è necessario specificare ogni oggetto per nome.</span><span class="sxs-lookup"><span data-stu-id="ea898-110">If you want to control the objects that are exported, you must specify each object by name.</span></span>  
  
 <span data-ttu-id="ea898-111">Se durante l'esportazione la struttura di data mining è stata elaborata e i risultati sono stati memorizzati nella cache, che rappresenta il comportamento predefinito, la definizione conterrà un riepilogo dei dati su cui si basa la struttura.</span><span class="sxs-lookup"><span data-stu-id="ea898-111">If the mining structure has been processed and the results have been cached, which is the default behavior, when you export the mining structure, the definition contains a summary of the data on which the structure is based.</span></span> <span data-ttu-id="ea898-112">Per rimuovere questo riepilogo, è necessario cancellare la cache associata alla struttura di data mining eseguendo l'operazione `Process Clear Structure`.</span><span class="sxs-lookup"><span data-stu-id="ea898-112">To remove this summary, you must clear the cache associated with the mining structure by performing a `Process Clear Structure` operation.</span></span> <span data-ttu-id="ea898-113">Per altre informazioni, vedere [Elaborare una struttura di data mining](process-a-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ea898-113">For more information, see [Process a Mining Structure](process-a-mining-structure.md).</span></span>  
  
### <a name="exporting-data-mining-models"></a><span data-ttu-id="ea898-114">Esportazione di modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="ea898-114">Exporting Data Mining Models</span></span>  
 <span data-ttu-id="ea898-115">È possibile utilizzare la parola chiave `WITH DEPENDENCIES` per esportare l'origine dati e la definizione della vista origine dati insieme al modello di data mining e alla relativa struttura.</span><span class="sxs-lookup"><span data-stu-id="ea898-115">You can use the `WITH DEPENDENCIES` keyword to export the data source and data source view definition together with the mining model and its structure.</span></span>  
  
 <span data-ttu-id="ea898-116">Quando si esporta un modello di data mining senza esportarne le dipendenze, l'istruzione EXPORT esporta la definizione del modello di data mining e la relativa struttura di data mining, ma non la definizione delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="ea898-116">When you export a mining model without exporting its dependencies, the EXPORT statement will export the definition of the mining model and its mining structure, but does not export the definition of the data sources.</span></span> <span data-ttu-id="ea898-117">Di conseguenza, dopo aver importato il modello sarà possibile esplorarlo immediatamente ma, se si desidera rielaborarlo nel server di destinazione o eseguire query sui dati sottostanti, sarà necessario creare un'origine dati corrispondente nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ea898-117">As a consequence, after you import the model you will be able to browse the model immediately, but if you want to reprocess the mining model on the target server, or run queries against the underlying data, you must create a corresponding data source on the destination server.</span></span>  
  
## <a name="importing-data-mining-structures-and-models"></a><span data-ttu-id="ea898-118">Importazione di strutture e modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="ea898-118">Importing Data Mining Structures and Models</span></span>  
 <span data-ttu-id="ea898-119">Quando si importa un oggetto di data mining, esso viene importato nel server e nel database ai cui si è connessi quando si esegue l'istruzione IMPORT.</span><span class="sxs-lookup"><span data-stu-id="ea898-119">When you import a data mining object, the object is imported to the server and database to which you are connected when you execute the IMPORT statement.</span></span> <span data-ttu-id="ea898-120">Se il file di importazione include un database che non esiste nel server, il database verrà creato.</span><span class="sxs-lookup"><span data-stu-id="ea898-120">If the import file includes a database that does not exist on the server, the database will be created.</span></span>  
  
 <span data-ttu-id="ea898-121">È inoltre possibile importare una struttura o un modello di data mining mediante il comando `Restore`.</span><span class="sxs-lookup"><span data-stu-id="ea898-121">You can also import a mining structure or mining model by using the `Restore` command.</span></span> <span data-ttu-id="ea898-122">I modelli o le strutture verranno ripristinate nel database che presenta lo stesso nome del database dal quale sono stati esportati.</span><span class="sxs-lookup"><span data-stu-id="ea898-122">Your models or structures will be restored into the database that has the same name as the database from which they were exported.</span></span> <span data-ttu-id="ea898-123">Per altre informazioni, vedere [Opzioni di ripristino](../multidimensional-models/restore-options.md).</span><span class="sxs-lookup"><span data-stu-id="ea898-123">For more information, see [Restore Options](../multidimensional-models/restore-options.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea898-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea898-124">Remarks</span></span>  
 <span data-ttu-id="ea898-125">Non è possibile importare un modello o una struttura in un server se in tale server è già presente un modello o una struttura con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="ea898-125">You cannot import a model or structure to a server if a model or structure of the same name already exists on that server.</span></span> <span data-ttu-id="ea898-126">Inoltre, non è possibile esportare un oggetto di data mining, quindi modificarne il nome nel file di esportazione.</span><span class="sxs-lookup"><span data-stu-id="ea898-126">Also, you cannot export a data mining object and then modify the name of that object in the export file.</span></span> <span data-ttu-id="ea898-127">Pertanto, se si prevedono conflitti di denominazione, è necessario eliminare l'oggetto di data mining nel server di destinazione o rinominare l'oggetto di data mining prima di esportare la definizione.</span><span class="sxs-lookup"><span data-stu-id="ea898-127">Therefore, if you anticipate naming conflicts, you should either delete the data mining object on the target server, or rename the data mining object before you export the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea898-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea898-128">See Also</span></span>  
 [<span data-ttu-id="ea898-129">Gestione degli oggetti e delle soluzioni di data mining</span><span class="sxs-lookup"><span data-stu-id="ea898-129">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
