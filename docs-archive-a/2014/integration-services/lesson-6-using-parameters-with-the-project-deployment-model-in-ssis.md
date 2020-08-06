---
title: 'Lezione 6: utilizzo di parametri con il modello di distribuzione del progetto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9216f18c-1762-4f2d-8c22-bd0ab7107555
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4bdc6b9dfc019822d6cf1bd9ec7d89ffcc5ea5e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626138"
---
# <a name="lesson-6-using-parameters-with-the-project-deployment-model"></a><span data-ttu-id="daee0-102">Lezione 6: Uso di parametri con il modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="daee0-102">Lesson 6: Using Parameters with the Project Deployment Model</span></span>
  <span data-ttu-id="daee0-103">In SQL Server 2012 è disponibile un nuovo modello di distribuzione in cui è possibile distribuire i progetti nel server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="daee0-103">SQL Server 2012 introduces a new deployment model where you can deploy your projects to the Integration Services server.</span></span> <span data-ttu-id="daee0-104">Il server Integration Services consente di gestire ed eseguire pacchetti e di configurare i valori di runtime per i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="daee0-104">The Integration Services server enables you to manage and run packages, and to configure runtime values for packages.</span></span>  
  
 <span data-ttu-id="daee0-105">In questa lezione verrà modificato il pacchetto creato nella [lezione 5: aggiunta di configurazioni del pacchetto per il modello di distribuzione del pacchetto per l'](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) utilizzo del modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="daee0-105">In this lesson, you will modify the package that you created in [Lesson 5: Adding Package Configurations for the Package Deployment Model](lesson-5-add-ssis-package-configurations-for-the-package-deployment-model.md) to use the Project Deployment Model.</span></span> <span data-ttu-id="daee0-106">Sostituire il valore di configurazione con un parametro per specificare la posizione dei dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="daee0-106">You replace the configuration value with a parameter to specify the sample data location.</span></span> <span data-ttu-id="daee0-107">È inoltre possibile copiare il pacchetto della lezione 5 completato incluso nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="daee0-107">You can also copy the completed Lesson 5 package that is included with the tutorial.</span></span>  
  
 <span data-ttu-id="daee0-108">Mediante la configurazione guidata progetti di Integration Services convertire il progetto nel modello di distribuzione del progetto e utilizzare un parametro anziché un valore di configurazione per impostare la proprietà Directory.</span><span class="sxs-lookup"><span data-stu-id="daee0-108">Using the Integration Services Project Configuration Wizard, you will convert the project to the Project Deployment Model and use a Parameter rather than a configuration value to set the Directory property.</span></span> <span data-ttu-id="daee0-109">In questa lezione vengono illustrati solo alcuni dei passaggi per convertire i pacchetti esistenti SSIS nel nuovo modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="daee0-109">This lesson partially covers the steps you would follow to convert existing SSIS packages to the new Project Deployment Model.</span></span>  
  
 <span data-ttu-id="daee0-110">Quando il pacchetto viene di nuovo eseguito, il servizio Integration Services usa il parametro per popolare il valore della variabile e la variabile a sua volta aggiorna la proprietà Directory.</span><span class="sxs-lookup"><span data-stu-id="daee0-110">When you run the package again, the Integration Services service uses the parameter to populate the value of the variable, and the variable in turn updates the Directory property.</span></span> <span data-ttu-id="daee0-111">Di conseguenza, tramite il pacchetto viene eseguita un'iterazione della nuova cartella dei dati specificata dal valore del parametro anziché della cartella impostata nel file di configurazione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="daee0-111">As a result, the package iterates through the files in the new data folder specified by the parameter value rather than the folder that was set in the package configuration file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="daee0-112">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="daee0-112">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="daee0-113">Per altre informazioni sull'installazione e sulla distribuzione di **AdventureWorksDW2012**, vedere [Considerazioni per l'installazione di esempi e di database di esempio di SQL Server](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span><span class="sxs-lookup"><span data-stu-id="daee0-113">For more information about how to install and deploy **AdventureWorksDW2012**, see [Considerations for Installing SQL Server Samples and Sample Databases](https://technet.microsoft.com/library/ms161556%28v=sql.105%29).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="daee0-114">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="daee0-114">Lesson Tasks</span></span>  
 <span data-ttu-id="daee0-115">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="daee0-115">This lesson contains the following tasks:</span></span>  
  
1.  [<span data-ttu-id="daee0-116">Passaggio 1: Copia del pacchetto della lezione 5</span><span class="sxs-lookup"><span data-stu-id="daee0-116">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
2.  [<span data-ttu-id="daee0-117">Passaggio 2: Conversione del progetto nel modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="daee0-117">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
3.  [<span data-ttu-id="daee0-118">Passaggio 3: Test del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="daee0-118">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
4.  [<span data-ttu-id="daee0-119">Passaggio 4: Distribuzione del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="daee0-119">Step 4: Deploying the Lesson 6 Package</span></span>](lesson-6-4-deploying-the-lesson-6-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="daee0-120">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="daee0-120">Start the Lesson</span></span>  
 [<span data-ttu-id="daee0-121">Passaggio 1: Copia del pacchetto della lezione 5</span><span class="sxs-lookup"><span data-stu-id="daee0-121">Step 1: Copying the Lesson 5 Package</span></span>](lesson-6-1-copying-the-lesson-5-package.md)  
  
  
