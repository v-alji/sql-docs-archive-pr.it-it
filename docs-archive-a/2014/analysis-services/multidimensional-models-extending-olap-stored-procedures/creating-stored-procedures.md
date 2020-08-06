---
title: Creazione di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715847"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="d7fea-102">Creazione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="d7fea-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="d7fea-103">Tutte le stored procedure devono essere associate a una classe CLR (Common Language Runtime) o COM (Component Object Model) per poter essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="d7fea-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="d7fea-104">La classe deve essere installata nel server, in genere sotto forma di libreria di [!INCLUDE[msCoName](../../includes/msconame-md.md)] collegamento dinamico (dll) ActiveX® e registrata come assembly nel server o in un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="d7fea-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="d7fea-105">Le stored procedure vengono registrate in un server o in un database.</span><span class="sxs-lookup"><span data-stu-id="d7fea-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="d7fea-106">Le stored procedure del server possono essere chiamate da qualsiasi contesto di query,</span><span class="sxs-lookup"><span data-stu-id="d7fea-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="d7fea-107">mentre le stored procedure di database sono accessibili solo se il contesto del database è il database nel quale è stata definita la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d7fea-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="d7fea-108">Se in un assembly sono presenti funzioni che chiamano funzioni di un assembly diverso, è necessario registrare entrambi gli assembly nello stesso contesto (server o database).</span><span class="sxs-lookup"><span data-stu-id="d7fea-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="d7fea-109">Per un server o un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database distribuito in un server, è possibile usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per registrare un assembly.</span><span class="sxs-lookup"><span data-stu-id="d7fea-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="d7fea-110">Per un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] è possibile utilizzare Progettazione [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per registrare un assembly nel progetto.</span><span class="sxs-lookup"><span data-stu-id="d7fea-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7fea-111">Gli assembly COM potrebbero comportare un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7fea-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="d7fea-112">A causa di tale rischio e di altre considerazioni, gli assembly COM sono stati deprecati in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7fea-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="d7fea-113">e potrebbero non essere supportati nelle versioni future.</span><span class="sxs-lookup"><span data-stu-id="d7fea-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="d7fea-114">Registrazione di un assembly server</span><span class="sxs-lookup"><span data-stu-id="d7fea-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="d7fea-115">In Esplora oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] gli assembly server vengono elencati nella cartella Assembly in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7fea-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d7fea-116">Gli assembly server possono contenere sia assembly .NET (CLR) sia librerie COM.</span><span class="sxs-lookup"><span data-stu-id="d7fea-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="d7fea-117">Per creare un assembly server</span><span class="sxs-lookup"><span data-stu-id="d7fea-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="d7fea-118">Espandere l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Esplora oggetti, fare clic con il pulsante destro del mouse sulla cartella **assembly** , quindi scegliere **nuovo assembly**.</span><span class="sxs-lookup"><span data-stu-id="d7fea-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="d7fea-119">Verrà visualizzata la finestra di dialogo **Registra assembly server** .</span><span class="sxs-lookup"><span data-stu-id="d7fea-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="d7fea-120">Per **tipo** specificare il tipo di assembly:</span><span class="sxs-lookup"><span data-stu-id="d7fea-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="d7fea-121">Per una DLL (CLR) con codice gestito, specificare Assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="d7fea-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="d7fea-122">Per una DLL (COM) con codice nativo, specificare DLL COM.</span><span class="sxs-lookup"><span data-stu-id="d7fea-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="d7fea-123">Per **nome file**specificare la DLL contenente le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d7fea-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="d7fea-124">Per **nome assembly**specificare un nome per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7fea-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="d7fea-125">Se si tratta di una build di debug della libreria da utilizzare per eseguire il debug delle stored procedure, selezionare la casella di controllo **Includi informazioni di debug** .</span><span class="sxs-lookup"><span data-stu-id="d7fea-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="d7fea-126">Per ulteriori informazioni sul debug di stored procedure, vedere [debug di stored procedure](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d7fea-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="d7fea-127">È possibile fare clic su **OK** per registrare l'assembly immediatamente oppure, sulla barra degli strumenti della finestra di dialogo, è possibile fare clic su un comando nel menu **script** per creare uno script per l'azione di registrazione in una finestra di query, in un file o negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="d7fea-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="d7fea-128">Dopo aver registrato un assembly server, è possibile configurarlo facendo clic con il pulsante destro del mouse sull'assembly in Esplora oggetti e quindi scegliendo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d7fea-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="d7fea-129">Registrazione di un assembly database nel server</span><span class="sxs-lookup"><span data-stu-id="d7fea-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="d7fea-130">In Esplora oggetti in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] gli assembly database vengono elencati nella cartella Assembly in un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7fea-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="d7fea-131">Gli assembly database possono contenere sia assembly .NET (CLR) sia librerie COM.</span><span class="sxs-lookup"><span data-stu-id="d7fea-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="d7fea-132">Per creare un assembly database in un server</span><span class="sxs-lookup"><span data-stu-id="d7fea-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="d7fea-133">Espandere l'istanza del [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Esplora oggetti, fare clic con il pulsante destro del mouse sulla cartella **assembly** e quindi scegliere **nuovo assembly**.</span><span class="sxs-lookup"><span data-stu-id="d7fea-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="d7fea-134">Verrà visualizzata la finestra di dialogo **Registra assembly database** .</span><span class="sxs-lookup"><span data-stu-id="d7fea-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="d7fea-135">Per **tipo** specificare il tipo di assembly:</span><span class="sxs-lookup"><span data-stu-id="d7fea-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="d7fea-136">Per una DLL (CLR) con codice gestito, specificare Assembly .NET.</span><span class="sxs-lookup"><span data-stu-id="d7fea-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="d7fea-137">Per una DLL (COM) con codice nativo, specificare DLL COM.</span><span class="sxs-lookup"><span data-stu-id="d7fea-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="d7fea-138">Per **nome file**specificare la DLL contenente le stored procedure.</span><span class="sxs-lookup"><span data-stu-id="d7fea-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="d7fea-139">Per **nome assembly**specificare un nome per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7fea-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="d7fea-140">Se si tratta di una build di debug della libreria da utilizzare per eseguire il debug delle stored procedure, selezionare la casella di controllo **Includi informazioni di debug** .</span><span class="sxs-lookup"><span data-stu-id="d7fea-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="d7fea-141">Per ulteriori informazioni sul debug di stored procedure, vedere [debug di stored procedure](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d7fea-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="d7fea-142">È possibile fare clic su **OK** per registrare l'assembly immediatamente oppure, sulla barra degli strumenti della finestra di dialogo, è possibile fare clic su un comando nel menu **script** per creare uno script per l'azione di registrazione in una finestra di query, in un file o negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="d7fea-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="d7fea-143">Dopo aver registrato un assembly del database, è possibile configurarlo facendo clic con il pulsante destro del mouse sull'assembly in Esplora oggetti e quindi scegliendo **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d7fea-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="d7fea-144">Registrazione di un assembly database in un progetto</span><span class="sxs-lookup"><span data-stu-id="d7fea-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="d7fea-145">In Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] gli assembly database vengono elencati nella cartella Assembly in un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7fea-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="d7fea-146">Gli assembly database possono contenere sia assembly .NET (CLR) sia librerie COM.</span><span class="sxs-lookup"><span data-stu-id="d7fea-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="d7fea-147">Per creare un assembly database in un progetto di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d7fea-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="d7fea-148">Espandere l'istanza del [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Esplora oggetti, fare clic con il pulsante destro del mouse sulla cartella **assembly** e quindi scegliere **nuovo riferimento ad assembly**.</span><span class="sxs-lookup"><span data-stu-id="d7fea-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="d7fea-149">Verrà visualizzata la finestra di dialogo **Aggiungi riferimento** .</span><span class="sxs-lookup"><span data-stu-id="d7fea-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="d7fea-150">Nella scheda **.NET** della finestra di dialogo **Aggiungi riferimento** sono elencati gli assembly .NET (CLR) esistenti, mentre nella scheda **progetti** sono elencati i progetti.</span><span class="sxs-lookup"><span data-stu-id="d7fea-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="d7fea-151">È possibile fare clic su un componente o un progetto esistente e quindi fare clic su **Aggiungi** per aggiungerlo al [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="d7fea-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="d7fea-152">Per aggiungere un riferimento a una DLL COM, fare clic sulla scheda **Sfoglia** per individuare il file.</span><span class="sxs-lookup"><span data-stu-id="d7fea-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="d7fea-153">Nell'elenco **progetti e componenti selezionati** vengono visualizzati il nome, il tipo, la versione e il percorso di ogni componente aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="d7fea-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="d7fea-154">Al termine della selezione dei componenti da aggiungere, fare clic su **OK** per aggiungerli al [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="d7fea-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="d7fea-155">Formatto dello script di un assembly</span><span class="sxs-lookup"><span data-stu-id="d7fea-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="d7fea-156">Registrare un assembly .NET è un'operazione piuttosto semplice.</span><span class="sxs-lookup"><span data-stu-id="d7fea-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="d7fea-157">Per aggiungere un assembly .NET a un database in formato binario è possibile utilizzare il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d7fea-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7fea-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7fea-158">See Also</span></span>  
 <span data-ttu-id="d7fea-159">[Gestione di assembly di modelli multidimensionali](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="d7fea-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="d7fea-160">Definizione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="d7fea-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
