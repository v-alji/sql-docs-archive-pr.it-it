---
title: Visualizzare o modificare word breaker e filtri registrati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714095"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="278a3-102">Visualizzazione o modifica di word breaker e filtri registrati</span><span class="sxs-lookup"><span data-stu-id="278a3-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="278a3-103">Dopo l'installazione o la disinstallazione di word breaker o filtri in un sistema, le modifiche non diventano automaticamente effettive nelle istanze server.</span><span class="sxs-lookup"><span data-stu-id="278a3-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="278a3-104">In questo argomento viene descritto come visualizzare i word breaker o i filtri registrati, nonché come registrare i word breaker e i filtri appena installati in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="278a3-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="278a3-105">Per visualizzare un elenco delle lingue i cui word breaker sono registrati</span><span class="sxs-lookup"><span data-stu-id="278a3-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="278a3-106">Usare la vista del catalogo [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) , come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="278a3-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="278a3-107">Per visualizzare un elenco dei filtri registrati</span><span class="sxs-lookup"><span data-stu-id="278a3-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="278a3-108">Usare [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) , come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="278a3-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="278a3-109">Per registrare i word breaker e i filtri appena installati</span><span class="sxs-lookup"><span data-stu-id="278a3-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="278a3-110">Usare la stored procedure di sistema [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) per aggiornare l'elenco di lingue, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="278a3-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="278a3-111">Per annullare la registrazione di word breaker e filtri disinstallati</span><span class="sxs-lookup"><span data-stu-id="278a3-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="278a3-112">Usare **sp_fulltext_service** per aggiornare l'elenco di lingue nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="278a3-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="278a3-113">Usare **sp_fulltext_service** per riavviare i processi host del daemon di filtri (fdhost.exe) nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="278a3-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="278a3-114">Per sostituire i word breaker o i filtri esistenti dopo averne installati di nuovi</span><span class="sxs-lookup"><span data-stu-id="278a3-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="278a3-115">Quando si prepara l'installazione di un file DLL contenente nuovi word breaker o filtri, verificare che il nome sia diverso da quelli di eventuali file DLL installati nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="278a3-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="278a3-116">Copiare il nuovo file DLL nella directory contenente i file DLL standard di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'istanza server.</span><span class="sxs-lookup"><span data-stu-id="278a3-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="278a3-117">Il percorso predefinito è:</span><span class="sxs-lookup"><span data-stu-id="278a3-117">The default location is:</span></span>  
  
     <span data-ttu-id="278a3-118">C:\Programmi\Microsoft SQL Server\MSSQL.*nome_istanza*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="278a3-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="278a3-119">Si consiglia di caricare solo componenti firmati e verificati.</span><span class="sxs-lookup"><span data-stu-id="278a3-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="278a3-120">È inoltre consigliabile eseguire il servizio dell'utilità di avvio FDHOST (MSSQLFDLauncher) con privilegi minimi.</span><span class="sxs-lookup"><span data-stu-id="278a3-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="278a3-121">Installare i nuovi word breaker o filtri.</span><span class="sxs-lookup"><span data-stu-id="278a3-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="278a3-122">**Per installare e caricare filtri IFilter di Microsoft Filter Pack**</span><span class="sxs-lookup"><span data-stu-id="278a3-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="278a3-123">Come registrare IFilter di Microsoft Filter Pack con SQL Server</span><span class="sxs-lookup"><span data-stu-id="278a3-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="278a3-124">Usare **sp_fulltext_service** per caricare i word breaker e i filtri appena installati nell'istanza del server nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="278a3-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="278a3-125">Usare **sp_fulltext_service** per aggiornare l'elenco di lingue nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="278a3-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="278a3-126">Riavviare i processi host del daemon di filtri (fdhost.exe) usando **sp_fulltext_service** nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="278a3-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="278a3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="278a3-127">See Also</span></span>  
 <span data-ttu-id="278a3-128">[Impostazione dell'account del servizio dell'Utilità di avvio del daemon di filtri full-text](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="278a3-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="278a3-129">[Configurazione e gestione di filtri per la ricerca](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="278a3-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="278a3-130">Configurazione e gestione di word breaker e stemmer per la ricerca</span><span class="sxs-lookup"><span data-stu-id="278a3-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
