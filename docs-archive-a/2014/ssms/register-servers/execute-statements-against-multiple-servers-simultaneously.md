---
title: Eseguire simultaneamente istruzioni su più server
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717190"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="2f8f7-102">Esecuzione simultanea di istruzioni su più server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2f8f7-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2f8f7-103">In questo argomento viene descritto come eseguire una query su più server contemporaneamente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]creando un gruppo di server locali, o un server di gestione centrale e uno o più gruppi di server, e uno o più server registrati all'interno dei gruppi, quindi eseguendo la query sul gruppo completo.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="2f8f7-104">I risultati restituiti dalla query possono essere combinati in un singolo riquadro dei risultati oppure possono essere inclusi in riquadri dei risultati distinti.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="2f8f7-105">Il set di risultati può includere colonne aggiuntive per il nome del server e l'account di accesso utilizzati dalla query in ciascun server.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="2f8f7-106">I server di gestione centrale e i server subordinati possono essere registrati solo tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="2f8f7-107">I server inclusi nei gruppi di server locali possono essere registrati tramite l'autenticazione di Windows o l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f8f7-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f8f7-108">Prima di utilizzare le procedure seguenti, creare un server di gestione centrale e uno o più gruppi di server.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="2f8f7-109">Per altre informazioni, vedere [Creazione di un server di gestione centrale e di un gruppo di server &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="2f8f7-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="2f8f7-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2f8f7-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f8f7-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2f8f7-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f8f7-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f8f7-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f8f7-113">**Per eseguire istruzioni su più server tramite:**</span><span class="sxs-lookup"><span data-stu-id="2f8f7-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="2f8f7-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f8f7-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f8f7-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2f8f7-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f8f7-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f8f7-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f8f7-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2f8f7-117">Permissions</span></span>  
 <span data-ttu-id="2f8f7-118">Poiché le connessioni gestite da un server di gestione centrale vengono eseguite nel contesto dell'utente, l'utilizzo dell'autenticazione di Windows comporta la possibile variazione delle autorizzazioni effettive per i server registrati.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="2f8f7-119">L'utente, ad esempio, potrebbe essere un membro del ruolo predefinito del server sysadmin nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, ma disporre di autorizzazioni limitate per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2f8f7-120">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f8f7-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="2f8f7-121">Per eseguire istruzioni su più destinazioni di configurazione simultaneamente</span><span class="sxs-lookup"><span data-stu-id="2f8f7-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="2f8f7-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="2f8f7-123">Espandere un server di gestione centrale, fare clic con il pulsante destro del mouse su un gruppo di server, scegliere **Connetti**, quindi fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2f8f7-124">Nell'editor di query digitare ed eseguire un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] , ad esempio la seguente:</span><span class="sxs-lookup"><span data-stu-id="2f8f7-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="2f8f7-125">Per impostazione predefinita, il riquadro dei risultati combinerà i risultati della query restituiti da tutti i server inclusi nel gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="2f8f7-126">Per modificare le opzioni dei risultati multiserver</span><span class="sxs-lookup"><span data-stu-id="2f8f7-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="2f8f7-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="2f8f7-128">Espandere **Risultati query**, espandere **SQL Server**, quindi fare clic su **Risultati multiserver**.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="2f8f7-129">Nella pagina **Risultati multiserver** specificare le impostazioni desiderate per le opzioni, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f8f7-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8f7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f8f7-130">See Also</span></span>  
 [<span data-ttu-id="2f8f7-131">Amministrare più server tramite server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="2f8f7-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
