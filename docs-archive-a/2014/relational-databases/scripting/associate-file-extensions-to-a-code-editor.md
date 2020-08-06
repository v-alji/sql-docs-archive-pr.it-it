---
title: Associazione di estensioni di file a un editor di codice
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627170"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="55a83-102">Associazione di estensioni di file a un editor di codice</span><span class="sxs-lookup"><span data-stu-id="55a83-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="55a83-103">L'associazione di estensioni di file a un editor di codice specifico consente di aprire un file con l'editor di codice [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] appropriato quando si fa doppio clic su un file in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="55a83-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="55a83-104">L'associazione delle estensioni utilizzate solitamente da [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ad esempio sql e mdx, viene eseguita durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="55a83-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="55a83-105">È inoltre necessario associare le nuove estensioni di file a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nel file system.</span><span class="sxs-lookup"><span data-stu-id="55a83-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="55a83-106">Questa caratteristica consente di aprire file creati con altri editor oppure di aprire file rinominati, ad esempio copie di backup di file con estensione sql rinominati con estensione bak.</span><span class="sxs-lookup"><span data-stu-id="55a83-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="55a83-107">Il processo è suddiviso in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="55a83-107">There are two steps in the process.</span></span> <span data-ttu-id="55a83-108">È innanzitutto necessario associare l'estensione a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e quindi associare l'estensione a un editor di codice specifico.</span><span class="sxs-lookup"><span data-stu-id="55a83-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="55a83-109">Per associare una nuova estensione di file a SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55a83-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="55a83-110">Fare clic sul pulsante **Start** , scegliere **Tutti i programmi**, **Accessori**e quindi **Esplora risorse**.</span><span class="sxs-lookup"><span data-stu-id="55a83-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="55a83-111">In Esplora risorse scegliere **Opzioni cartella** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="55a83-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="55a83-112">Nella finestra di dialogo **Opzioni cartella** fare clic su **Nuovo** nella scheda **Tipi di file**.</span><span class="sxs-lookup"><span data-stu-id="55a83-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="55a83-113">Nella finestra di dialogo **Creazione nuova estensione** immettere nella casella **Estensione file** la nuova estensione di file da associare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a83-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="55a83-114">Non inserire un punto davanti all'estensione.</span><span class="sxs-lookup"><span data-stu-id="55a83-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="55a83-115">Selezionare la nuova estensione nella casella **Tipi di file registrati** , quindi fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="55a83-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="55a83-116">Nella finestra di dialogo **Apri con** fare clic su **SSMS - SQL Server Management Studio**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a83-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="55a83-117">Fare clic su **Chiudi** per chiudere la finestra di dialogo **Opzioni cartella** , quindi chiudere Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="55a83-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="55a83-118">Per associare una nuova estensione di file a un editor di codice in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55a83-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="55a83-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="55a83-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="55a83-120">Nella finestra di dialogo **Opzioni** fare clic su **Editor di testo**e quindi su **Estensione file**.</span><span class="sxs-lookup"><span data-stu-id="55a83-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="55a83-121">Immettere la nuova estensione di file nella casella **Estensione** .</span><span class="sxs-lookup"><span data-stu-id="55a83-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="55a83-122">Nella casella **Editor** selezionare l'editor di codice da usare per aprire questo tipo di file, fare clic su **Aggiungi**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a83-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55a83-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55a83-123">See Also</span></span>  
 [<span data-ttu-id="55a83-124">Utilità Ssms</span><span class="sxs-lookup"><span data-stu-id="55a83-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
