---
title: Stored procedure di gestione temporanea (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637956"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="0a950-102">Stored procedure di gestione temporanea (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a950-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="0a950-103">Quando si inizia il processo di gestione temporanea da [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], viene usata una delle tre stored procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="0a950-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="0a950-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="0a950-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="0a950-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="0a950-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="0a950-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="0a950-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="0a950-107">Dove name è il nome della tabella di staging specificata alla creazione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="0a950-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="0a950-108">Parametri delle stored procedure del processo di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="0a950-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="0a950-109">Nella tabella seguente vengono elencati i parametri di queste stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0a950-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="0a950-110">Parametro</span><span class="sxs-lookup"><span data-stu-id="0a950-110">Parameter</span></span>|<span data-ttu-id="0a950-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a950-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a950-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="0a950-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="0a950-113">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="0a950-113">Required</span></span>|<span data-ttu-id="0a950-114">Il nome della versione.</span><span class="sxs-lookup"><span data-stu-id="0a950-114">The name of the version.</span></span> <span data-ttu-id="0a950-115">Può supportare o non supportare la distinzione tra maiuscole e minuscole, a seconda dell'impostazione delle regole di confronto di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a950-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="0a950-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="0a950-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="0a950-117">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="0a950-117">Required</span></span>|<span data-ttu-id="0a950-118">Determina se le transazioni sono registrate durante il processo di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="0a950-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="0a950-119">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="0a950-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="0a950-120">**0**: le transazioni non vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="0a950-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="0a950-121">**1**: le transazioni vengono registrate.</span><span class="sxs-lookup"><span data-stu-id="0a950-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="0a950-122">Per altre informazioni sulle transazioni, vedere [Transazioni &#40;Master Data Services&#41;](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a950-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="0a950-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="0a950-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="0a950-124">Richiesto, salvo che dal servizio Web</span><span class="sxs-lookup"><span data-stu-id="0a950-124">Required, except by web service</span></span>|<span data-ttu-id="0a950-125">Il valore **BatchTag** come specificato nella tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="0a950-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="0a950-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="0a950-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="0a950-127">Richiesto solo dal servizio Web</span><span class="sxs-lookup"><span data-stu-id="0a950-127">Required by web service only</span></span>|<span data-ttu-id="0a950-128">Il valore **Batch_ID** come specificato nella tabella di staging.</span><span class="sxs-lookup"><span data-stu-id="0a950-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="0a950-129">Esempio di stored procedure del processo di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="0a950-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="0a950-130">Nell'esempio seguente viene illustrata la modalità di inizio del processo di gestione temporanea mediante una stored procedure di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="0a950-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a950-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a950-131">See Also</span></span>  
 <span data-ttu-id="0a950-132">[&#40;della stored procedure di convalida Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a950-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="0a950-133">[Caricare o aggiornare membri in Master Data Services tramite il processo di gestione temporanea](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a950-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="0a950-134">Visualizzare gli errori che si verificano durante il processo di gestione temporanea &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a950-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  
