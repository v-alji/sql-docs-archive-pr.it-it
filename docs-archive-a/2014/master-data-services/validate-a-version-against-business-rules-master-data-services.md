---
title: Convalidare una versione rispetto a regole business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627864"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="2e605-102">Convalidare una versione rispetto a regole business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2e605-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="2e605-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]convalidare una versione per applicare regole di business a tutti i membri nella versione del modello.</span><span class="sxs-lookup"><span data-stu-id="2e605-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="2e605-104">In questa procedura viene illustrato come usare l'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per convalidare i dati.</span><span class="sxs-lookup"><span data-stu-id="2e605-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="2e605-105">Se si dispone dell'autorizzazione nel database MDS, è possibile utilizzare una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2e605-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="2e605-106">Per altre informazioni, vedere [Stored procedure di convalida &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e605-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e605-107">Tutti i membri devono superare la convalida prima che possa essere eseguito il commit di una versione.</span><span class="sxs-lookup"><span data-stu-id="2e605-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e605-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2e605-108">Prerequisites</span></span>  
 <span data-ttu-id="2e605-109">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="2e605-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2e605-110">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="2e605-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="2e605-111">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="2e605-111">You must be a model administrator.</span></span> <span data-ttu-id="2e605-112">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2e605-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2e605-113">Lo stato della versione deve essere **Aperto** o **Bloccato**.</span><span class="sxs-lookup"><span data-stu-id="2e605-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="2e605-114">Nella pagina **Convalida versioni** devono essere presenti membri con uno stato diverso da **Convalida completata**.</span><span class="sxs-lookup"><span data-stu-id="2e605-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="2e605-115">Per convalidare una versione</span><span class="sxs-lookup"><span data-stu-id="2e605-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="2e605-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Gestione versioni**.</span><span class="sxs-lookup"><span data-stu-id="2e605-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="2e605-117">Nella pagina **Gestisci versioni** scegliere **Convalida versione**dalla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="2e605-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="2e605-118">Nella pagina **Convalida versioni** selezionare il modello e la versione che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="2e605-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="2e605-119">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="2e605-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="2e605-120">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e605-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e605-121">Quando non è più visualizzato l'indicatore di stato, la versione ha terminato la convalida.</span><span class="sxs-lookup"><span data-stu-id="2e605-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2e605-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2e605-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="2e605-123">Bloccare una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2e605-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e605-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e605-124">See Also</span></span>  
 <span data-ttu-id="2e605-125">[Stati di convalida &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e605-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="2e605-126">[&#40;della stored procedure di convalida Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e605-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="2e605-127">[Versioni &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e605-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="2e605-128">[Regole business &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2e605-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="2e605-129">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2e605-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  
