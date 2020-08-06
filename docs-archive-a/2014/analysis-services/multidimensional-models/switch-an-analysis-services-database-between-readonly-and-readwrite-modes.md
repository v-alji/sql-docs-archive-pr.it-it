---
title: Passare un database Analysis Services tra le modalità ReadOnly e ReadWrite | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711071"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="a0671-102">Passare un database di Analysis Services tra le modalità ReadOnly e ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a0671-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="a0671-103">In alcune situazioni frequenti, un amministratore del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] potrebbe voler modificare la modalità lettura/scrittura di un database tabulare o multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="a0671-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="a0671-104">Queste situazioni sono spesso determinate da esigenze aziendali, ad esempio la condivisione del database tra un pool di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Server per una migliore esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="a0671-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="a0671-105">In un database è possibile passare da una modalità all'altra in vari modi.</span><span class="sxs-lookup"><span data-stu-id="a0671-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="a0671-106">In questo documento vengono illustrati gli scenari comuni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0671-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="a0671-107">In modo interattivo tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0671-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="a0671-108">A livello di programmazione tramite AMO</span><span class="sxs-lookup"><span data-stu-id="a0671-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="a0671-109">Tramite script utilizzando XMLA</span><span class="sxs-lookup"><span data-stu-id="a0671-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a0671-110">Procedure</span><span class="sxs-lookup"><span data-stu-id="a0671-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="a0671-111">Per attivare la modalità lettura/scrittura di un database in modo interattivo tramite Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0671-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="a0671-112">Individuare il database di cui cambiare la modalità nel riquadro sinistro o destro di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0671-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="a0671-113">Fare clic con il pulsante destro del mouse sul database e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0671-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="a0671-114">Individuare la cartella del database e prendere nota del percorso.</span><span class="sxs-lookup"><span data-stu-id="a0671-114">Find the database folder and note the location.</span></span> <span data-ttu-id="a0671-115">Un percorso di archiviazione del database vuoto indica che la cartella del database si trova nella cartella di dati del server.</span><span class="sxs-lookup"><span data-stu-id="a0671-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a0671-116">Non appena il database viene scollegato, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] non consente più di ottenerne il percorso.</span><span class="sxs-lookup"><span data-stu-id="a0671-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="a0671-117">Fare clic con il pulsante destro del mouse sul database e scegliere **Disconnetti.**</span><span class="sxs-lookup"><span data-stu-id="a0671-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="a0671-118">Assegnare una password al database da scollegare, quindi fare clic su **OK** per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="a0671-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="a0671-119">Individuare la cartella **database** nel riquadro sinistro o destro di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0671-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="a0671-120">Fare clic con il pulsante destro del mouse sulla cartella **database** e scegliere **Connetti...**</span><span class="sxs-lookup"><span data-stu-id="a0671-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="a0671-121">Nella casella di testo **cartella** digitare il percorso originale della cartella del database.</span><span class="sxs-lookup"><span data-stu-id="a0671-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="a0671-122">In alternativa, è possibile utilizzare il pulsante Sfoglia (**...**) per individuare la cartella del database.</span><span class="sxs-lookup"><span data-stu-id="a0671-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="a0671-123">Selezionare la modalità di lettura/scrittura per il database.</span><span class="sxs-lookup"><span data-stu-id="a0671-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="a0671-124">Digitare la password usata nel passaggio 3 e fare clic su **OK** per eseguire il comando di connessione.</span><span class="sxs-lookup"><span data-stu-id="a0671-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="a0671-125">Per attivare la modalità lettura/scrittura di un database a livello di programmazione tramite AMO</span><span class="sxs-lookup"><span data-stu-id="a0671-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="a0671-126">Nell'applicazione C# adattare il codice di esempio seguente e completare le attività indicate.</span><span class="sxs-lookup"><span data-stu-id="a0671-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="a0671-127">Nell'applicazione C# richiamare `SwitchReadWrite()` con i parametri necessari.</span><span class="sxs-lookup"><span data-stu-id="a0671-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="a0671-128">Compilare ed eseguire il codice per spostare il database.</span><span class="sxs-lookup"><span data-stu-id="a0671-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="a0671-129">Per attivare la modalità lettura/scrittura di un database tramite script utilizzando XMLA</span><span class="sxs-lookup"><span data-stu-id="a0671-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="a0671-130">Individuare il database di cui cambiare la modalità nel riquadro sinistro o destro di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0671-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="a0671-131">Fare clic con il pulsante destro del mouse sul database e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0671-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="a0671-132">Individuare la cartella del database e prendere nota del percorso.</span><span class="sxs-lookup"><span data-stu-id="a0671-132">Find the database folder and note the location.</span></span> <span data-ttu-id="a0671-133">Un percorso di archiviazione del database vuoto indica che la cartella del database si trova nella cartella di dati del server.</span><span class="sxs-lookup"><span data-stu-id="a0671-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a0671-134">Non appena il database viene scollegato, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] non consente più di ottenerne il percorso.</span><span class="sxs-lookup"><span data-stu-id="a0671-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="a0671-135">Aprire una nuova scheda XMLA in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0671-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="a0671-136">Copiare il modello di script seguente per XMLA:</span><span class="sxs-lookup"><span data-stu-id="a0671-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="a0671-137">Sostituire `%dbName%` con il nome del database e `%password%` con la password.</span><span class="sxs-lookup"><span data-stu-id="a0671-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="a0671-138">I caratteri % fanno parte del modello e devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="a0671-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="a0671-139">Eseguire il comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="a0671-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="a0671-140">Copiare il modello di script seguente per XMLA in una nuova scheda XMLA:</span><span class="sxs-lookup"><span data-stu-id="a0671-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="a0671-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="a0671-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="a0671-142">Sostituire `%dbFolder%` con il percorso completo in formato UNC della cartella del database, `%ReadOnlyMode%` con il valore `ReadOnly` o `ReadWrite` corrispondente e `%password%` con la password.</span><span class="sxs-lookup"><span data-stu-id="a0671-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="a0671-143">I caratteri % fanno parte del modello e devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="a0671-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="a0671-144">Eseguire il comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="a0671-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0671-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0671-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="a0671-146">[Microsoft. AnalysisServices. database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="a0671-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="a0671-147">[Collegamento e scollegamento di Analysis Services database](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a0671-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="a0671-148">[Percorso di archiviazione del database](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="a0671-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="a0671-149">[Proprietà ReadWriteMode del database](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="a0671-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="a0671-150">[Connetti elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="a0671-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="a0671-151">[Scollega elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="a0671-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="a0671-152">[Elemento ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="a0671-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="a0671-153">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="a0671-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
