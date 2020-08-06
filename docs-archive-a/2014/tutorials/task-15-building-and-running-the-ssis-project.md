---
title: 'Attività 15: compilazione ed esecuzione del progetto SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719025"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="d987e-102">Attività 15: Compilazione ed esecuzione del progetto SSIS</span><span class="sxs-lookup"><span data-stu-id="d987e-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="d987e-103">In questa attività viene compilato ed eseguito il progetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="d987e-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="d987e-104">Se nel computer è installata la versione a 64 bit di Excel 2010, è necessario impostare il valore di **Run64BitRuntime** su **false** per il funzionamento dell'origine Excel.</span><span class="sxs-lookup"><span data-stu-id="d987e-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="d987e-105">Nella finestra di **Esplora soluzioni** fare clic su **progetto** nel menu e quindi su **Proprietà CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="d987e-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="d987e-106">Nella finestra di dialogo **Proprietà** espandere **proprietà di configurazione** a sinistra e fare clic su **debug**.</span><span class="sxs-lookup"><span data-stu-id="d987e-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="d987e-107">Impostare **Run64BitRuntime** su **false**.</span><span class="sxs-lookup"><span data-stu-id="d987e-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="d987e-108">![Proprietà progetto CleanseAndCurateSuppliers](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "Proprietà progetto CleanseAndCurateSuppliers")</span><span class="sxs-lookup"><span data-stu-id="d987e-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="d987e-109">Scegliere **OK** per chiudere la finestra di dialogo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d987e-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="d987e-110">Fare clic su **Compila** sulla barra dei menu e quindi su **Compila CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="d987e-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="d987e-111">Assicurarsi che non siano presenti errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d987e-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="d987e-112">Fare clic su **debug** nella barra dei menu e fare clic su **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="d987e-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="d987e-113">Esaminare i messaggi nella finestra di stato e verificare che il pacchetto sia **stato** eseguito e terminato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d987e-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="d987e-114">![Risultati dalla finestra di stato](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Risultati dalla finestra di stato")</span><span class="sxs-lookup"><span data-stu-id="d987e-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="d987e-115">![Stato finale dalla finestra di stato](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Stato finale dalla finestra di stato")</span><span class="sxs-lookup"><span data-stu-id="d987e-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="d987e-116">Fare clic su **debug** nella barra dei menu e fare clic su **Interrompi debug** per arrestare la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="d987e-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="d987e-117">Se il pacchetto ha esito negativo, è necessario abilitare i visualizzatori dati e verificare il flusso dei dati tra i componenti.</span><span class="sxs-lookup"><span data-stu-id="d987e-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d987e-118">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d987e-118">Next Step</span></span>  
 [<span data-ttu-id="d987e-119">Attività 16: Verifica con Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="d987e-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  
