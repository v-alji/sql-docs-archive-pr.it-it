---
title: 'Lezione 5: aggiunta di configurazioni del pacchetto per il modello di distribuzione del pacchetto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1c10dd54-67cb-4b63-9e4d-aa6ff0452ecb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ee03d624ac7144cf6aef0829bcb7835fe5af9c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713304"
---
# <a name="lesson-5-adding-package-configurations-for-the-package-deployment-model"></a><span data-ttu-id="9911e-102">Lezione 5: Aggiunta di configurazioni del pacchetto per il modello di distribuzione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="9911e-102">Lesson 5: Adding Package Configurations for the Package Deployment Model</span></span>
  <span data-ttu-id="9911e-103">Le configurazioni di pacchetto consentono di impostare variabili e proprietà di runtime all'esterno dell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="9911e-103">Package configurations let you set run-time properties and variables from outside of the development environment.</span></span> <span data-ttu-id="9911e-104">Le configurazioni consentono inoltre di sviluppare pacchetti flessibili e semplici da implementare e distribuire.</span><span class="sxs-lookup"><span data-stu-id="9911e-104">Configurations allow you to develop packages that are flexible and easy to both deploy and distribute.</span></span> <span data-ttu-id="9911e-105">In [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono disponibili i tipi di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="9911e-105">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offers the following configuration types:</span></span>  
  
-   <span data-ttu-id="9911e-106">File di configurazione XML</span><span class="sxs-lookup"><span data-stu-id="9911e-106">XML configuration file</span></span>  
  
-   <span data-ttu-id="9911e-107">Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="9911e-107">Environment variable</span></span>  
  
-   <span data-ttu-id="9911e-108">Voce del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9911e-108">Registry entry</span></span>  
  
-   <span data-ttu-id="9911e-109">Variabile pacchetto padre</span><span class="sxs-lookup"><span data-stu-id="9911e-109">Parent package variable</span></span>  
  
-   <span data-ttu-id="9911e-110">Tabella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9911e-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>  
  
 <span data-ttu-id="9911e-111">In questa lezione verrà modificato il pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] semplice creato nella [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) per usare il modello di distribuzione del pacchetto e le configurazioni del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9911e-111">In this lesson, you will modify the simple [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you created in [Lesson 4: Adding Error Flow Redirection](lesson-4-add-error-flow-redirection-with-ssis.md) to use the Package Deployment Model and take advantage of package configurations.</span></span> <span data-ttu-id="9911e-112">È inoltre possibile copiare il pacchetto della lezione 4 completato incluso nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="9911e-112">You can also copy the completed Lesson 4 package that is included with the tutorial.</span></span> <span data-ttu-id="9911e-113">Configurazione guidata pacchetto consente di creare una configurazione XML che aggiorna la proprietà `Directory` del contenitore Ciclo Foreach tramite una variabile a livello di pacchetto associata alla proprietà Directory.</span><span class="sxs-lookup"><span data-stu-id="9911e-113">Using the Package Configuration Wizard, you will create an XML configuration that updates the `Directory` property of the Foreach Loop container by using a package-level variable mapped to the Directory property.</span></span> <span data-ttu-id="9911e-114">Dopo aver creato il file di configurazione è possibile modificare il valore della variabile all'esterno dell'ambiente di sviluppo e puntare la proprietà modificata a una nuova cartella di dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="9911e-114">Once you have created the configuration file, you will modify the value of the variable from outside of the development environment and point the modified property to a new sample data folder.</span></span> <span data-ttu-id="9911e-115">Quando si esegue di nuovo il pacchetto, il file di configurazione popola il valore della variabile e la variabile a sua volta aggiorna la `Directory` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9911e-115">When you run the package again, the configuration file populates the value of the variable, and the variable in turn updates the `Directory` property.</span></span> <span data-ttu-id="9911e-116">Di conseguenza, il pacchetto esegue un'iterazione della nuova cartella dei dati anziché della cartella originale specificata a livello di codice nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9911e-116">As a result, the package iterates through the files in the new data folder, rather than iterating through the files in the original folder that was hard-coded in the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9911e-117">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="9911e-117">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="9911e-118">Per altre informazioni sull'installazione e sulla distribuzione di **AdventureWorksDW2012**, vedere la pagina relativa agli [esempi del prodotto Reporting Services su CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span><span class="sxs-lookup"><span data-stu-id="9911e-118">For more information about how to install and deploy **AdventureWorksDW2012**, see [Reporting Services Product Samples on CodePlex](https://go.microsoft.com/fwlink/?LinkID=526910).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9911e-119">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="9911e-119">Lesson Tasks</span></span>  
 <span data-ttu-id="9911e-120">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="9911e-120">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="9911e-121">Passaggio 1: Copia del pacchetto della lezione 4</span><span class="sxs-lookup"><span data-stu-id="9911e-121">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
-   [<span data-ttu-id="9911e-122">Passaggio 2: Abilitazione e impostazione delle configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="9911e-122">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
-   [<span data-ttu-id="9911e-123">Passaggio 3: Modifica del valore di configurazione della proprietà Directory</span><span class="sxs-lookup"><span data-stu-id="9911e-123">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
-   [<span data-ttu-id="9911e-124">Passaggio 4: Test del pacchetto creato nell'esercitazione della lezione 5</span><span class="sxs-lookup"><span data-stu-id="9911e-124">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="9911e-125">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="9911e-125">Start the Lesson</span></span>  
  
-   [<span data-ttu-id="9911e-126">Passaggio 1: Copia del pacchetto della lezione 4</span><span class="sxs-lookup"><span data-stu-id="9911e-126">Step 1: Copying the Lesson 4 Package</span></span>](lesson-5-1-copying-the-lesson-4-package.md)  
  
  
