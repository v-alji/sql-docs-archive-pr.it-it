---
title: Accedere a CDC Designer Console | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724880"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="07471-102">Accedere a CDC Designer Console</span><span class="sxs-lookup"><span data-stu-id="07471-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="07471-103">È possibile accedere a CDC Designer Console dal computer in cui è stata installata la console.</span><span class="sxs-lookup"><span data-stu-id="07471-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="07471-104">Per ulteriori informazioni sull'installazione, vedere Installazione.</span><span class="sxs-lookup"><span data-stu-id="07471-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="07471-105">Quando si apre CDC Designer Console, verrà visualizzata la finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07471-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="07471-106">L'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che accede alla finestra di progettazione di CDC deve disporre delle autorizzazioni UPDATE per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="07471-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="07471-107">Deve inoltre disporre del ruolo predefinito del server `dbcreator` per creare nuove istanze di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="07471-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="07471-108">L'account di accesso dovrebbe inoltre disporre dell'accesso SELECT ai database CDC utilizzati, in caso contrario l'utente non sarà in grado di visualizzare lo stato di questi database.</span><span class="sxs-lookup"><span data-stu-id="07471-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="07471-109">Immettere le informazioni riportate di seguito nella finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07471-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="07471-110">Server Name</span><span class="sxs-lookup"><span data-stu-id="07471-110">Server Name</span></span>  
 <span data-ttu-id="07471-111">Digitare il nome del server in cui si trova [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07471-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="07471-112">Authentication</span><span class="sxs-lookup"><span data-stu-id="07471-112">Authentication</span></span>  
 <span data-ttu-id="07471-113">Selezionare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07471-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="07471-114">**Autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="07471-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="07471-115">**Autenticazione di SQL Server**: se si seleziona questa opzione, è necessario digitare **Account di accesso** e **Password** per l'utente nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a cui ci si connette.</span><span class="sxs-lookup"><span data-stu-id="07471-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="07471-116">L'account di accesso deve disporre di un ruolo del database che consenta l'accesso al database MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="07471-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="07471-117">L'account di accesso deve inoltre disporre dell'accesso a eventuali database aggiuntivi in uso, in caso contrario l'utente non sarà in grado di visualizzare i dati in quei database.</span><span class="sxs-lookup"><span data-stu-id="07471-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="07471-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="07471-118">Options</span></span>  
 <span data-ttu-id="07471-119">Fare clic sulla freccia per visualizzare le opzioni disponibili da configurare.</span><span class="sxs-lookup"><span data-stu-id="07471-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="07471-120">È possibile scegliere di non modificare il valore predefinito per queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="07471-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="07471-121">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07471-121">The available options are:</span></span>  
  
 <span data-ttu-id="07471-122">**Connection Timeout**</span><span class="sxs-lookup"><span data-stu-id="07471-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="07471-123">Digitare il tempo, in secondi, di attesa del servizio CDC per Oracle per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima che si verifichi un errore di timeout. Il valore predefinito è **15**.</span><span class="sxs-lookup"><span data-stu-id="07471-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="07471-124">**Execution Timeout**</span><span class="sxs-lookup"><span data-stu-id="07471-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="07471-125">Digitare il tempo, in secondi, di attesa del servizio Windows Oracle CDC per l'esecuzione di un comando prima che si verifichi un errore di timeout. Il valore predefinito è **30**.</span><span class="sxs-lookup"><span data-stu-id="07471-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="07471-126">**Encrypt Connection**</span><span class="sxs-lookup"><span data-stu-id="07471-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="07471-127">Selezionare **Encrypt Connection** (Crittografa connessione) per la comunicazione tra il servizio Oracle CDC e l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione tramite una connessione crittografata. **Advanced (Avanzate)** : Fare clic su **Advanced** e digitare eventuali proprietà di connessione aggiuntive nella finestra di dialogo Advanced Connection Properties.</span><span class="sxs-lookup"><span data-stu-id="07471-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="07471-128">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="07471-128">**Advanced**</span></span>  
 <span data-ttu-id="07471-129">Fare clic su **Advanced** e digitare eventuali proprietà di connessione aggiuntive nella finestra di dialogo Advanced Connection Properties.</span><span class="sxs-lookup"><span data-stu-id="07471-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="07471-130">Per informazioni sulla finestra di dialogo Advanced Connection Properties, vedere [Advanced Connection Properties](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="07471-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07471-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07471-131">See Also</span></span>  
 [<span data-ttu-id="07471-132">Autorizzazioni necessarie della connessione di SQL Server per la finestra di progettazione di CDC</span><span class="sxs-lookup"><span data-stu-id="07471-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
