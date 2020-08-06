---
title: 'Passaggio 3: Modifica del valore di configurazione della proprietà Directory | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ba2a091f-361c-4331-afe2-53b465164c36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a71a7a181322d60caca98da4ddf3261cbce99c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626139"
---
# <a name="step-3-modifying-the-directory-property-configuration-value"></a><span data-ttu-id="9cc42-102">Passaggio 3: Modifica del valore di configurazione della proprietà Directory</span><span class="sxs-lookup"><span data-stu-id="9cc42-102">Step 3: Modifying the Directory Property Configuration Value</span></span>
  <span data-ttu-id="9cc42-103">In questa attività verrà modificata l'impostazione di configurazione archiviata nel file SSISTutorial.dtsConfig relativa alla proprietà Value della variabile a livello di pacchetto `User::varFolderName`.</span><span class="sxs-lookup"><span data-stu-id="9cc42-103">In this task, you will modify the configuration setting, stored in the SSISTutorial.dtsConfig file, for the Value property of the package-level variable `User::varFolderName`.</span></span> <span data-ttu-id="9cc42-104">Tale variabile aggiorna la proprietà Directory del contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="9cc42-104">The variable updates the Directory property of the Foreach Loop container.</span></span> <span data-ttu-id="9cc42-105">Il valore modificato punterà alla `New Sample Data` cartella creata nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="9cc42-105">The modified value will point to the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="9cc42-106">Dopo la modifica dell'impostazione di configurazione e l'esecuzione del pacchetto, la proprietà Directory viene aggiornata dalla variabile, usando il valore popolato dal file di configurazione anziché il valore della directory configurato in origine nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9cc42-106">After you modify the configuration setting and run the package, the Directory property will be updated by the variable, using the value populated from the configuration file instead of the directory value originally configured in the package.</span></span>  
  
### <a name="to-modify-the-configuration-setting-of-the-directory-property"></a><span data-ttu-id="9cc42-107">Per modificare l'impostazione di configurazione della proprietà Directory</span><span class="sxs-lookup"><span data-stu-id="9cc42-107">To modify the configuration setting of the Directory property</span></span>  
  
1.  <span data-ttu-id="9cc42-108">In Blocco note o in un altro editor di testo, individuare ed aprire il file di configurazione SSISTutorial.dtsConfig creato nell'attività precedente utilizzando Configurazione guidata pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9cc42-108">In Notepad or any other text editor, locate and open the SSISTutorial.dtsConfig configuration file that you created by using the Package Configuration Wizard in the previous task.</span></span>  
  
2.  <span data-ttu-id="9cc42-109">Modificare il valore dell'elemento **ConfiguredValue** in modo che corrisponda al percorso della `New Sample Data` cartella creata nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="9cc42-109">Change the value of the **ConfiguredValue** element to match the path of the `New Sample Data` folder that you created in the previous task.</span></span> <span data-ttu-id="9cc42-110">Non racchiudere il percorso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="9cc42-110">Do not surround the path in quotes.</span></span> <span data-ttu-id="9cc42-111">Se la `New Sample Data` cartella si trova al livello radice dell'unità (ad esempio, C: \\ ), il codice XML aggiornato dovrebbe essere simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9cc42-111">If the `New Sample Data` folder is at the root level of your drive (for example, C:\\), the updated XML should be similar to the following sample:</span></span>  
  
     `<?xml version="1.0"?><DTSConfiguration><DTSConfigurationHeading><DTSConfigurationFileInfo GeneratedBy="DOMAIN\UserName" GeneratedFromPackageName="Lesson 5" GeneratedFromPackageID="{F4475E73-59E3-478F-8EB2-B10AFA61D3FA}" GeneratedDate="6/10/2012 8:16:50 AM"/></DTSConfigurationHeading><Configuration ConfiguredType="Property" Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"><ConfiguredValue></ConfiguredValue></Configuration></DTSConfiguration>`  
  
     <span data-ttu-id="9cc42-112">Naturalmente, le informazioni sull'intestazione,, `GeneratedBy` `GeneratedFromPackageID` e **GeneratedDate** saranno diverse nel file.</span><span class="sxs-lookup"><span data-stu-id="9cc42-112">The heading information, `GeneratedBy`, `GeneratedFromPackageID`, and **GeneratedDate** will be different in your file, of course.</span></span> <span data-ttu-id="9cc42-113">L'elemento da esaminare è `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="9cc42-113">The element to note is the `Configuration` element.</span></span> <span data-ttu-id="9cc42-114">La proprietà `Value` della variabile `User::varFolderName` contiene ora C:\New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="9cc42-114">The `Value` property of the variable, `User::varFolderName`, now contains C:\New Sample Data.</span></span>  
  
3.  <span data-ttu-id="9cc42-115">Salvare le modifiche e chiudere l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="9cc42-115">Save the change, and then close the text editor.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9cc42-116">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="9cc42-116">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9cc42-117">Passaggio 4: Test del pacchetto creato nell'esercitazione della lezione 5</span><span class="sxs-lookup"><span data-stu-id="9cc42-117">Step 4: Testing the Lesson 5 Tutorial Package</span></span>](../integration-services/lesson-5-4-testing-the-lesson-5-tutorial-package.md)  
  
  
