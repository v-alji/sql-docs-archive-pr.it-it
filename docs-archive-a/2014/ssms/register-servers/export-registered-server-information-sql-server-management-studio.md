---
title: Esportare informazioni relative ai server registrati
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722163"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="7f268-102">Esportare informazioni relative a server registrati (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7f268-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7f268-103">In questo argomento viene illustrato come salvare ed esportare le informazioni relative a server registrati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]e distribuirle ad altri dipendenti o server.</span><span class="sxs-lookup"><span data-stu-id="7f268-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="7f268-104">È possibile utilizzare questa funzionalità di esportazione per ottenere un'interfaccia utente coerente su più computer.</span><span class="sxs-lookup"><span data-stu-id="7f268-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="7f268-105">L'esportazione e la successiva importazione dei file dei server registrati consente di configurare con facilità diversi computer con gli stessi server presenti in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="7f268-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="7f268-106">Ciò risulta utile quando si gestisce un numero elevato di server da computer distribuiti in diversi luoghi oppure quando si desidera configurare le impostazioni di connessione di base per un utente non esperto.</span><span class="sxs-lookup"><span data-stu-id="7f268-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f268-107">Le registrazioni server che usano l'autenticazione di SQL Server archiviano le password separatamente per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="7f268-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="7f268-108">Dopo aver esportato e importato le registrazioni dei server, è necessario che gli utenti immettano la password per ogni server al momento della prima connessione, in modo tale che le password vengano archiviate nei relativi elenchi dei server registrati.</span><span class="sxs-lookup"><span data-stu-id="7f268-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="7f268-109">Questa operazione non è necessaria per i server registrati mediante l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7f268-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="7f268-110">Per esportare informazioni relative a server registrati</span><span class="sxs-lookup"><span data-stu-id="7f268-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="7f268-111">Nella finestra Server registrati fare clic con il pulsante destro del mouse su un gruppo di server e quindi scegliere **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="7f268-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7f268-112">È possibile esportare un singolo server, l'intero albero dei server registrati, oppure un subset dell'albero stesso.</span><span class="sxs-lookup"><span data-stu-id="7f268-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="7f268-113">Nella finestra di dialogo **Esporta server registrati** selezionare le selezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7f268-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="7f268-114">**Gruppo di server**</span><span class="sxs-lookup"><span data-stu-id="7f268-114">**Server group**</span></span>  
     <span data-ttu-id="7f268-115">Specificare il gruppo di server che verrà esportato.</span><span class="sxs-lookup"><span data-stu-id="7f268-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="7f268-116">Esportare nel file di esportazione tutti i server registrati, i server registrati in un particolare gruppo di server oppure un singolo server registrato.</span><span class="sxs-lookup"><span data-stu-id="7f268-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="7f268-117">La funzionalità di esportazione è ricorsiva. Se, ad esempio, il gruppo di server A contiene il gruppo di server B e il gruppo di server B contiene i gruppi di server C e D, l'esportazione del gruppo A determinerà l'esportazione di tutte le voci contenute nei gruppi A, B, C e D.</span><span class="sxs-lookup"><span data-stu-id="7f268-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="7f268-118">Il gruppo di server visualizza solo i gruppi di server dell'albero di server registrati corrente.</span><span class="sxs-lookup"><span data-stu-id="7f268-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="7f268-119">**File di esportazione**</span><span class="sxs-lookup"><span data-stu-id="7f268-119">**Export file**</span></span>  
     <span data-ttu-id="7f268-120">Digitare il nome del file da esportare nella casella di testo oppure usare il pulsante Sfoglia ( **...** ) per trovare il file di esportazione nel computer client.</span><span class="sxs-lookup"><span data-stu-id="7f268-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="7f268-121">Se si seleziona un file esistente, le informazioni relative ai server registrati verranno aggiunte al file.</span><span class="sxs-lookup"><span data-stu-id="7f268-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="7f268-122">Verrà utilizzata l'estensione regsrvr.</span><span class="sxs-lookup"><span data-stu-id="7f268-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="7f268-123">Per rendere le informazioni relative ai server registrati disponibili ad altri utenti o a un altro computer, è possibile salvare il file sulla rete.</span><span class="sxs-lookup"><span data-stu-id="7f268-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="7f268-124">Gli altri utenti possono accedere al file e importare le informazioni relative ai server registrati, anche parzialmente.</span><span class="sxs-lookup"><span data-stu-id="7f268-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="7f268-125">Se si seleziona un file esistente come file di esportazione, il contenuto del file viene sovrascritto con le informazioni relative alla registrazione dei server.</span><span class="sxs-lookup"><span data-stu-id="7f268-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="7f268-126">**Non includere nomi utente e password nel file di esportazione**</span><span class="sxs-lookup"><span data-stu-id="7f268-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="7f268-127">Consente di escludere i nomi utente durante l'esportazione del file.</span><span class="sxs-lookup"><span data-stu-id="7f268-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7f268-128">Sebbene i file di esportazione siano crittografati, se i nomi utente e le password di autenticazione di SQL Server vengono inclusi nel file, sarà opportuno controllare con attenzione l'accesso al file.</span><span class="sxs-lookup"><span data-stu-id="7f268-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="7f268-129">Per questo motivo i nomi utente e le password vengono esclusi dal file di esportazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f268-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f268-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f268-130">See Also</span></span>  
 <span data-ttu-id="7f268-131">[Importa informazioni server registrate &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [creare un nuovo server registrato &#40;SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="7f268-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
