---
title: Connessione di SQL Server per la creazione dell'istanza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625518"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="f72f3-102">Connessione di SQL Server per la creazione dell'istanza</span><span class="sxs-lookup"><span data-stu-id="f72f3-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="f72f3-103">Uno dei primi passaggi della creazione di un'istanza di Oracle CDC consiste nella creazione di un database CDC nell'istanza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f72f3-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="f72f3-104">Questo database CDC viene abilitato per SQL Server CDC. Questa operazione richiede un account di accesso che sia un membro del ruolo predefinito del server `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="f72f3-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="f72f3-105">Se un utente che avvia la procedura guidata **Create an Oracle CDC Instance** non è un membro del ruolo predefinito del server `sysadmin` , viene visualizzata la finestra di dialogo **Connect to SQL Server** e vengono richieste le credenziali per un membro del ruolo `sysadmin` per eseguire l'attività Enable the database for SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="f72f3-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="f72f3-106">Quando viene creato il database CDC, l'account di accesso `sysadmin` viene eliminato e viene ripreso l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] originale utilizzato al momento dell'accesso a Oracle Designer Console.</span><span class="sxs-lookup"><span data-stu-id="f72f3-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f72f3-107">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="f72f3-107">Task List</span></span>  
 <span data-ttu-id="f72f3-108">Immettere le informazioni riportate di seguito nella finestra di dialogo **Connect to SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="f72f3-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="f72f3-109">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="f72f3-109">**Server Name**</span></span>  
 <span data-ttu-id="f72f3-110">Digitare il nome del server in cui si trova [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f72f3-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="f72f3-111">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="f72f3-111">**Authentication**</span></span>  
 <span data-ttu-id="f72f3-112">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f72f3-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="f72f3-113">**Autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="f72f3-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="f72f3-114">**Autenticazione di SQL Server**: se si seleziona questa opzione, è necessario digitare **Account di accesso** e **Password** per l'utente nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui ci si connette.</span><span class="sxs-lookup"><span data-stu-id="f72f3-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="f72f3-115">L'account di accesso deve disporre di un ruolo del database che consenta l'accesso al database MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="f72f3-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="f72f3-116">L'account di accesso deve inoltre disporre dell'accesso a eventuali database aggiuntivi in uso, in caso contrario l'utente non sarà in grado di visualizzare i dati in quei database.</span><span class="sxs-lookup"><span data-stu-id="f72f3-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="f72f3-117">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="f72f3-117">**Options**</span></span>  
 <span data-ttu-id="f72f3-118">Fare clic sulla freccia per visualizzare le opzioni disponibili da configurare.</span><span class="sxs-lookup"><span data-stu-id="f72f3-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="f72f3-119">È possibile scegliere di non modificare il valore predefinito per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="f72f3-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="f72f3-120">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f72f3-120">The available options are:</span></span>  
  
-   <span data-ttu-id="f72f3-121">**Connection Timeout** (Timeout connessione): Digitare il tempo, in secondi, di attesa del servizio CDC per Oracle per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima che si verifichi un errore di timeout. Il valore predefinito è **15**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="f72f3-122">**Timeout connessione** (Timeout esecuzione): Digitare il tempo, in secondi, di attesa del servizio Windows Oracle CDC per l'esecuzione di un comando prima che si verifichi un errore di timeout. Il valore predefinito è **30**.</span><span class="sxs-lookup"><span data-stu-id="f72f3-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="f72f3-123">**Encrypt Connection** (Crittografia connessione): selezionare **Encrypt Connection** (Crittografa connessione) per la comunicazione tra il servizio Oracle CDC e l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione tramite una connessione crittografata.</span><span class="sxs-lookup"><span data-stu-id="f72f3-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="f72f3-124">**Avanzate**: Fare clic su **Advanced** e digitare eventuali proprietà di connessione aggiuntive nella finestra di dialogo Advanced Connection Properties.</span><span class="sxs-lookup"><span data-stu-id="f72f3-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="f72f3-125">Per informazioni sulla finestra di dialogo Advanced Connection Properties, vedere [Advanced Connection Properties](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f72f3-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f72f3-126">See Also</span></span>  
 <span data-ttu-id="f72f3-127">[Creare il database delle modifiche di SQL Server](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="f72f3-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="f72f3-128">Autorizzazioni necessarie della connessione di SQL Server per la finestra di progettazione di CDC</span><span class="sxs-lookup"><span data-stu-id="f72f3-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
