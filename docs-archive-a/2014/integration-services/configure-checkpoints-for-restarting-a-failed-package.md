---
title: Configurare i checkpoint per il riavvio di un pacchetto non riuscito | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721671"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="78b86-102">Configurazione dei checkpoint per il riavvio di un pacchetto non riuscito</span><span class="sxs-lookup"><span data-stu-id="78b86-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="78b86-103">Impostando le proprietà relative ai checkpoint, è possibile configurare i pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in modo che vengano riavviati dal momento dell'errore, anziché essere eseguiti nuovamente dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="78b86-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="78b86-104">Per configurare un pacchetto per il riavvio</span><span class="sxs-lookup"><span data-stu-id="78b86-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="78b86-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="78b86-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="78b86-106">In **Esplora soluzioni**fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="78b86-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="78b86-107">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="78b86-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="78b86-108">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo dell'area di progettazione del flusso di controllo, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78b86-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="78b86-109">Impostare la proprietà SaveCheckpoints su `True` .</span><span class="sxs-lookup"><span data-stu-id="78b86-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="78b86-110">Digitare il nome del file del checkpoint nella proprietà CheckpointFileName.</span><span class="sxs-lookup"><span data-stu-id="78b86-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="78b86-111">Impostare la proprietà CheckpointUsage su uno dei due valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="78b86-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="78b86-112">Selezionare `Always` per riavviare sempre il pacchetto dal checkpoint.</span><span class="sxs-lookup"><span data-stu-id="78b86-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="78b86-113">Se il file del checkpoint non è disponibile, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="78b86-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="78b86-114">Selezionare `IfExists` per riavviare il pacchetto solo se il file del checkpoint è disponibile.</span><span class="sxs-lookup"><span data-stu-id="78b86-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="78b86-115">Configurare le attività e i contenitori da cui è possibile riavviare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="78b86-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="78b86-116">Fare clic con il pulsante destro del mouse su un'attività o un contenitore, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78b86-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="78b86-117">Impostare la proprietà FailPackageOnFailure su `True` per ogni attività e contenitore selezionati.</span><span class="sxs-lookup"><span data-stu-id="78b86-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b86-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78b86-118">See Also</span></span>  
 [<span data-ttu-id="78b86-119">Riavvio dei pacchetti tramite checkpoint</span><span class="sxs-lookup"><span data-stu-id="78b86-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  
