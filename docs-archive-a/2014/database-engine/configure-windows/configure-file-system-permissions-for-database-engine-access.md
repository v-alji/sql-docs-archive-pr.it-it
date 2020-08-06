---
title: Configurare le autorizzazioni del file system per l'accesso al motore di database | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638104"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="b29ff-102">Configurare le autorizzazioni del file system per l'accesso al motore di database</span><span class="sxs-lookup"><span data-stu-id="b29ff-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="b29ff-103">In questo argomento viene illustrato come concedere al [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]l'accesso al file system nel percorso in cui sono archiviati i file di database.</span><span class="sxs-lookup"><span data-stu-id="b29ff-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="b29ff-104">Il servizio [!INCLUDE[ssDE](../../includes/ssde-md.md)] deve disporre dell'autorizzazione del file system di Windows per accedere alla cartella file in cui sono archiviati i file di database.</span><span class="sxs-lookup"><span data-stu-id="b29ff-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="b29ff-105">L'autorizzazione per il percorso predefinito viene configurata durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="b29ff-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="b29ff-106">Se si posizionano i file di database in un percorso diverso, potrebbe essere necessario seguire questi passaggi per concedere al [!INCLUDE[ssDE](../../includes/ssde-md.md)] l'autorizzazione di controllo completo per il percorso in questione.</span><span class="sxs-lookup"><span data-stu-id="b29ff-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="b29ff-107">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] le autorizzazioni vengono assegnate al SID per servizio per ognuno dei relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="b29ff-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="b29ff-108">Tramite questo sistema viene fornito un livello elevato di isolamento e protezione del servizio.</span><span class="sxs-lookup"><span data-stu-id="b29ff-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="b29ff-109">Il SID per servizio deriva dal nome del servizio ed è univoco per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="b29ff-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="b29ff-110">L'argomento [Configurare account di servizio e autorizzazioni di Windows](configure-windows-service-accounts-and-permissions.md) descrive il SID per servizio e nella sezione **Privilegi e diritti di Windows**specifica i nomi.</span><span class="sxs-lookup"><span data-stu-id="b29ff-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="b29ff-111">Si tratta del SID per servizio a cui deve essere assegnata l'autorizzazione di accesso per il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="b29ff-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="b29ff-112">Per concedere le autorizzazioni del file system al SID per servizio</span><span class="sxs-lookup"><span data-stu-id="b29ff-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="b29ff-113">Utilizzando Esplora risorse passare al percorso del file system in cui sono archiviati i file di database.</span><span class="sxs-lookup"><span data-stu-id="b29ff-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="b29ff-114">Fare clic con il pulsante destro del mouse sulla cartella del file system e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b29ff-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b29ff-115">Nella scheda **Sicurezza** fare clic su **Modifica**quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b29ff-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="b29ff-116">Nella finestra di dialogo per la **selezione di utenti, computer, account del servizio o gruppi** fare clic su **Percorsi**sopra l'elenco di percorsi, selezionare il nome del computer e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b29ff-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b29ff-117">Nella casella **immettere i nomi degli oggetti da selezionare** Digitare il nome del SID per servizio elencato nell'argomento **configurare account di servizio e autorizzazioni di Windows**nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="b29ff-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="b29ff-118">Per il [!INCLUDE[ssDE](../../includes/ssde-md.md)] SID per servizio, utilizzare **NT SERVICE\MSSQLSERVER** per un'istanza predefinita o **NT SERVICE\MSSQL $ InstanceName** per un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="b29ff-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="b29ff-119">Fare clic su **Controlla nomi** per convalidare la voce.</span><span class="sxs-lookup"><span data-stu-id="b29ff-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="b29ff-120">La convalida spesso non viene completata e potrebbe essere indicato che il nome non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="b29ff-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="b29ff-121">Quando si fa clic su **OK**, viene visualizzata la finestra di dialogo **Trovati più nomi** .</span><span class="sxs-lookup"><span data-stu-id="b29ff-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="b29ff-122">A questo punto, selezionare il SID per servizio, **MSSQLSERVER** o **NT SERVICE\MSSQL $ InstanceName**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b29ff-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b29ff-123">Fare di nuovo clic su **OK** per tornare alla finestra di dialogo **autorizzazioni** .</span><span class="sxs-lookup"><span data-stu-id="b29ff-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="b29ff-124">Nella casella nome **gruppo o utente** selezionare il SID per servizio e quindi nella casella **autorizzazioni per** \<name> selezionare la casella di controllo **Consenti** per **controllo completo**.</span><span class="sxs-lookup"><span data-stu-id="b29ff-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="b29ff-125">Fare clic su **Applica**quindi due volte su **OK** per uscire.</span><span class="sxs-lookup"><span data-stu-id="b29ff-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29ff-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b29ff-126">See Also</span></span>  
 <span data-ttu-id="b29ff-127">[Gestire il servizio Motore di database](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="b29ff-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="b29ff-128">[Spostare i database di sistema](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b29ff-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="b29ff-129">Spostare database utente</span><span class="sxs-lookup"><span data-stu-id="b29ff-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
