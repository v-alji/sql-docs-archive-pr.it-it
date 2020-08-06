---
title: 'Lesson 2: Specifying Connection Information (Reporting Services) (Lezione 2: Specifica delle informazioni di connessione (Reporting Services)) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715107"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="b234f-102">Lezione 2: Specifica delle informazioni di connessione (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="b234f-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="b234f-103">Dopo aver aggiunto un report al progetto Tutorial, è necessario definire un' *origine dati*, vale a dire informazioni di connessione usate dal report per accedere ai dati da un database relazionale, da un database multidimensionale o da un'altra risorsa.</span><span class="sxs-lookup"><span data-stu-id="b234f-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="b234f-104">In questa lezione come origine dati verrà utilizzato il database di esempio [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b234f-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="b234f-105">In questa esercitazione si presuppone che il database si trovi in un'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] installata nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b234f-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="b234f-106">Per impostare una connessione</span><span class="sxs-lookup"><span data-stu-id="b234f-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="b234f-107">Nel riquadro **dei dati del report** fare clic su **nuovo** e quindi su **origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b234f-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b234f-108">Se il riquadro **Dati report** non è visualizzato, scegliere **Dati report** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="b234f-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="b234f-109">In **Nome**digitare [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b234f-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="b234f-110">Accertarsi che sia selezionata l'opzione **Connessione incorporata** .</span><span class="sxs-lookup"><span data-stu-id="b234f-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="b234f-111">In **Tipo**selezionare **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b234f-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="b234f-112">In **Stringa di connessione**digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b234f-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="b234f-113">Per questa stringa di connessione si presuppone che [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], il server di report e il database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] siano installati nel computer locale e che si disponga dell'autorizzazione per l'accesso al database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b234f-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b234f-114">Se si utilizza [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services oppure un'istanza denominata, è necessario includere nella stringa di connessione le informazioni sull'istanza:</span><span class="sxs-lookup"><span data-stu-id="b234f-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="b234f-115">Per ulteriori informazioni sulle stringhe di connessione, vedere [connessioni dati, origini dati e stringhe di connessione in Reporting Services e nella](data-connections-data-sources-and-connection-strings-in-reporting-services.md) finestra di [dialogo Proprietà origine dati, generale](data-source-properties-dialog-box-general.md).</span><span class="sxs-lookup"><span data-stu-id="b234f-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="b234f-116">Fare clic su **Credenziali** nel riquadro sinistro e selezionare **Usa autenticazione di Windows (sicurezza integrata)**.</span><span class="sxs-lookup"><span data-stu-id="b234f-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="b234f-117">l'origine dati [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] viene aggiunta al riquadro **dei dati del report** .</span><span class="sxs-lookup"><span data-stu-id="b234f-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="b234f-118">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="b234f-118">Next Task</span></span>  
 <span data-ttu-id="b234f-119">È stata definita correttamente una connessione al database di esempio [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b234f-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="b234f-120">Verrà successivamente creato il report.</span><span class="sxs-lookup"><span data-stu-id="b234f-120">Next, you will create the report.</span></span> <span data-ttu-id="b234f-121">Vedere [Lezione 3: Definizione di un set di dati per il report tabella &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b234f-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b234f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b234f-122">See Also</span></span>  
 [<span data-ttu-id="b234f-123">Connessioni dati, origini dati e stringhe di connessione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b234f-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
