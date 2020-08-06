---
title: Debug di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715843"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="d1238-102">Debug di stored procedure</span><span class="sxs-lookup"><span data-stu-id="d1238-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="d1238-103">Le stored procedure di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in realtà sono librerie CLR o COM, in genere DLL, scritte in C# o qualsiasi altro linguaggio CLR o COM.</span><span class="sxs-lookup"><span data-stu-id="d1238-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="d1238-104">Pertanto, il debug di una stored procedure è molto simile al debug di qualsiasi altra applicazione nell'ambiente di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1238-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="d1238-105">Per eseguire il debug di una stored procedure nell'ambiente di sviluppo di Visual Studio vengono utilizzate le funzioni di debug integrate,</span><span class="sxs-lookup"><span data-stu-id="d1238-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="d1238-106">che consentono di arrestare l'esecuzione in corrispondenza delle posizioni delle procedure, controllare la memoria e registrare valori, modificare variabili, osservare i messaggi visualizzati e analizzare in dettaglio il funzionamento del codice.</span><span class="sxs-lookup"><span data-stu-id="d1238-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="d1238-107">Per eseguire il debug di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="d1238-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="d1238-108">Aprire il progetto utilizzato per creare la DLL in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d1238-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d1238-109">Impostare punti di interruzione nel metodo o nella funzione corrispondente alla procedura di cui si desidera eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="d1238-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="d1238-110">Utilizzare Visual Studio per creare una build di debug di una DLL di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d1238-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="d1238-111">Distribuire la DLL nel server.</span><span class="sxs-lookup"><span data-stu-id="d1238-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="d1238-112">Per ulteriori informazioni sulla distribuzione della DLL nel server, vedere [creazione di stored procedure](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d1238-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="d1238-113">La stored procedure di cui si desidera eseguire il debug deve essere chiamata da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1238-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="d1238-114">Se non esiste un'applicazione utilizzabile a tale scopo, è possibile utilizzare l'Editor di query MDX in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per creare una query MDX che chiami la stored procedure desiderata.</span><span class="sxs-lookup"><span data-stu-id="d1238-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="d1238-115">In Visual Studio connettersi al processo di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (Msmdsrv.exe).</span><span class="sxs-lookup"><span data-stu-id="d1238-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="d1238-116">Scegliere **Connetti toProcess**dal menu **debug** .</span><span class="sxs-lookup"><span data-stu-id="d1238-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="d1238-117">Nella finestra di dialogo **Connetti toProcess** selezionare **Mostra i processi di tutti gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="d1238-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="d1238-118">Nell'elenco **processi disponibili** , nella colonna **processo** , fare clic su **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="d1238-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="d1238-119">Se le istanze di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in esecuzione nel server sono più di una, è necessario identificare il processo specificando l'ID dell'istanza che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d1238-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="d1238-120">Nella casella **di testo Connetti a** verificare che sia selezionato il tipo di programma appropriato.</span><span class="sxs-lookup"><span data-stu-id="d1238-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="d1238-121">Per una DLL CLR, fare clic su **Seleziona**, quindi su **Esegui il debug di questi tipi di codice**, quindi su **gestito**e infine su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1238-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="d1238-122">Per una DLL COM, fare clic su **Seleziona**, quindi su **Esegui il debug di questi tipi di codice**, quindi su **nativo**e infine su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1238-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="d1238-123">Scegliere **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="d1238-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="d1238-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] richiamare il programma o lo script MDX che chiama la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d1238-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="d1238-125">Il debugger interrompe l'esecuzione quando raggiunge una riga contenente un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d1238-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="d1238-126">È possibile valutare variabili nella finestra Espressione di controllo, visualizzare variabili locali ed eseguire il codice un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="d1238-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="d1238-127">In caso di problemi durante il debug di una libreria, verificare che il file del database di programma (PDB) corrispondente sia stato copiato nel percorso di distribuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="d1238-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="d1238-128">Se questo file non è stato copiato durante la registrazione o la distribuzione, è necessario copiarlo manualmente nello stesso percorso della DLL.</span><span class="sxs-lookup"><span data-stu-id="d1238-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="d1238-129">Per il codice nativo (DLL COM), il file PDB si trova nella sottodirectory \debug.</span><span class="sxs-lookup"><span data-stu-id="d1238-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="d1238-130">Per il codice gestito (DLL CLR), si trova nella sottodirectory \WINDEBUG.</span><span class="sxs-lookup"><span data-stu-id="d1238-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1238-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1238-131">See Also</span></span>  
 <span data-ttu-id="d1238-132">[Gestione di assembly di modelli multidimensionali](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="d1238-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="d1238-133">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="d1238-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
