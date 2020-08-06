---
title: Aggiungere o eliminare un componente in un flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713355"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="909cb-102">Aggiunta o eliminazione di un componente in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="909cb-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="909cb-103">I componenti dei flussi di dati sono le origini, le destinazioni e le trasformazioni incluse in un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="909cb-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="909cb-104">È possibile aggiungere componenti a un flusso di dati solo se il flusso di controllo del pacchetto include un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="909cb-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="909cb-105">Nelle procedure seguenti viene descritto come aggiungere o eliminare un componente nel flusso di dati di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="909cb-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="909cb-106">Per aggiungere un componente a un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="909cb-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="909cb-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="909cb-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="909cb-108">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="909cb-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="909cb-109">Fare clic sulla scheda **Flusso di controllo** e quindi fare doppio clic sull'attività Flusso di dati che contiene il flusso di dati al quale si vuole aggiungere un componente.</span><span class="sxs-lookup"><span data-stu-id="909cb-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="909cb-110">Nella casella degli strumenti espandere **Origini flusso di dati**, **Trasformazioni flusso di dati**o **Destinazioni flusso di dati**e quindi trascinare un elemento flusso di dati nell'area di progettazione della scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="909cb-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="909cb-111">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="909cb-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="909cb-112">Per eliminare un componente da un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="909cb-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="909cb-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="909cb-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="909cb-114">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="909cb-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="909cb-115">Fare clic sulla scheda **Flusso di controllo** e quindi fare doppio clic sull'attività Flusso di dati che contiene il flusso di dati dal quale si vuole eliminare un componente.</span><span class="sxs-lookup"><span data-stu-id="909cb-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="909cb-116">Fare clic con il pulsante destro del mouse sul componente flusso di dati e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="909cb-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="909cb-117">Confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="909cb-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="909cb-118">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="909cb-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909cb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="909cb-119">See Also</span></span>  
 <span data-ttu-id="909cb-120">[Connessione di componenti in un flusso di dati](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="909cb-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="909cb-121">[Configurare un output degli errori in un componente flusso di dati](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="909cb-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="909cb-122">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="909cb-122">Data Flow</span></span>](data-flow.md)  
  
  
