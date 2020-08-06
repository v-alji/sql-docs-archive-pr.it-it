---
title: Creare il database delle modifiche di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724040"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="0aa1d-102">Creare il database delle modifiche di SQL Server</span><span class="sxs-lookup"><span data-stu-id="0aa1d-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="0aa1d-103">Quando si avvia la New Instance Wizard, viene visualizzata la pagina Create CDC Database.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="0aa1d-104">Utilizzare la pagina Create CDC Database per fornire informazioni sulla nuova istanza di CDC e creare un nuovo database delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="0aa1d-105">Quando si crea un nuovo database CDC esso viene abilitato per SQL Server CDC. Questa operazione richiede un account di accesso che sia un membro del ruolo predefinito del server `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="0aa1d-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="0aa1d-106">Se l'utente che avvia la procedura guidata Create an Oracle CDC Instance non è un membro del ruolo predefinito del server `sysadmin` , viene visualizzata la finestra di dialogo Connect to SQL Server e vengono richieste le credenziali per un membro del ruolo sysadmin per eseguire l'attività SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="0aa1d-107">Quando viene creato il database CDC, l'account di accesso `sysadmin` viene eliminato e viene ripreso l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] originale utilizzato al momento dell'accesso a Oracle Designer Console.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0aa1d-108">Per attività diverse dall'abilitazione del database per SQL Server CDC, l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usato per l'esecuzione della Procedura guidata nuova istanza deve disporre delle autorizzazioni UPDATE e del ruolo predefinito del server `dbcreator` per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="0aa1d-109">Per informazioni sull'immissione dei dati nella finestra di dialogo Connect to SQL Server, vedere [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="0aa1d-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0aa1d-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0aa1d-110">Options</span></span>  
 <span data-ttu-id="0aa1d-111">**Oracle CDC Instance**</span><span class="sxs-lookup"><span data-stu-id="0aa1d-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="0aa1d-112">Specificare le informazioni seguenti sull'istanza di CDC che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="0aa1d-113">**Name**: digitare un nome per il nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="0aa1d-114">Sarà anche il nome del nuovo database delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="0aa1d-115">**Description**: digitare una descrizione per la nuova istanza che consenta di identificarla.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="0aa1d-116">Operazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-116">This is optional.</span></span>  
  
 <span data-ttu-id="0aa1d-117">**SQL Server Change Database**</span><span class="sxs-lookup"><span data-stu-id="0aa1d-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="0aa1d-118">Questa sezione viene utilizzata per creare il database.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="0aa1d-119">**Change Database**: nome del nuovo database delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="0aa1d-120">Il nome del database equivale al nome specificato per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="0aa1d-121">In questo campo di sola lettura viene visualizzato il percorso completo del database.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="0aa1d-122">**Create Database**: fare clic su **Create Database** per creare il database.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="0aa1d-123">Per creare il database, l'account di accesso deve disporre del ruolo del server `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="0aa1d-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="0aa1d-124">Per ulteriori informazioni, vedere la nota sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0aa1d-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="0aa1d-125">Dopo avere creato il database, è possibile fare clic su **Next** in [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span><span class="sxs-lookup"><span data-stu-id="0aa1d-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa1d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa1d-126">See Also</span></span>  
 <span data-ttu-id="0aa1d-127">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="0aa1d-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="0aa1d-128">Servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="0aa1d-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
