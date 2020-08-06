---
title: Gestione connessione file | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722940"
---
# <a name="file-connection-manager"></a><span data-ttu-id="26792-102">gestione connessione file</span><span class="sxs-lookup"><span data-stu-id="26792-102">File Connection Manager</span></span>
  <span data-ttu-id="26792-103">Una gestione connessione file consente a un pacchetto di fare riferimento a un file o a una cartella esistente oppure di creare un file o una cartella in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="26792-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="26792-104">Ad esempio, è possibile fare riferimento a un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="26792-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="26792-105">Le informazioni presenti nei file vengono usate da alcuni componenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per eseguire le operazioni.</span><span class="sxs-lookup"><span data-stu-id="26792-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="26792-106">L'attività Esegui SQL può ad esempio fare riferimento a un file che contiene le istruzioni SQL eseguite dall'attività.</span><span class="sxs-lookup"><span data-stu-id="26792-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="26792-107">In altri componenti le operazioni vengono effettuate nei file.</span><span class="sxs-lookup"><span data-stu-id="26792-107">Other components perform operations on files.</span></span> <span data-ttu-id="26792-108">Ad esempio, tramite l'attività File System è possibile fare riferimento a un file per copiarlo in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="26792-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="26792-109">Tipi di utilizzo per la gestione connessione file</span><span class="sxs-lookup"><span data-stu-id="26792-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="26792-110">Tramite la proprietà `FileUsageType` della gestione connessione file viene specificata la modalità di utilizzo della connessione file.</span><span class="sxs-lookup"><span data-stu-id="26792-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="26792-111">La gestione connessione file può creare un file o una cartella oppure utilizzare un file o una cartella esistente.</span><span class="sxs-lookup"><span data-stu-id="26792-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="26792-112">Nella tabella seguente vengono elencati i possibili valori di `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="26792-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="26792-113">valore</span><span class="sxs-lookup"><span data-stu-id="26792-113">Value</span></span>|<span data-ttu-id="26792-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26792-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="26792-115">La gestione connessione file utilizza un file esistente.</span><span class="sxs-lookup"><span data-stu-id="26792-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="26792-116">La gestione connessione file crea un file.</span><span class="sxs-lookup"><span data-stu-id="26792-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="26792-117">La gestione connessione file utilizza una cartella esistente.</span><span class="sxs-lookup"><span data-stu-id="26792-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="26792-118">La gestione connessione file crea una cartella.</span><span class="sxs-lookup"><span data-stu-id="26792-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="26792-119">Connessioni a più file o cartelle</span><span class="sxs-lookup"><span data-stu-id="26792-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="26792-120">La gestione connessione file può fare riferimento solo a un file o a una cartella.</span><span class="sxs-lookup"><span data-stu-id="26792-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="26792-121">Per fare riferimento a più file o cartelle, al posto di una gestione connessione file utilizzare una gestione connessione per più file.</span><span class="sxs-lookup"><span data-stu-id="26792-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="26792-122">Per altre informazioni, vedere [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="26792-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="26792-123">Configurazione della gestione connessione file</span><span class="sxs-lookup"><span data-stu-id="26792-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="26792-124">Quando si aggiunge una gestione connessione file a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione file, imposta le proprietà della connessione file e la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="26792-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="26792-125">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `FILE`.</span><span class="sxs-lookup"><span data-stu-id="26792-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="26792-126">Per configurare una gestione connessione file, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="26792-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="26792-127">Specificare il tipo di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="26792-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="26792-128">Specificare un file o una cartella.</span><span class="sxs-lookup"><span data-stu-id="26792-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="26792-129">È possibile impostare la proprietà ConnectionString per la gestione connessione file specificando un'espressione nella finestra Proprietà di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26792-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="26792-130">Tuttavia, per evitare un errore di convalida quando si usa un'espressione per specificare il file o la cartella, aggiungere il percorso di un file o di una cartella in **Editor gestione connessione file**per **File/Cartella**.</span><span class="sxs-lookup"><span data-stu-id="26792-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="26792-131">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="26792-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="26792-132">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione file](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="26792-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="26792-133">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="26792-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
