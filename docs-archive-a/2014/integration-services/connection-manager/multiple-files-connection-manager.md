---
title: Gestione connessione per più file | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636347"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="0b6e0-102">gestione connessione per più file</span><span class="sxs-lookup"><span data-stu-id="0b6e0-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="0b6e0-103">Una gestione connessione per più file consente a un pacchetto di fare riferimento a file e cartelle esistenti o di creare file e cartelle in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b6e0-104">Le attività predefinite e i componenti del flusso di dati in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non utilizzano la gestione connessione per più file.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="0b6e0-105">È tuttavia possibile utilizzare la gestione connessione nell'attività Script o nel componente di script.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="0b6e0-106">Per informazioni sull'uso delle gestioni connessioni nell'attività Script, vedere [Connessione a origini dati nell'attività Script](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="0b6e0-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="0b6e0-107">Per informazioni sull'utilizzo delle gestioni connessioni nel componente script, vedere [connessione a origini dati nel componente script] (.. /extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="0b6e0-108">Tipi di utilizzo per la gestione connessione per più file</span><span class="sxs-lookup"><span data-stu-id="0b6e0-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="0b6e0-109">La proprietà `FileUsageType` della gestione connessione per più file specifica la modalità di utilizzo della connessione.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="0b6e0-110">La gestione connessione per più file consente sia di creare file e cartelle, sia di utilizzare file e cartelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="0b6e0-111">Nella tabella seguente vengono elencati i possibili valori di `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="0b6e0-112">valore</span><span class="sxs-lookup"><span data-stu-id="0b6e0-112">Value</span></span>|<span data-ttu-id="0b6e0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b6e0-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0b6e0-114">**0**</span><span class="sxs-lookup"><span data-stu-id="0b6e0-114">**0**</span></span>|<span data-ttu-id="0b6e0-115">La gestione connessione per più file utilizza un file esistente.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="0b6e0-116">**1**</span><span class="sxs-lookup"><span data-stu-id="0b6e0-116">**1**</span></span>|<span data-ttu-id="0b6e0-117">La gestione connessione per più file crea un file.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="0b6e0-118">**2**</span><span class="sxs-lookup"><span data-stu-id="0b6e0-118">**2**</span></span>|<span data-ttu-id="0b6e0-119">La gestione connessione per più file utilizza una cartella esistente.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="0b6e0-120">**3**</span><span class="sxs-lookup"><span data-stu-id="0b6e0-120">**3**</span></span>|<span data-ttu-id="0b6e0-121">La gestione connessione per più file crea una cartella.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="0b6e0-122">Configurazione della gestione connessione per più file</span><span class="sxs-lookup"><span data-stu-id="0b6e0-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="0b6e0-123">Quando si aggiunge una gestione connessione per più file a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione per più file, imposta le proprietà di tale connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="0b6e0-124">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `MULTIFILE`.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="0b6e0-125">Per configurare una gestione connessione per più file, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0b6e0-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="0b6e0-126">Specificare il tipo di utilizzo di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="0b6e0-127">Specificare file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="0b6e0-128">Se si utilizzano più file e cartelle, specificare l'ordine con cui accedere a tali elementi.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="0b6e0-129">Se la gestione connessione per più file fa riferimento a più file e cartelle, i percorsi dei file e delle cartelle sono separati da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="0b6e0-130">La proprietà `ConnectionString` della gestione connessione ha il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="0b6e0-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="0b6e0-131">Per specificare più file o cartelle è inoltre possibile utilizzare caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="0b6e0-132">Ad esempio, per fare riferimento a tutti i file di testo sull'unità C, il valore della `ConnectionString` proprietà può essere impostato su C: \\ \*. txt.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="0b6e0-133">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0b6e0-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0b6e0-134">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Riferimento all'interfaccia utente della finestra di dialogo Aggiungi gestione connessione file](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0b6e0-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="0b6e0-135">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0b6e0-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
