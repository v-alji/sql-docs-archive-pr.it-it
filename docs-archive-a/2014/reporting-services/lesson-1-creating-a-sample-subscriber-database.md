---
title: 'Lesson 1: Creating a Sample Subscriber Database (Lezione 1: Creazione di un database di esempio del Sottoscrittore) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6ee49f0858b28c0c4b00fd391b0db7b4d2c54b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726591"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a><span data-ttu-id="58306-102">Lezione 1: Creazione di un database di esempio del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="58306-102">Lesson 1: Creating a Sample Subscriber Database</span></span>
  <span data-ttu-id="58306-103">Prima di definire una sottoscrizione guidata dai dati è necessario disporre di un'origine dei dati contenente i dati della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="58306-103">Before you can define a data-driven subscription, you must have a data source that provides subscription data.</span></span> <span data-ttu-id="58306-104">In questo passaggio vengono illustrate le procedure per la creazione di un piccolo database per archiviare i dati della sottoscrizione utilizzati in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="58306-104">In this step, you will create a small database to store the subscription data used in this tutorial.</span></span> <span data-ttu-id="58306-105">Successivamente, quando la sottoscrizione viene elaborata, tramite il server di report vengono recuperati i dati e utilizzati per personalizzare l'output di report, le opzioni di recapito e il formato di presentazione del report.</span><span class="sxs-lookup"><span data-stu-id="58306-105">Later, when the subscription is processed, the report server retrieves this data and uses it to customize report output, delivery options, and report presentation format.</span></span>  
  
 <span data-ttu-id="58306-106">In questa lezione si presuppone che si usi [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per creare un [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="58306-106">This lesson assumes you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to create a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span>  
  
### <a name="to-create-a-sample-subscriber-database"></a><span data-ttu-id="58306-107">Per creare un database di esempio del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="58306-107">To create a sample Subscriber database</span></span>  
  
1.  <span data-ttu-id="58306-108">Avviare [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e stabilire una connessione a un [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58306-108">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="58306-109">Fare clic con il pulsante destro del mouse su Database, quindi scegliere **Nuovo database**.</span><span class="sxs-lookup"><span data-stu-id="58306-109">Right-click on Databases, select **New Database...**.</span></span>  
  
3.  <span data-ttu-id="58306-110">Nella finestra di dialogo nuovo database digitare *sottoscrittori*in nome database.</span><span class="sxs-lookup"><span data-stu-id="58306-110">In the New Database dialog box, in Database Name, type *Subscribers*.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="58306-111">Fare clic sul pulsante **Nuova query** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="58306-111">Click the **New Query** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="58306-112">Copiare le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] seguenti nella query vuota:</span><span class="sxs-lookup"><span data-stu-id="58306-112">Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:</span></span>  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  <span data-ttu-id="58306-113">Fare clic su **Esegui** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="58306-113">Click **! Execute** on the toolbar.</span></span>  
  
7.  <span data-ttu-id="58306-114">Utilizzare un'istruzione SELECT per verificare che siano disponibili tre righe di dati.</span><span class="sxs-lookup"><span data-stu-id="58306-114">Use a SELECT statement to verify that you have three rows of data.</span></span> <span data-ttu-id="58306-115">Ad esempio: `select * from OrderInfo`</span><span class="sxs-lookup"><span data-stu-id="58306-115">For example: `select * from OrderInfo`</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="58306-116">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="58306-116">Next Steps</span></span>  
 <span data-ttu-id="58306-117">In tal modo sono stati creati i dati di sottoscrizione per la distribuzione dei report e per la variazione dell'output del report per ogni sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="58306-117">You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber.</span></span> <span data-ttu-id="58306-118">Sarà quindi possibile modificare le proprietà dell'origine dei dati del report da distribuire ai sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="58306-118">Next, you will modify the data source properties of the report you will distribute to subscribers.</span></span> <span data-ttu-id="58306-119">La modifica delle proprietà dell'origine dei dati viene eseguita per preparare il report per il recapito delle sottoscrizioni guidate dai dati.</span><span class="sxs-lookup"><span data-stu-id="58306-119">Modifying the data source properties is done to prepare the report for data-driven subscription delivery.</span></span> <span data-ttu-id="58306-120">Inoltre, verrà modificata la progettazione report per includere un parametro che verrà utilizzato dalla sottoscrizione con i dati del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="58306-120">You will also modify the report design to include a parameter that the subscription will use with the subscriber data.</span></span> <span data-ttu-id="58306-121">[Lezione 2: modifica delle proprietà dell'origine dati del report](lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="58306-121">[Lesson 2: Modifying the Report Data Source Properties](lesson-2-modifying-the-report-data-source-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58306-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58306-122">See Also</span></span>  
 <span data-ttu-id="58306-123">[Creare una sottoscrizione guidata dai dati &#40;esercitazione su SSRS&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="58306-123">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="58306-124">[Creazione di un database](../relational-databases/databases/create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="58306-124">[Create a Database](../relational-databases/databases/create-a-database.md) </span></span>  
 [<span data-ttu-id="58306-125">Creare un report tabella semplice &#40;esercitazione su SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="58306-125">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
