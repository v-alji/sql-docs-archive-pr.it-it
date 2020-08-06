---
title: Accedere ai dati per le operazioni DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716880"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="7553f-102">Accedere ai dati per le operazioni DQS</span><span class="sxs-lookup"><span data-stu-id="7553f-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="7553f-103">Per utilizzare i dati di origine per operazioni [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) ed esportare i dati elaborati, è possibile effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7553f-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="7553f-104">Copiare i dati di origine in una tabella o vista nel database DQS_STAGING_DATA, quindi usarli per le operazioni DQS.</span><span class="sxs-lookup"><span data-stu-id="7553f-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="7553f-105">Inoltre è possibile esportare i dati elaborati in una nuova tabella nel database DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="7553f-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="7553f-106">A questo scopo, all'account utente di Windows deve essere concesso l'accesso in lettura/scrittura al database DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="7553f-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="7553f-107">Usare il database in uso come dati di origine per le operazioni DQS e come destinazione per l'esportazione dei dati elaborati.</span><span class="sxs-lookup"><span data-stu-id="7553f-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="7553f-108">A tale scopo, assicurarsi che il database si trovi nella stessa istanza di SQL Server dei database del server Data Quality.</span><span class="sxs-lookup"><span data-stu-id="7553f-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="7553f-109">In caso contrario, il database non sarà disponibile nel client Data Quality per le relative operazioni.</span><span class="sxs-lookup"><span data-stu-id="7553f-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="7553f-110">All'account utente di Windows deve essere concesso anche l'accesso al database DQS_STAGING_DATA per l'esportazione dei risultati corrispondenti perché questa operazione è un processo in due fasi: i risultati corrispondenti vengono prima esportati nelle tabelle temporanee del database DQS_STAGING_DATA e successivamente vengono spostati nella tabella nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7553f-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7553f-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7553f-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="7553f-112">È necessario aver completato l'installazione di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] tramite l'esecuzione del file DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="7553f-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="7553f-113">Per altre informazioni, vedere [Eseguire DQSInstaller.exe per completare l'installazione del server DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="7553f-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="7553f-114">L'account utente di Windows deve essere un membro del ruolo predefinito del server appropriato (ad esempio securityadmin, serveradmin o sysadmin) nell'istanza del motore di database per concedere/modificare l'accesso all'account di accesso SQL sui database.</span><span class="sxs-lookup"><span data-stu-id="7553f-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="7553f-115">Per concedere l'accesso in lettura/scrittura a un utente sul database DQS_STAGING_DATA</span><span class="sxs-lookup"><span data-stu-id="7553f-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="7553f-116">Avviare Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="7553f-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="7553f-117">In Microsoft SQL Server Management Studio espandere l'istanza di SQL Server, espandere **Sicurezza**, quindi **Account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="7553f-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="7553f-118">Fare clic con il pulsante destro del mouse sull'account di accesso SQL, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7553f-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7553f-119">Nel riquadro sinistro della finestra di dialogo **Proprietà account di accesso** fare clic su **Mapping utenti** .</span><span class="sxs-lookup"><span data-stu-id="7553f-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="7553f-120">Nel riquadro di destra selezionare la casella di controllo sotto la colonna **Mappa** per il database **DQS_STAGING_DATA** , quindi selezionare i ruoli seguenti nel riquadro **Appartenenza a ruoli del database per: DQS_STAGING_DATA** :</span><span class="sxs-lookup"><span data-stu-id="7553f-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="7553f-121">**db_datareader**: consente di leggere i dati da tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="7553f-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="7553f-122">**db_datawriter**: consente di aggiungere, eliminare o modificare i dati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="7553f-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="7553f-123">**db_ddladmin**: consente di creare, modificare o eliminare tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="7553f-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="7553f-124">Nella finestra di dialogo **Proprietà account di accesso** fare clic su **OK** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7553f-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7553f-125">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7553f-125">Next Steps</span></span>  
 <span data-ttu-id="7553f-126">Provare a effettuare operazioni DQS tramite cui si accede al database come origine dati per l'operazione DQS, quindi esportare i dati elaborati nel database.</span><span class="sxs-lookup"><span data-stu-id="7553f-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7553f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7553f-127">See Also</span></span>  
 [<span data-ttu-id="7553f-128">Installare Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="7553f-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
