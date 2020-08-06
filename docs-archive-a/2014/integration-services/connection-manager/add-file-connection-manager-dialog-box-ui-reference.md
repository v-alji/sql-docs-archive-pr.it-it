---
title: Riferimento all'interfaccia utente della finestra di dialogo Aggiungi gestione connessione file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722948"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="29f25-102">Riferimento all'interfaccia utente della finestra di dialogo Aggiungi gestione connessione file</span><span class="sxs-lookup"><span data-stu-id="29f25-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="29f25-103">Utilizzare la finestra di dialogo **Aggiungi gestione connessione file** per definire una connessione a un gruppo di file o cartelle.</span><span class="sxs-lookup"><span data-stu-id="29f25-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="29f25-104">Per ulteriori informazioni sulla gestione connessione per più file, vedere [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="29f25-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29f25-105">Le attività predefinite e i componenti del flusso di dati in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non utilizzano la gestione connessione per più file.</span><span class="sxs-lookup"><span data-stu-id="29f25-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="29f25-106">È tuttavia possibile utilizzare la gestione connessione nell'attività Script o nel componente di script.</span><span class="sxs-lookup"><span data-stu-id="29f25-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29f25-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="29f25-107">Options</span></span>  
 <span data-ttu-id="29f25-108">**Tipo di utilizzo**</span><span class="sxs-lookup"><span data-stu-id="29f25-108">**Usage type**</span></span>  
 <span data-ttu-id="29f25-109">Consente di specificare il tipo di file da utilizzare per la gestione connessione per più file.</span><span class="sxs-lookup"><span data-stu-id="29f25-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="29f25-110">valore</span><span class="sxs-lookup"><span data-stu-id="29f25-110">Value</span></span>|<span data-ttu-id="29f25-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29f25-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="29f25-112">**Creazione file**</span><span class="sxs-lookup"><span data-stu-id="29f25-112">**Create files**</span></span>|<span data-ttu-id="29f25-113">La gestione connessione creerà i file.</span><span class="sxs-lookup"><span data-stu-id="29f25-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="29f25-114">**File esistenti**</span><span class="sxs-lookup"><span data-stu-id="29f25-114">**Existing files**</span></span>|<span data-ttu-id="29f25-115">La gestione connessione utilizzerà i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="29f25-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="29f25-116">**Creazione cartelle**</span><span class="sxs-lookup"><span data-stu-id="29f25-116">**Create folders**</span></span>|<span data-ttu-id="29f25-117">La gestione connessione creerà le cartelle.</span><span class="sxs-lookup"><span data-stu-id="29f25-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="29f25-118">**Cartelle esistenti**</span><span class="sxs-lookup"><span data-stu-id="29f25-118">**Existing folders**</span></span>|<span data-ttu-id="29f25-119">La gestione connessione utilizzerà le cartelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="29f25-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="29f25-120">**File/Cartelle**</span><span class="sxs-lookup"><span data-stu-id="29f25-120">**Files / Folders**</span></span>  
 <span data-ttu-id="29f25-121">Consente di visualizzare i file o le cartelle aggiunti tramite i pulsanti descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="29f25-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="29f25-122">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="29f25-122">**Add**</span></span>  
 <span data-ttu-id="29f25-123">Consente di aggiungere un file usando la finestra di dialogo **Seleziona file** o di aggiungere una cartella usando la finestra di dialogo **Sfoglia cartella** .</span><span class="sxs-lookup"><span data-stu-id="29f25-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="29f25-124">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="29f25-124">**Edit**</span></span>  
 <span data-ttu-id="29f25-125">Consente di selezionare un file o una cartella e quindi di sostituirli con un file o una cartella differente usando la finestra di dialogo **Seleziona file** o **Sfoglia cartella** .</span><span class="sxs-lookup"><span data-stu-id="29f25-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="29f25-126">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="29f25-126">**Remove**</span></span>  
 <span data-ttu-id="29f25-127">Consente di selezionare un file o una cartella e quindi di rimuoverli dall'elenco usando il pulsante **Rimuovi** .</span><span class="sxs-lookup"><span data-stu-id="29f25-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="29f25-128">**Pulsanti freccia**</span><span class="sxs-lookup"><span data-stu-id="29f25-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="29f25-129">Selezionare un file o una cartella e quindi utilizzare i pulsanti freccia per spostare il file o la cartella verso l'alto o verso il basso in modo da specificare la sequenza di accesso.</span><span class="sxs-lookup"><span data-stu-id="29f25-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f25-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29f25-130">See Also</span></span>  
 [<span data-ttu-id="29f25-131">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="29f25-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
