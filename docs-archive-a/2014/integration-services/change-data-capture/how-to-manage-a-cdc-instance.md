---
title: Procedura di gestione di un'istanza di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712287"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="84a60-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="84a60-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="84a60-103">In questa procedura viene illustrato come utilizzare CDC Designer Console per gestire le operazioni dell'istanza di CDC al runtime.</span><span class="sxs-lookup"><span data-stu-id="84a60-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="84a60-104">Per gestire le operazioni dell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="84a60-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="84a60-105">Scegliere **CDC Designer Console** dal menu **Start**.</span><span class="sxs-lookup"><span data-stu-id="84a60-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="84a60-106">Nel riquadro sinistro espandere **Change Data Capture** , quindi espandere il servizio che contiene l'istanza che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="84a60-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="84a60-107">Selezionare il nome di un'istanza che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="84a60-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="84a60-108">Nel riquadro **Actions** sul lato destro di CDC Designer Console, fare clic sull'operazione che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="84a60-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="84a60-109">È anche possibile fare clic con il pulsante destro del mouse sul nome dell'istanza nel riquadro sinistro e selezionare l'operazione che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="84a60-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="84a60-110">È possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="84a60-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="84a60-111">**Start**: avvio dell'acquisizione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="84a60-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="84a60-112">**Stop**: arresto dell'acquisizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="84a60-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="84a60-113">**Reset**: fare clic su **Reset** per reimpostare l'istanza di CDC sullo stato iniziale (vuoto).</span><span class="sxs-lookup"><span data-stu-id="84a60-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="84a60-114">Questa opzione diventa disponibile dopo che l'istanza di CDC è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="84a60-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="84a60-115">Tutte le modifiche presenti nelle tabelle delle modifiche e lo stato interno dell'istanza di CDC vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="84a60-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="84a60-116">Al successivo avvio dell'istanza di CDC, l'acquisizione delle modifiche verrà avviata da quel momento e includerà solo le transazioni avviate dopo l'avvio dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="84a60-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="84a60-117">**Delete**: eliminazione dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="84a60-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="84a60-118">**Oracle Logging Script**: fare clic su **Oracle Logging Script** per visualizzare la finestra di dialogo Oracle Logging Script contenente lo script della registrazione supplementare Oracle.</span><span class="sxs-lookup"><span data-stu-id="84a60-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="84a60-119">Per informazioni sulle operazioni che è possibile eseguire in questa finestra di dialogo, vedere [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="84a60-120">**Nota**: quando si eseguono gli script di registrazione supplementare, viene visualizzata la finestra di dialogo Oracle Credentials for Running Script in cui immettere un nome utente e una password Oracle validi.</span><span class="sxs-lookup"><span data-stu-id="84a60-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="84a60-121">Per informazioni su come fornire le credenziali Oracle appropriate, vedere [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="84a60-122">**CDC Instance Deployment**: generazione di uno script di distribuzione per l'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="84a60-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="84a60-123">Per informazioni su questa finestra di dialogo, vedere [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="84a60-124">Per ulteriori informazioni su queste attività, vedere [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="84a60-125">È inoltre possibile selezionare **Properties** per modificare le proprietà di configurazione dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="84a60-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="84a60-126">Per ulteriori informazioni sulla modifica delle proprietà dell'istanza di CDC, vedere [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
