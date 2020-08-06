---
title: 'Passaggio 1: Copia del pacchetto della lezione 5 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637993"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="6e6e9-102">Passaggio 1: Copia del pacchetto della lezione 5</span><span class="sxs-lookup"><span data-stu-id="6e6e9-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="6e6e9-103">In questa attività si procederà alla creazione di una copia del pacchetto della lezione 5, denominato Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="6e6e9-104">In alternativa, è possibile aggiungere al progetto il pacchetto completo della lezione 5 incluso nell'esercitazione e, successivamente, copiarlo.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="6e6e9-105">Questa nuova copia verrà utilizzata per tutto il seguito della lezione 6.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="6e6e9-106">Per copiare il pacchetto della lezione 5</span><span class="sxs-lookup"><span data-stu-id="6e6e9-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="6e6e9-107">Se SQL Server Data Tools non è già aperto, fare clic sul pulsante Start, scegliere Tutti i programmi, Microsoft SQL Server 2012, quindi selezionare SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="6e6e9-108">Scegliere Apri dal menu File, fare clic su Progetto/Soluzione, selezionare SSIS Tutorial fare clic su Apri, quindi fare doppio clic su SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="6e6e9-109">In Esplora soluzioni fare clic con il pulsante destro del mouse su Lesson 5.dtsx e quindi scegliere Copia.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="6e6e9-110">In Esplora soluzioni fare clic con il pulsante destro del mouse su Pacchetti SSIS e quindi scegliere Incolla.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="6e6e9-111">Per impostazione predefinita, il pacchetto copiato viene denominato Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="6e6e9-112">In Esplora soluzioni fare doppio clic su Lesson 6.dtsx per aprire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="6e6e9-113">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo della scheda Flusso di controllo e scegliere Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="6e6e9-114">Nella finestra Proprietà aggiornare la proprietà Name impostandola su Lesson 6.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="6e6e9-115">Fare clic sulla casella relativa alla proprietà ID, fare clic sulla freccia a discesa, quindi scegliere \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="6e6e9-116">Per aggiungere il pacchetto della lezione 5 completato</span><span class="sxs-lookup"><span data-stu-id="6e6e9-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="6e6e9-117">Aprire SQL Server Data Tools e il progetto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="6e6e9-118">In Esplora soluzioni fare clic con il pulsante destro del mouse su Pacchetti SSIS e scegliere Aggiungi pacchetto esistente.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="6e6e9-119">Nella finestra di dialogo Aggiungi copia del pacchetto esistente, in Posizione pacchetto, selezionare File system.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="6e6e9-120">Fare clic sul pulsante Sfoglia (...), Lesson 5. dtsx nel computer e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="6e6e9-121">Per scaricare tutti i pacchetti di lezioni di questa esercitazione, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="6e6e9-122">Passare alla pagina relativa agli [esempi di prodotti di Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="6e6e9-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="6e6e9-123">Fare clic sulla scheda **Downloads** .</span><span class="sxs-lookup"><span data-stu-id="6e6e9-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="6e6e9-124">Fare clic sul file SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="6e6e9-125">Copiare e incollare il pacchetto della lezione 5, come illustrato nei passaggi 3-8 della procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="6e6e9-126">Dopo la copia del pacchetto della lezione 5, se si dispone dei pacchetti delle lezioni precedenti nella soluzione, fare clic con il pulsante destro del mouse su ogni pacchetto delle lezioni 1-5 e fare clic su Escludi dal progetto.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="6e6e9-127">Al termine sarà presente un solo pacchetto Lesson 6.dtsx nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="6e6e9-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6e6e9-128">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="6e6e9-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6e6e9-129">Passaggio 2: Conversione del progetto nel modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="6e6e9-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
