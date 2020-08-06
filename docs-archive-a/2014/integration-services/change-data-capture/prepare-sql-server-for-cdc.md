---
title: Preparare SQL Server per CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625520"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="1cab8-102">Preparare SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="1cab8-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="1cab8-103">Il servizio Oracle CDC richiede che tutte le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione contengano il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1cab8-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="1cab8-104">Per creare questo database utilizzare l'azione Prepare SQL Server in CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="1cab8-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="1cab8-105">Verrà creato uno script speciale eseguito per creare le tabelle, le stored procedure e altri artefatti obbligatori per il database.</span><span class="sxs-lookup"><span data-stu-id="1cab8-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="1cab8-106">Questa attività viene eseguita una volta sola per ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1cab8-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="1cab8-107">Per ulteriori informazioni sul database MSXDBCDC, vedere Database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1cab8-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="1cab8-108">In CDC Service Configuration Console, fare clic su **Prepare SQL Server**(Prepara SQL Server).</span><span class="sxs-lookup"><span data-stu-id="1cab8-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="1cab8-109">Se questa opzione non è disponibile, verificare che nel riquadro sinistro della console sia selezionata l'opzione **Local CDC Services** (Servizi CDC locali).</span><span class="sxs-lookup"><span data-stu-id="1cab8-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1cab8-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1cab8-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="1cab8-111">Server Name</span><span class="sxs-lookup"><span data-stu-id="1cab8-111">Server Name</span></span>  
 <span data-ttu-id="1cab8-112">Digitare il nome del server in cui si trova [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cab8-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="1cab8-113">Authentication</span><span class="sxs-lookup"><span data-stu-id="1cab8-113">Authentication</span></span>  
 <span data-ttu-id="1cab8-114">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cab8-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="1cab8-115">**Autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="1cab8-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="1cab8-116">**Autenticazione di SQL Server**: se si seleziona questa opzione, è necessario digitare il **nome utente** e la **password** dell'utente nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si effettua la connessione.</span><span class="sxs-lookup"><span data-stu-id="1cab8-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="1cab8-117">Per preparare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per Oracle CDC, l'account di accesso deve disporre di autorizzazioni di scrittura per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="1cab8-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="1cab8-118">Immettere le credenziali per un account di accesso che dispone di autorizzazioni per il database MSXDBCDC, ad esempio un membro del ruolo `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="1cab8-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="1cab8-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1cab8-119">Options</span></span>  
 <span data-ttu-id="1cab8-120">Fare clic sulla freccia per visualizzare le opzioni disponibili da configurare.</span><span class="sxs-lookup"><span data-stu-id="1cab8-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="1cab8-121">È possibile scegliere di non modificare il valore predefinito per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="1cab8-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="1cab8-122">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cab8-122">The available options are:</span></span>  
  
-   <span data-ttu-id="1cab8-123">**Connection Timeout** (Timeout connessione): Digitare il tempo, in secondi, di attesa del servizio CDC per Oracle per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima che si verifichi un errore di timeout. Il valore predefinito è **15**.</span><span class="sxs-lookup"><span data-stu-id="1cab8-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="1cab8-124">**Timeout connessione** (Timeout esecuzione): Digitare il tempo, in secondi, di attesa del servizio Windows Oracle CDC per l'esecuzione di un comando prima che si verifichi un errore di timeout. Il valore predefinito è **30**.</span><span class="sxs-lookup"><span data-stu-id="1cab8-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="1cab8-125">**Encrypt Connection** (Crittografia connessione): selezionare **Encrypt Connection** (Crittografa connessione) per la comunicazione tra il servizio Oracle CDC e l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione tramite una connessione crittografata.</span><span class="sxs-lookup"><span data-stu-id="1cab8-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="1cab8-126">**Avanzate**: digitare eventuali proprietà di connessione aggiuntive, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1cab8-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="1cab8-127">View Script</span><span class="sxs-lookup"><span data-stu-id="1cab8-127">View Script</span></span>  
 <span data-ttu-id="1cab8-128">Fare clic su **Visualizza script** per visualizzare una versione di sola lettura dello script di impostazione.</span><span class="sxs-lookup"><span data-stu-id="1cab8-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="1cab8-129">Se necessario, un amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può copiare questo script nella console di gestione di SQL Server per modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1cab8-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="1cab8-130">Per altre informazioni sulla preparazione di SQL Server per lo script, vedere [Preparare SQL Server per lo script di visualizzazione di Oracle CDC](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="1cab8-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cab8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cab8-131">See Also</span></span>  
 <span data-ttu-id="1cab8-132">[Procedura di utilizzo dei servizi CDC](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="1cab8-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="1cab8-133">Procedura di preparazione di SQL Server per CDC</span><span class="sxs-lookup"><span data-stu-id="1cab8-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
