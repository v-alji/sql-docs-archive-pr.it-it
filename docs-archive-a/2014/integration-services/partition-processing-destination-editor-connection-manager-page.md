---
title: Editor destinazione elaborazione partizione (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.connection.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: 7add6f82-eed1-47fc-a5d7-7b91f3f24d34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a0f79dfcc9c0d98d871a49618f4dabfb8a3bbac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627867"
---
# <a name="partition-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="44d0b-102">Editor destinazione elaborazione partizione (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="44d0b-102">Partition Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="44d0b-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione elaborazione partizione** per specificare una connessione a un progetto di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44d0b-103">Use the **Connection Manager** page of the **Partition Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="44d0b-104">Per ulteriori informazioni sulla destinazione elaborazione partizione, vedere [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="44d0b-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44d0b-105">Le attività qui descritte non si applicano ai modelli tabulari di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="44d0b-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="44d0b-106">Non è possibile eseguire il mapping di colonne di input a colonne di partizione per i modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="44d0b-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="44d0b-107">È possibile utilizzare invece l'attività Esegui DDL Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) per elaborare la partizione.</span><span class="sxs-lookup"><span data-stu-id="44d0b-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="44d0b-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="44d0b-108">Options</span></span>  
 <span data-ttu-id="44d0b-109">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="44d0b-109">**Connection manager**</span></span>  
 <span data-ttu-id="44d0b-110">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="44d0b-110">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="44d0b-111">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="44d0b-111">**New**</span></span>  
 <span data-ttu-id="44d0b-112">Consente di creare una connessione usando la finestra di dialogo **Aggiungi gestione connessione Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="44d0b-112">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="44d0b-113">**Elenco delle partizioni disponibili**</span><span class="sxs-lookup"><span data-stu-id="44d0b-113">**List of available partitions**</span></span>  
 <span data-ttu-id="44d0b-114">Consente di selezionare la partizione da elaborare.</span><span class="sxs-lookup"><span data-stu-id="44d0b-114">Select the partition to process.</span></span>  
  
 <span data-ttu-id="44d0b-115">**Metodo di elaborazione**</span><span class="sxs-lookup"><span data-stu-id="44d0b-115">**Processing method**</span></span>  
 <span data-ttu-id="44d0b-116">Consente di selezionare il metodo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="44d0b-116">Select the processing method.</span></span> <span data-ttu-id="44d0b-117">Il valore predefinito di questa opzione è **Completo**.</span><span class="sxs-lookup"><span data-stu-id="44d0b-117">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="44d0b-118">Valore</span><span class="sxs-lookup"><span data-stu-id="44d0b-118">Value</span></span>|<span data-ttu-id="44d0b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44d0b-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44d0b-120">Aggiunta (incrementale)</span><span class="sxs-lookup"><span data-stu-id="44d0b-120">Add (incremental)</span></span>|<span data-ttu-id="44d0b-121">Consente di eseguire un'elaborazione incrementale della partizione.</span><span class="sxs-lookup"><span data-stu-id="44d0b-121">Perform an incremental processing of the partition.</span></span>|  
|<span data-ttu-id="44d0b-122">Full</span><span class="sxs-lookup"><span data-stu-id="44d0b-122">Full</span></span>|<span data-ttu-id="44d0b-123">Consente di eseguire l'elaborazione completa della partizione.</span><span class="sxs-lookup"><span data-stu-id="44d0b-123">Perform full processing of the partition.</span></span>|  
|<span data-ttu-id="44d0b-124">Solo dati</span><span class="sxs-lookup"><span data-stu-id="44d0b-124">Data only</span></span>|<span data-ttu-id="44d0b-125">Consente di eseguire un'elaborazione di aggiornamento della partizione.</span><span class="sxs-lookup"><span data-stu-id="44d0b-125">Perform an update processing of the partition.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44d0b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44d0b-126">See Also</span></span>  
 <span data-ttu-id="44d0b-127">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="44d0b-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="44d0b-128">[Editor destinazione elaborazione partizione &#40;pagina mapping&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="44d0b-128">[Partition Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/partition-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="44d0b-129">Editor destinazione elaborazione partizione &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="44d0b-129">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
