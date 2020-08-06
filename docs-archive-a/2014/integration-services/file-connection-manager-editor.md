---
title: Editor gestione connessione file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636269"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="d36d1-102">Editor gestione connessione file</span><span class="sxs-lookup"><span data-stu-id="d36d1-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="d36d1-103">Utilizzare la finestra di dialogo **Editor gestione connessione file** per specificare le proprietà utilizzate per la connessione a un file o a una cartella.</span><span class="sxs-lookup"><span data-stu-id="d36d1-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d36d1-104">È possibile impostare la proprietà ConnectionString per la gestione connessione file specificando un'espressione nella finestra Proprietà di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d36d1-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d36d1-105">Tuttavia, per evitare un errore di convalida quando si usa un'espressione per specificare il file o la cartella, aggiungere il percorso di un file o di una cartella in **Editor gestione connessione file**per **File/Cartella**.</span><span class="sxs-lookup"><span data-stu-id="d36d1-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="d36d1-106">Per ulteriori informazioni sulla gestione connessione file, vedere [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d36d1-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d36d1-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d36d1-107">Options</span></span>  
 <span data-ttu-id="d36d1-108">**Tipo di utilizzo**</span><span class="sxs-lookup"><span data-stu-id="d36d1-108">**Usage Type**</span></span>  
 <span data-ttu-id="d36d1-109">Consente di specificare se **Gestione connessione file flat** deve connettersi a un file o a una cartella esistente o creare un nuovo file o cartella.</span><span class="sxs-lookup"><span data-stu-id="d36d1-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="d36d1-110">Valore</span><span class="sxs-lookup"><span data-stu-id="d36d1-110">Value</span></span>|<span data-ttu-id="d36d1-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d36d1-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d36d1-112">Crea file</span><span class="sxs-lookup"><span data-stu-id="d36d1-112">Create file</span></span>|<span data-ttu-id="d36d1-113">Consente di creare un nuovo file in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d36d1-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="d36d1-114">File esistente</span><span class="sxs-lookup"><span data-stu-id="d36d1-114">Existing file</span></span>|<span data-ttu-id="d36d1-115">Consente di utilizzare un file esistente.</span><span class="sxs-lookup"><span data-stu-id="d36d1-115">Use an existing file.</span></span>|  
|<span data-ttu-id="d36d1-116">Creazione cartella</span><span class="sxs-lookup"><span data-stu-id="d36d1-116">Create folder</span></span>|<span data-ttu-id="d36d1-117">Consente di creare una nuova cartella in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d36d1-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="d36d1-118">Cartella esistente</span><span class="sxs-lookup"><span data-stu-id="d36d1-118">Existing folder</span></span>|<span data-ttu-id="d36d1-119">Consente di utilizzare una cartella esistente.</span><span class="sxs-lookup"><span data-stu-id="d36d1-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="d36d1-120">**File/Cartella**</span><span class="sxs-lookup"><span data-stu-id="d36d1-120">**File / Folder**</span></span>  
 <span data-ttu-id="d36d1-121">Se si sceglie **File**, specificare il file da usare.</span><span class="sxs-lookup"><span data-stu-id="d36d1-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="d36d1-122">Se si sceglie **Cartella**, specificare la cartella da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d36d1-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="d36d1-123">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="d36d1-123">**Browse**</span></span>  
 <span data-ttu-id="d36d1-124">Selezionare il file o la cartella usando la finestra di dialogo **Seleziona file** o **Sfoglia cartella** .</span><span class="sxs-lookup"><span data-stu-id="d36d1-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36d1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d36d1-125">See Also</span></span>  
 [<span data-ttu-id="d36d1-126">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="d36d1-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
