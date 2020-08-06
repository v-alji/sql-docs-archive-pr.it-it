---
title: Stored procedure di convalida (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628771"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="9b1b9-102">Stored procedure di convalida (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9b1b9-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="9b1b9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]convalidare una versione per applicare regole di business a tutti i membri nella versione del modello.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="9b1b9-104">In questo argomento viene illustrato come usare la stored procedure **mdm.udpValidateModel** per convalidare i dati.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="9b1b9-105">Se si è un amministratore nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , è possibile eseguire la convalida nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="9b1b9-106">Per altre informazioni, vedere [Convalidare una versione usando le regole di business &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b1b9-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b1b9-107">Se si richiama la convalida prima del completamento del processo di gestione temporanea, i membri che non hanno completato la gestione temporanea non saranno convalidati.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b1b9-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b1b9-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b1b9-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b1b9-109">Parameters</span></span>  
 <span data-ttu-id="9b1b9-110">I parametri di questa procedura sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b1b9-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="9b1b9-111">Parametro</span><span class="sxs-lookup"><span data-stu-id="9b1b9-111">Parameter</span></span>|<span data-ttu-id="9b1b9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b1b9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b1b9-113">UserID</span><span class="sxs-lookup"><span data-stu-id="9b1b9-113">UserID</span></span>|<span data-ttu-id="9b1b9-114">L'ID utente.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-114">The user ID.</span></span>|  
|<span data-ttu-id="9b1b9-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="9b1b9-115">Model_ID</span></span>|<span data-ttu-id="9b1b9-116">L'ID modello.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-116">The model ID.</span></span>|  
|<span data-ttu-id="9b1b9-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="9b1b9-117">Version_ID</span></span>|<span data-ttu-id="9b1b9-118">L'ID versione.</span><span class="sxs-lookup"><span data-stu-id="9b1b9-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b1b9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b1b9-119">See Also</span></span>  
 <span data-ttu-id="9b1b9-120">[Importazione dati &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9b1b9-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="9b1b9-121">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b1b9-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  
