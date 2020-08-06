---
title: Pubblicazione di un database (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627803"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="98d9d-102">Pubblicazione di un database (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="98d9d-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="98d9d-103">È possibile utilizzare la procedura guidata **Genera e pubblica script** per pubblicare un database intero o singoli oggetti di database in un provider di hosting Web remoto.</span><span class="sxs-lookup"><span data-stu-id="98d9d-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98d9d-104">La funzionalità descritta in questo argomento era fornita da Pubblicazione guidata database.</span><span class="sxs-lookup"><span data-stu-id="98d9d-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="98d9d-105">Poiché la funzionalità di pubblicazione è stata aggiunta alla procedura guidata Genera e pubblica script, la procedura Pubblicazione guidata database non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="98d9d-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="98d9d-106">Genera e pubblica script</span><span class="sxs-lookup"><span data-stu-id="98d9d-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="98d9d-107">La procedura guidata Genera e pubblica script consente di pubblicare un database oppure oggetti di database selezionati su un provider di hosting Web.</span><span class="sxs-lookup"><span data-stu-id="98d9d-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="98d9d-108">Un provider di hosting Web di SQL Server è un'interfaccia di connettività a un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="98d9d-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="98d9d-109">Il servizio Web viene creato tramite il progetto Database Publishing Service in SQL Server Hosting Toolkit su CodePlex.</span><span class="sxs-lookup"><span data-stu-id="98d9d-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="98d9d-110">Il servizio Web facilita la pubblicazione nel servizio dei database dei clienti dell'hoster Web tramite la procedura guidata Genera e pubblica script.</span><span class="sxs-lookup"><span data-stu-id="98d9d-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="98d9d-111">Per altre informazioni sul download di SQL Server Hosting Toolkit, vedere [Database Publishing Services di SQL Server](https://go.microsoft.com/fwlink/?LinkId=142025).</span><span class="sxs-lookup"><span data-stu-id="98d9d-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="98d9d-112">È inoltre possibile utilizzare la procedura guidata Genera e pubblica script per creare uno script per il trasferimento di un database.</span><span class="sxs-lookup"><span data-stu-id="98d9d-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="98d9d-113">Per pubblicare un database su un servizio Web</span><span class="sxs-lookup"><span data-stu-id="98d9d-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="98d9d-114">In Esplora oggetti, espandere **Database**, fare clic con il pulsante destro del mouse su un database, scegliere **Attività**, quindi fare clic su **Genera e pubblica script**.</span><span class="sxs-lookup"><span data-stu-id="98d9d-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="98d9d-115">Per creare script per gli oggetti di database da pubblicare, seguire i passaggi della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="98d9d-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="98d9d-116">Nella pagina **Seleziona oggetti** selezionare gli oggetti da pubblicare sul servizio di hosting Web.</span><span class="sxs-lookup"><span data-stu-id="98d9d-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="98d9d-117">Nella pagina **Imposta opzioni di generazione script** selezionare **Pubblica su servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="98d9d-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="98d9d-118">Nella casella **Provider** specificare il provider per il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="98d9d-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="98d9d-119">Se non è stato configurato un provider di hosting Web, selezionare **Gestisci provider** e utilizzare la finestra di dialogo **Gestisci provider** per configurare un provider per il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="98d9d-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="98d9d-120">Per specificare opzioni di pubblicazione avanzate, selezionare il pulsante **Avanzate** nella sezione **Pubblica su servizio Web** .</span><span class="sxs-lookup"><span data-stu-id="98d9d-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="98d9d-121">Controllare le selezioni effettuate nella pagina **Riepilogo** .</span><span class="sxs-lookup"><span data-stu-id="98d9d-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="98d9d-122">Fare clic su **Indietro** per modificare le selezioni.</span><span class="sxs-lookup"><span data-stu-id="98d9d-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="98d9d-123">Fare clic su **Avanti** per pubblicare gli oggetti selezionati.</span><span class="sxs-lookup"><span data-stu-id="98d9d-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="98d9d-124">Monitorare lo stato di pubblicazione nella pagina **Salva o pubblica script** .</span><span class="sxs-lookup"><span data-stu-id="98d9d-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d9d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98d9d-125">See Also</span></span>  
 <span data-ttu-id="98d9d-126">[Generazione di script &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="98d9d-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="98d9d-127">Copiare database in altri server</span><span class="sxs-lookup"><span data-stu-id="98d9d-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
