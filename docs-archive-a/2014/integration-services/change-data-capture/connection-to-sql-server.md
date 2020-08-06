---
title: Connessione a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5bb582f9-68d3-4c1e-ab02-6fc16807f1a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6639118b3bd531e5cece8899eb0d68e00e566186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625523"
---
# <a name="connection-to-sql-server"></a><span data-ttu-id="e8d11-102">Connessione a SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8d11-102">Connection to SQL Server</span></span>
  <span data-ttu-id="e8d11-103">Quando si tenta di creare un'istanza di Oracle CDC con un account di accesso senza un ruolo del database che include l'autorizzazione di scrittura (ad esempio il ruolo **db_owner** ) per il database MSXDBCDC, viene visualizzata la finestra di dialogo Connetti a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8d11-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to create an Oracle CDC instanced, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="e8d11-104">In questa finestra di dialogo è necessario immettere le credenziali per un account di accesso con autorizzazione di scrittura per il database MSXDBCDC, ad esempio il ruolo del database **db_owner** , per creare la nuova istanza di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="e8d11-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to create the new Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="e8d11-105">Immettere le informazioni riportate di seguito nella finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8d11-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="e8d11-106">Server Name</span><span class="sxs-lookup"><span data-stu-id="e8d11-106">Server Name</span></span>  
 <span data-ttu-id="e8d11-107">Digitare il nome del server in cui si trova [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8d11-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="e8d11-108">Authentication</span><span class="sxs-lookup"><span data-stu-id="e8d11-108">Authentication</span></span>  
 <span data-ttu-id="e8d11-109">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8d11-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="e8d11-110">Autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="e8d11-110">Windows Authentication</span></span>  
  
-   <span data-ttu-id="e8d11-111">**Autenticazione di SQL Server**: se si seleziona questa opzione, è necessario digitare **Login** e **Password** per l'utente nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui si esegue la connessione.</span><span class="sxs-lookup"><span data-stu-id="e8d11-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
### <a name="options"></a><span data-ttu-id="e8d11-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e8d11-112">Options</span></span>  
 <span data-ttu-id="e8d11-113">Fare clic sulla freccia per visualizzare le opzioni disponibili da configurare.</span><span class="sxs-lookup"><span data-stu-id="e8d11-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="e8d11-114">È possibile scegliere di non modificare il valore predefinito per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="e8d11-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="e8d11-115">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8d11-115">The available options are:</span></span>  
  
-   <span data-ttu-id="e8d11-116">**Timeout connessione**: digitare il tempo, in secondi, di attesa del programma per la connessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da stabilire prima che venga generato un errore di timeout.</span><span class="sxs-lookup"><span data-stu-id="e8d11-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="e8d11-117">Il valore predefinito è **15**.</span><span class="sxs-lookup"><span data-stu-id="e8d11-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="e8d11-118">**Timeout esecuzione**: digitare il tempo, in secondi, di attesa del programma per l'esecuzione del comando SQL da terminare prima che venga generato un errore di timeout.</span><span class="sxs-lookup"><span data-stu-id="e8d11-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="e8d11-119">Il valore predefinito è **30**.</span><span class="sxs-lookup"><span data-stu-id="e8d11-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="e8d11-120">**Crittografa connessione**: selezionare **Crittografa connessione** per assicurare che la connessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da stabilire venga crittografata per garantire la privacy.</span><span class="sxs-lookup"><span data-stu-id="e8d11-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="e8d11-121">**Advanced**: fare clic su **Advanced** e digitare eventuali proprietà di connessione aggiuntive nella finestra di dialogo Advanced Connection Properties, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e8d11-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d11-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8d11-122">See Also</span></span>  
 [<span data-ttu-id="e8d11-123">Autorizzazioni necessarie per la connessione a SQL per il servizio CDC</span><span class="sxs-lookup"><span data-stu-id="e8d11-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
