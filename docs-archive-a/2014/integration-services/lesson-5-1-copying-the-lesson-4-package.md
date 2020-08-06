---
title: 'Passaggio 1: Copia del pacchetto della lezione 4 | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637425"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="d3e6e-102">Passaggio 1: Copia del pacchetto della lezione 4</span><span class="sxs-lookup"><span data-stu-id="d3e6e-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="d3e6e-103">In questa attività si procederà alla creazione di una copia del pacchetto creato nella lezione 4, denominato Lesson 4.dtsx.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="d3e6e-104">In alternativa, è possibile aggiungere al progetto il pacchetto completo della lezione 4 incluso nell'esercitazione e, successivamente, copiarlo.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="d3e6e-105">Questa nuova copia verrà usata per tutto il seguito della lezione 5.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="d3e6e-106">Per copiare il pacchetto della lezione 4</span><span class="sxs-lookup"><span data-stu-id="d3e6e-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="d3e6e-107">Se [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools non è già aperto, fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2012**, quindi selezionare **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="d3e6e-108">Scegliere **Apri** dal menu **File**, fare clic su **Progetto/Soluzione**, selezionare **SSIS Tutorial** e fare clic su **Apri**, quindi fare doppio clic su **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="d3e6e-109">In Esplora soluzioni fare clic con il pulsante destro del mouse su **Lesson 4.dtsx**e quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="d3e6e-110">In Esplora soluzioni fare clic con il pulsante destro del mouse su **pacchetti SSIS**e quindi scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="d3e6e-111">Per impostazione predefinita, il pacchetto copiato viene denominato Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="d3e6e-112">In Esplora soluzioni fare doppio clic su **Lesson 5.dtsx** per aprire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="d3e6e-113">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo della scheda **flusso di controllo** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="d3e6e-114">Nella Finestra Proprietà aggiornare la `Name` proprietà a `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="d3e6e-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="d3e6e-115">Fare clic sulla casella relativa alla proprietà **ID** , fare clic sulla freccia a discesa, quindi scegliere **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="d3e6e-116">Per aggiungere il pacchetto della lezione 4 completato</span><span class="sxs-lookup"><span data-stu-id="d3e6e-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="d3e6e-117">Aprire [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools e il progetto SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="d3e6e-118">In Esplora soluzioni fare clic con il pulsante destro del mouse su **pacchetti SSIS**e scegliere **Aggiungi pacchetto esistente**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="d3e6e-119">Nella finestra di dialogo **Aggiungi copia del pacchetto esistente** , in **Posizione pacchetto**, selezionare **File system**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="d3e6e-120">Fare clic sul pulsante Sfoglia **(...)** , passare a **Lesson 4. dtsx** nel computer e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="d3e6e-121">Per scaricare tutti i pacchetti di lezioni di questa esercitazione, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="d3e6e-122">Passare alla pagina relativa agli [esempi di prodotti di Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="d3e6e-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="d3e6e-123">Fare clic sulla scheda **Downloads** .</span><span class="sxs-lookup"><span data-stu-id="d3e6e-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="d3e6e-124">Fare clic sul file SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="d3e6e-125">Copiare e incollare il pacchetto della lezione 4, come illustrato nei passaggi 3-8 della procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="d3e6e-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d3e6e-126">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="d3e6e-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d3e6e-127">Passaggio 2: Abilitazione e impostazione delle configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="d3e6e-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
