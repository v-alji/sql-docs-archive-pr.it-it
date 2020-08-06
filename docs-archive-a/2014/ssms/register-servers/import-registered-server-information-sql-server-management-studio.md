---
title: Importare informazioni relative ai server registrati
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722164"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="df22c-102">Importazione di informazioni relative a server registrati (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="df22c-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="df22c-103">In questo argomento viene illustrato come importare le informazioni sul server registrato salvate in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df22c-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="df22c-104">L'esportazione e la successiva importazione dei file dei server registrati consente di configurare con facilità diversi computer con gli stessi server presenti in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="df22c-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="df22c-105">Ciò risulta utile quando si gestisce un numero elevato di server da computer distribuiti in diversi luoghi oppure quando si desidera configurare le impostazioni di connessione di base per un utente poco esperto.</span><span class="sxs-lookup"><span data-stu-id="df22c-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df22c-106">Non è possibile importare le informazioni sui server registrati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] da versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df22c-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="df22c-107">Per importare informazioni relative ai server registrati</span><span class="sxs-lookup"><span data-stu-id="df22c-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="df22c-108">In Server registrati fare clic sul tipo di server sulla barra degli strumenti Server registrati.</span><span class="sxs-lookup"><span data-stu-id="df22c-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="df22c-109">Il tipo di server deve corrispondere al tipo del file di esportazione dei server registrati.</span><span class="sxs-lookup"><span data-stu-id="df22c-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="df22c-110">Se, ad esempio, sono state esportate informazioni sui server registrati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , fare clic su **SQL Server** sulla barra degli strumenti Server registrati.</span><span class="sxs-lookup"><span data-stu-id="df22c-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="df22c-111">Fare clic con il pulsante destro del mouse su un gruppo di server e quindi scegliere **Importa**.</span><span class="sxs-lookup"><span data-stu-id="df22c-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="df22c-112">Nella finestra di dialogo **Importa Server registrati** selezionare il file dei server registrati da importare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="df22c-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="df22c-113">**File da importare**</span><span class="sxs-lookup"><span data-stu-id="df22c-113">**Import file**</span></span>  
     <span data-ttu-id="df22c-114">Digitare il nome del file da importare nella casella di testo oppure fare clic sul pulsante Sfoglia ( **...** ) per individuare il file da importare nel computer client.</span><span class="sxs-lookup"><span data-stu-id="df22c-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="df22c-115">Se si seleziona un file esistente, le informazioni relative ai server registrati verranno aggiunte al file.</span><span class="sxs-lookup"><span data-stu-id="df22c-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="df22c-116">Il file da importare deve essere un file dei server registrati precedentemente esportato.</span><span class="sxs-lookup"><span data-stu-id="df22c-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="df22c-117">I file dei server registrati hanno l'estensione regsrvr.</span><span class="sxs-lookup"><span data-stu-id="df22c-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="df22c-118">**Selezionare il gruppo di server in cui eseguire l'importazione**</span><span class="sxs-lookup"><span data-stu-id="df22c-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="df22c-119">Consente di selezionare il nodo radice o un gruppo di server particolare in cui verranno importate le voci dei server registrati presenti nel file.</span><span class="sxs-lookup"><span data-stu-id="df22c-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="df22c-120">È possibile importare tutti i server registrati, i server registrati in un dato gruppo di server oppure un singolo server registrato.</span><span class="sxs-lookup"><span data-stu-id="df22c-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="df22c-121">La funzionalità di importazione è ricorsiva. Se, ad esempio, il gruppo di server A contiene il gruppo di server B e il gruppo di server B contiene i gruppi di server C e D, l'importazione del gruppo di server A determinerà l'importazione di tutte le voci contenute nei gruppi A, B, C e D.</span><span class="sxs-lookup"><span data-stu-id="df22c-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="df22c-122">Il gruppo di server visualizza solo i gruppi di server dell'albero di server registrati corrente.</span><span class="sxs-lookup"><span data-stu-id="df22c-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="df22c-123">Se si sceglie di importare un gruppo di server o un server esistente, verrà visualizzato un messaggio che richiede di confermare la sovrascrittura del server o del gruppo di server esistente.</span><span class="sxs-lookup"><span data-stu-id="df22c-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="df22c-124">Le registrazioni dei server che utilizzano l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguono l'archiviazione delle password separatamente per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="df22c-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="df22c-125">Dopo avere importato le registrazioni dei server, è necessario che gli utenti immettano la password per ogni server al momento della prima connessione, in modo tale che le password vengano archiviate nei relativi elenchi dei server registrati.</span><span class="sxs-lookup"><span data-stu-id="df22c-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="df22c-126">Questa operazione non è necessaria per i server registrati mediante l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="df22c-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df22c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df22c-127">See Also</span></span>  
 <span data-ttu-id="df22c-128">[Modificare la &#40;di registrazione di un server SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [esportare le informazioni sul server registrato &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="df22c-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="df22c-129">Creare un nuovo server registrato &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="df22c-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
