---
title: Generare script
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637229"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="5489a-102">Generazione di script (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5489a-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5489a-103">fornisce due meccanismi per la generazione di script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5489a-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="5489a-104">È possibile creare script per più oggetti utilizzando la **procedura guidata genera e pubblica script.**</span><span class="sxs-lookup"><span data-stu-id="5489a-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="5489a-105">È anche possibile generare uno script per un singolo oggetto o per più oggetti usando il menu **Crea script per** in **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="5489a-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="5489a-106">**Scegliere un metodo:**  [Procedura guidata Genera e pubblica script](#GenPubScriptWiz), [Menu Crea script per in Esplora oggetti](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="5489a-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="5489a-107">**Per usare il menu Crea script per:**  [Creare uno script per un solo oggetto](#ScriptSingleObject), [Creare uno script per due oggetti con Esplora oggetti](#ScriptTwoObjectsOE), [Creare uno script per due oggetti usando Dettagli esplora oggetti](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="5489a-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="5489a-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5489a-108">Before You Begin</span></span>  
 <span data-ttu-id="5489a-109">Scegliere il meccanismo che soddisfa maggiormente i requisiti.</span><span class="sxs-lookup"><span data-stu-id="5489a-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="5489a-110">Procedura guidata Genera e pubblica script</span><span class="sxs-lookup"><span data-stu-id="5489a-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="5489a-111">Usare la **Procedura guidata Genera e pubblica script** per creare uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] per molti oggetti.</span><span class="sxs-lookup"><span data-stu-id="5489a-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="5489a-112">Durante la procedura guidata viene generato uno script di tutti gli oggetti contenuti in un database o un subset degli oggetti selezionati.</span><span class="sxs-lookup"><span data-stu-id="5489a-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="5489a-113">La procedura guidata dispone di numerose opzioni per gli script, che consentono ad esempio di includere autorizzazioni, regole di confronto, vincoli e così via.</span><span class="sxs-lookup"><span data-stu-id="5489a-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="5489a-114">Per istruzioni sull'uso della procedura guidata, vedere [Genera e pubblica script](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5489a-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="5489a-115">Menu Crea script per in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="5489a-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="5489a-116">Il menu **Crea script per in Esplora oggetti** consente di creare uno script per un solo oggetto, più oggetti o più istruzioni per un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="5489a-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="5489a-117">È possibile scegliere tra diversi tipi di script, per ad esempio creare, modificare o eliminare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5489a-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="5489a-118">È possibile salvare lo script in una finestra dell'editor di query, in un file o negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="5489a-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="5489a-119">Lo script viene creato in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="5489a-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="5489a-120">Per generare uno script per un singolo oggetto</span><span class="sxs-lookup"><span data-stu-id="5489a-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="5489a-121">**Per generare uno script per un singolo oggetto**</span><span class="sxs-lookup"><span data-stu-id="5489a-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="5489a-122">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="5489a-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5489a-123">Espandere **Database**, quindi espandere il database che contiene l'oggetto per cui creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="5489a-124">Espandere la categoria dell'oggetto:</span><span class="sxs-lookup"><span data-stu-id="5489a-124">Expand the category of the object.</span></span> <span data-ttu-id="5489a-125">ad esempio il nodo **Tabelle** o **Viste** .</span><span class="sxs-lookup"><span data-stu-id="5489a-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="5489a-126">Fare clic con il pulsante destro del mouse sull'oggetto, scegliere Crea **script \<object type> come**, ad esempio, scegliere Crea **script per tabella**.</span><span class="sxs-lookup"><span data-stu-id="5489a-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="5489a-127">Scegliere il tipo di script, ad esempio **Genera codice per istruzione CREATE** o **Genera codice per istruzione ALTER**.</span><span class="sxs-lookup"><span data-stu-id="5489a-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="5489a-128">Selezionare il percorso in cui salvare lo script, ad esempio **Nuova finestra editor di query** o **Appunti**.</span><span class="sxs-lookup"><span data-stu-id="5489a-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a><span data-ttu-id="5489a-129">Per generare uno script di due oggetti usando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="5489a-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="5489a-130">**Per generare uno script per due oggetti tramite Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="5489a-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="5489a-131">Talvolta può essere necessario creare uno script con più opzioni, ad esempio per eliminare una procedura e successivamente crearne un'altra o per creare e quindi modificare una tabella.</span><span class="sxs-lookup"><span data-stu-id="5489a-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="5489a-132">I processi riportati di seguito per la generazione di script di più oggetti, possono essere utilizzato anche quando è necessario creare uno script che fa riferimento a tipi diversi di oggetti, quali tabelle, viste e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="5489a-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="5489a-133">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="5489a-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5489a-134">Espandere **Database**, quindi espandere il database che contiene gli oggetti per cui creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="5489a-135">Fare clic con il pulsante destro del mouse sul primo oggetto per cui creare lo script, scegliere Crea \*\*script \<object type> \*\*per e nelle selezioni **Salva con nome** scegliere **nuova finestra Editor di query** come destinazione dell'output.</span><span class="sxs-lookup"><span data-stu-id="5489a-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="5489a-136">Passare al secondo oggetto per cui si desidera creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="5489a-137">Fare clic con il pulsante destro del mouse sull'oggetto, scegliere Crea \*\*script \<object type> \*\*per e nelle selezioni **Salva con nome** scegliere **Appunti** come destinazione dell'output.</span><span class="sxs-lookup"><span data-stu-id="5489a-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="5489a-138">Nella finestra dell'editor di query aperta per il primo oggetto incollare lo script per il secondo oggetto dagli Appunti.</span><span class="sxs-lookup"><span data-stu-id="5489a-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a><span data-ttu-id="5489a-139">Per generare uno script di due oggetti usando Esplora oggetti dettagli</span><span class="sxs-lookup"><span data-stu-id="5489a-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="5489a-140">**Per generare uno script per due oggetti tramite Dettagli Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="5489a-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="5489a-141">È possibile usare il riquadro **Dettagli Esplora oggetti** per generare uno script per più oggetti della stessa categoria.</span><span class="sxs-lookup"><span data-stu-id="5489a-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="5489a-142">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="5489a-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5489a-143">Espandere **Database**, quindi espandere il database che contiene gli oggetti per cui creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="5489a-144">Espandere il nodo della categoria dei tipi di oggetto per cui si vuole creare uno script, ad esempio il nodo **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="5489a-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="5489a-145">Aprire il riquadro **Dettagli Esplora oggetti** premendo il tasto **F7**oppure selezionando **Dettagli Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="5489a-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="5489a-146">Fare clic su uno degli oggetti per cui si desidera creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="5489a-147">Tenendo premuto il tasto Crtl fare clic sul secondo oggetto per cui si desidera creare lo script.</span><span class="sxs-lookup"><span data-stu-id="5489a-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="5489a-148">Fare clic con il pulsante destro del mouse su uno degli oggetti selezionati e scegliere Crea **script \<object type> come**.</span><span class="sxs-lookup"><span data-stu-id="5489a-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
