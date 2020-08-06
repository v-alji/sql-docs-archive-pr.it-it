---
title: 'Passaggio 1: Copia del pacchetto della lezione 2 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bd91402-4e37-41de-ab78-8ca5a1948a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39bfc965febc401bd66b1077388021b8ccf52aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715564"
---
# <a name="step-1-copying-the-lesson-2-package"></a><span data-ttu-id="ece46-102">Passaggio 1: Copia del pacchetto della lezione 2</span><span class="sxs-lookup"><span data-stu-id="ece46-102">Step 1: Copying the Lesson 2 Package</span></span>
  <span data-ttu-id="ece46-103">In questa attività si procederà alla creazione di una copia del pacchetto della lezione 2, denominato Lesson 2.dtsx.</span><span class="sxs-lookup"><span data-stu-id="ece46-103">In this task, you will create a copy of the Lesson 2.dtsx package that you created in Lesson 2.</span></span> <span data-ttu-id="ece46-104">In alternativa è possibile aggiungere al progetto il pacchetto completo della lezione 2 incluso nell'esercitazione e successivamente copiarlo.</span><span class="sxs-lookup"><span data-stu-id="ece46-104">Alternatively, you can add the completed lesson 2 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="ece46-105">Questa nuova copia verrà usata per il resto della lezione 3.</span><span class="sxs-lookup"><span data-stu-id="ece46-105">You will use this new copy throughout the rest of Lesson 3.</span></span>  
  
### <a name="to-create-the-lesson-3-package"></a><span data-ttu-id="ece46-106">Per creare il pacchetto della lezione 3</span><span class="sxs-lookup"><span data-stu-id="ece46-106">To create the Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="ece46-107">Se [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools non è già aperto, fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2012**, quindi selezionare **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ece46-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="ece46-108">Scegliere **Apri** dal menu **File**, fare clic su **Progetto/Soluzione**, selezionare **SSIS Tutorial** e fare clic su **Apri**, quindi fare doppio clic su **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="ece46-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="ece46-109">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Lesson 2.dtsx**e fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="ece46-109">In Solution Explorer, right-click **Lesson 2.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="ece46-110">In Esplora soluzioni fare clic con il pulsante destro del mouse su **pacchetti SSIS**e quindi scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="ece46-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="ece46-111">Per impostazione predefinita, il pacchetto copiato viene denominato Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="ece46-111">By default, the copied package is named Lesson 3.dtsx.</span></span>  
  
5.  <span data-ttu-id="ece46-112">In Esplora soluzioni fare doppio clic su **Lesson 3. dtsx** per aprire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ece46-112">In Solution Explorer, double-click **Lesson 3.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="ece46-113">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo della scheda **Flusso di controllo** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="ece46-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="ece46-114">Nella Finestra Proprietà aggiornare la `Name` proprietà a `Lesson 3` .</span><span class="sxs-lookup"><span data-stu-id="ece46-114">In the Properties window, update the `Name` property to `Lesson 3`.</span></span>  
  
8.  <span data-ttu-id="ece46-115">Fare clic sulla casella relativa alla proprietà **ID** , e poi nell'elenco selezionare **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="ece46-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson2-package"></a><span data-ttu-id="ece46-116">Per aggiungere il pacchetto della lezione 2 completato</span><span class="sxs-lookup"><span data-stu-id="ece46-116">To add the completed Lesson2 package</span></span>  
  
1.  <span data-ttu-id="ece46-117">Aprire [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] e aprire il progetto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="ece46-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="ece46-118">In Esplora soluzioni fare clic con il pulsante destro del mouse su **pacchetti SSIS**e scegliere **Aggiungi pacchetto esistente**.</span><span class="sxs-lookup"><span data-stu-id="ece46-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="ece46-119">Nella finestra di dialogo **Aggiungi copia del pacchetto esistente** , in **Posizione pacchetto**, selezionare **File system**.</span><span class="sxs-lookup"><span data-stu-id="ece46-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="ece46-120">Fare clic sul pulsante sfoglia **(...)**, passare a **Lesson 2.dtsx** nel computer, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="ece46-120">Click the browse **(...)** button, navigate to **Lesson 2.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="ece46-121">Per scaricare tutti i pacchetti di lezioni di questa esercitazione, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ece46-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="ece46-122">Passare alla pagina relativa agli [esempi di prodotti di Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="ece46-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="ece46-123">Fare clic sulla scheda **Downloads** .</span><span class="sxs-lookup"><span data-stu-id="ece46-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="ece46-124">Fare clic sul file SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="ece46-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="ece46-125">Copiare e incollare il pacchetto della lezione 3, come illustrato nei passaggi 3-8 della procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="ece46-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ece46-126">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="ece46-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ece46-127">Passaggio 2: Aggiunta e configurazione di funzionalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="ece46-127">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
  
