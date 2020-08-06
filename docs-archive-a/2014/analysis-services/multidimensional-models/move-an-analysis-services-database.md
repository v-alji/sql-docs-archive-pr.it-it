---
title: Spostare un database di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724263"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="31d69-102">Spostare un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="31d69-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="31d69-103">Spesso, un amministratore del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] desidera spostare un database multidimensionale o tabulare in un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="31d69-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="31d69-104">Queste situazioni spesso sono determinate da esigenze aziendali, ad esempio lo spostamento del database in un disco diverso per migliorare le prestazioni, la necessità di ottenere più spazio per la crescita del database oppure per aggiornare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="31d69-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="31d69-105">Un database può essere spostato in vari modi.</span><span class="sxs-lookup"><span data-stu-id="31d69-105">A database can be moved in many ways.</span></span> <span data-ttu-id="31d69-106">In questo documento vengono illustrati gli scenari comuni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31d69-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="31d69-107">In modo interattivo tramite SSMS</span><span class="sxs-lookup"><span data-stu-id="31d69-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="31d69-108">A livello di programmazione tramite AMO</span><span class="sxs-lookup"><span data-stu-id="31d69-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="31d69-109">Tramite script utilizzando XMLA</span><span class="sxs-lookup"><span data-stu-id="31d69-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="31d69-110">Tutti gli scenari richiedono all'utente di accedere alla cartella del database e utilizzare un metodo per lo spostamento dei file nella destinazione finale desiderata.</span><span class="sxs-lookup"><span data-stu-id="31d69-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31d69-111">Lo scollegamento di un database senza l'assegnazione di una password lascia il database in uno stato non protetto.</span><span class="sxs-lookup"><span data-stu-id="31d69-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="31d69-112">Si consiglia di assegnare una password al database per proteggere le informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="31d69-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="31d69-113">Inoltre, è necessario applicare la sicurezza dall'accesso corrispondente alla cartella del database, alle sottocartelle e ai file per impedire accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="31d69-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="31d69-114">Procedure</span><span class="sxs-lookup"><span data-stu-id="31d69-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="31d69-115">Spostamento di un database in modo interattivo tramite SSMS</span><span class="sxs-lookup"><span data-stu-id="31d69-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="31d69-116">Individuare il database da spostare nel riquadro sinistro o destro di SSMS.</span><span class="sxs-lookup"><span data-stu-id="31d69-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="31d69-117">Fare clic con il pulsante destro del mouse sul database e selezionare **Disconnetti...**</span><span class="sxs-lookup"><span data-stu-id="31d69-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="31d69-118">Assegnare una password al database da scollegare, quindi fare clic su **OK** per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="31d69-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="31d69-119">Utilizzare un meccanismo del sistema operativo o un metodo standard di spostamento file per spostare la cartella del database nel nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="31d69-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="31d69-120">Individuare la cartella **Database** nel riquadro sinistro o destro di SSMS.</span><span class="sxs-lookup"><span data-stu-id="31d69-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="31d69-121">Fare clic con il pulsante destro del mouse sulla cartella **database** e scegliere **Connetti...**</span><span class="sxs-lookup"><span data-stu-id="31d69-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="31d69-122">Nella casella di testo **cartella** digitare il nuovo percorso della cartella del database.</span><span class="sxs-lookup"><span data-stu-id="31d69-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="31d69-123">In alternativa, è possibile utilizzare il pulsante Sfoglia (**...**) per individuare la cartella del database.</span><span class="sxs-lookup"><span data-stu-id="31d69-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="31d69-124">Consente di selezionare la `ReadWrite` modalità del database.</span><span class="sxs-lookup"><span data-stu-id="31d69-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="31d69-125">Digitare la password usata nel passaggio 3, quindi fare clic su **OK** per eseguire il comando di collegamento.</span><span class="sxs-lookup"><span data-stu-id="31d69-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="31d69-126">Spostamento di un database a livello di programmazione tramite AMO</span><span class="sxs-lookup"><span data-stu-id="31d69-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="31d69-127">Nell'applicazione C# adattare il codice di esempio seguente e completare le attività indicate.</span><span class="sxs-lookup"><span data-stu-id="31d69-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="31d69-128">Nell'applicazione C# richiamare `MoveDb()` con i parametri necessari.</span><span class="sxs-lookup"><span data-stu-id="31d69-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="31d69-129">Compilare ed eseguire il codice per spostare il database.</span><span class="sxs-lookup"><span data-stu-id="31d69-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="31d69-130">Spostamento di un database tramite script utilizzando XMLA</span><span class="sxs-lookup"><span data-stu-id="31d69-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="31d69-131">Aprire una nuova scheda XMLA in SSMS.</span><span class="sxs-lookup"><span data-stu-id="31d69-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="31d69-132">Copiare il modello di script seguente per XMLA:</span><span class="sxs-lookup"><span data-stu-id="31d69-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="31d69-133">Sostituire `%dbName%` con il nome del database e `%password%` con la password.</span><span class="sxs-lookup"><span data-stu-id="31d69-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="31d69-134">I caratteri % fanno parte del modello e devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="31d69-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="31d69-135">Eseguire il comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="31d69-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="31d69-136">Utilizzare un meccanismo del sistema operativo o un metodo standard di spostamento file per spostare la cartella del database nel nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="31d69-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="31d69-137">Copiare il modello di script seguente per XMLA in una nuova scheda XMLA:</span><span class="sxs-lookup"><span data-stu-id="31d69-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="31d69-138">Sostituire `%dbFolder%` con il percorso completo in formato UNC della cartella del database, `%ReadOnlyMode%` con il valore `ReadOnly` o `ReadWrite` corrispondente e `%password%` con la password.</span><span class="sxs-lookup"><span data-stu-id="31d69-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="31d69-139">I caratteri % fanno parte del modello e devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="31d69-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="31d69-140">Eseguire il comando XMLA.</span><span class="sxs-lookup"><span data-stu-id="31d69-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d69-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31d69-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="31d69-142">[Microsoft. AnalysisServices. database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="31d69-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="31d69-143">[Collegamento e scollegamento di Analysis Services database](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="31d69-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="31d69-144">[Percorso di archiviazione del database](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="31d69-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="31d69-145">[Proprietà ReadWriteMode del database](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="31d69-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="31d69-146">[Connetti elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="31d69-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="31d69-147">[Scollega elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="31d69-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="31d69-148">[Elemento ReadWriteMode](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="31d69-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="31d69-149">Elemento DbStorageLocation</span><span class="sxs-lookup"><span data-stu-id="31d69-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
