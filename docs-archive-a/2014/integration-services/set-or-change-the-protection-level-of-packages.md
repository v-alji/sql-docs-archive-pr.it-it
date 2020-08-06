---
title: Impostare o modificare il livello di protezione dei pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724807"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="04a48-102">Impostazione o modifica del livello di protezione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="04a48-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="04a48-103">Per controllare l'accesso al contenuto dei pacchetti e ai valori sensibili contenuti, ad esempio password, impostare il valore della proprietà `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="04a48-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="04a48-104">Per poter compilare il progetto, ai pacchetti contenuti in un progetto deve essere assegnato lo stesso livello di protezione del progetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="04a48-105">Se si modifica l'impostazione della proprietà `ProtectionLevel` nel progetto, è necessario aggiornare manualmente l'impostazione delle proprietà per i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="04a48-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="04a48-106">Per informazioni su come determinare le `ProtectionLevel` impostazioni appropriate per i pacchetti in fasi diverse del ciclo di vita del pacchetto, vedere [controllo di accesso per dati sensibili nei pacchetti](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="04a48-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="04a48-107">Per informazioni generali sulle funzionalità di sicurezza in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], vedere [Panoramica della sicurezza &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="04a48-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="04a48-108">Le procedure presenti in questo argomento descrivono come utilizzare [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] o l'utilità della riga di comando dtutil per modificare la proprietà `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="04a48-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04a48-109">Oltre alle procedure di questo argomento, è in genere possibile impostare o modificare la proprietà `ProtectionLevel` di un pacchetto quando si importa o esporta il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="04a48-110">È inoltre possibile modificare la proprietà [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] di un pacchetto quando si utilizza l'importazione e l'esportazione guidata di `ProtectionLevel` per salvare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="04a48-111">Per impostare o modificare il livello di protezione di un pacchetto in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="04a48-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="04a48-112">Esaminare i valori disponibili per la `ProtectionLevel` proprietà nell'argomento [impostazione del livello di protezione dei pacchetti](security/access-control-for-sensitive-data-in-packages.md)e determinare il valore appropriato per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="04a48-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="04a48-114">Aprire il pacchetto nella finestra di progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04a48-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="04a48-115">Se nella finestra Proprietà non sono riportate le proprietà del pacchetto, fare clic sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="04a48-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="04a48-116">Nella Finestra Proprietà, nel gruppo di **sicurezza** , selezionare il valore appropriato per la `ProtectionLevel` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="04a48-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="04a48-117">Se si seleziona un livello di protezione che richiede una password, immettere la password come valore della proprietà **PackagePassword** .</span><span class="sxs-lookup"><span data-stu-id="04a48-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="04a48-118">Per salvare il pacchetto modificato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="04a48-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="04a48-119">Per impostare o modificare il livello di protezione dei pacchetti dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="04a48-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="04a48-120">Esaminare i valori disponibili per la `ProtectionLevel` proprietà nell'argomento [impostazione del livello di protezione dei pacchetti](security/access-control-for-sensitive-data-in-packages.md)e determinare il valore appropriato per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04a48-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="04a48-121">Esaminare i mapping per l' `Encrypt` opzione nell'argomento [Utilità dtutil](dtutil-utility.md)e determinare l'intero appropriato da utilizzare come valore della `ProtectionLevel` proprietà selezionata.</span><span class="sxs-lookup"><span data-stu-id="04a48-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="04a48-122">Aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="04a48-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="04a48-123">Al prompt dei comandi, passare alla cartella contenente il pacchetto o i pacchetti per cui si desidera impostare la proprietà `ProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="04a48-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="04a48-124">Negli esempi di sintassi illustrati nel passaggio seguente si presuppone che questa cartella sia la cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="04a48-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="04a48-125">Impostare o modificare il livello di protezione del pacchetto o dei pacchetti utilizzando un comando simile a quello degli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="04a48-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="04a48-126">Il comando seguente imposta la proprietà `ProtectionLevel` di un pacchetto singolo nel file system sul livello 2, "Crittografa tutti i dati sensibili con una password", con la password "strongpassword":</span><span class="sxs-lookup"><span data-stu-id="04a48-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="04a48-127">Il comando seguente imposta la proprietà `ProtectionLevel` di tutti i pacchetti in una particolare cartella nel file system sul livello 2, "Crittografa tutti i dati sensibili con una password", con la password "strongpassword":</span><span class="sxs-lookup"><span data-stu-id="04a48-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="04a48-128">Se si utilizza un comando simile in un file batch, immettere il segnaposto del file "% f" come "%% f" nel file batch.</span><span class="sxs-lookup"><span data-stu-id="04a48-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a48-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04a48-129">See Also</span></span>  
 [<span data-ttu-id="04a48-130">Utilità dtutil</span><span class="sxs-lookup"><span data-stu-id="04a48-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
