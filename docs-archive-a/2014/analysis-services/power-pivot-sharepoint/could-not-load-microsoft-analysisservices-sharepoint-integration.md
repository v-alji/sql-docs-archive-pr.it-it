---
title: Impossibile caricare il file o l'assembly &#39;Microsoft. Data. Services, Version = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; o una delle relative dipendenze. Non è possibile trovare il file specificato. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635795"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="ecada-104">Impossibile caricare il file o l'assembly &#39;Microsoft. Data. Services, Version = 3.5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; o una delle relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="ecada-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="ecada-105">Non è possibile trovare il file specificato.</span><span class="sxs-lookup"><span data-stu-id="ecada-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="ecada-106">Negli ambienti di SharePoint 2010 in cui è disponibile PowerPivot per SharePoint, questo errore si verificherà se si tenta un'esportazione del feed di dati e nel sistema non è presente la versione richiesta di Microsoft ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="ecada-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ecada-107">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ecada-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecada-108">Si applica a</span><span class="sxs-lookup"><span data-stu-id="ecada-108">Applies to</span></span>|<span data-ttu-id="ecada-109">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="ecada-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="ecada-110">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="ecada-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="ecada-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecada-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="ecada-112">Causa</span><span class="sxs-lookup"><span data-stu-id="ecada-112">Cause</span></span>|<span data-ttu-id="ecada-113">Impossibile trovare ADO.NET Data Services 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="ecada-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="ecada-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ecada-114">Message Text</span></span>|<span data-ttu-id="ecada-115">Impossibile caricare il file o l'assembly "Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral PublicKeyToken=b77a5c561934e089" o una delle relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="ecada-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="ecada-116">Impossibile trovare il file specificato</span><span class="sxs-lookup"><span data-stu-id="ecada-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecada-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ecada-117">Explanation</span></span>  
 <span data-ttu-id="ecada-118">In SharePoint 2010 è incluso un pulsante Esporta come feed di dati che può essere utilizzato per esportare un elenco SharePoint come feed di dati XML.</span><span class="sxs-lookup"><span data-stu-id="ecada-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="ecada-119">Inoltre, sia Reporting Services in modalità SharePoint sia PowerPivot per SharePoint supportano le funzionalità del feed di dati che richiedono ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="ecada-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="ecada-120">Se ADO.NET Data Services non è installato, questo errore si verificherà quando si richiede un feed di dati.</span><span class="sxs-lookup"><span data-stu-id="ecada-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecada-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ecada-121">User Action</span></span>  
  
1.  <span data-ttu-id="ecada-122">Passare alla documentazione relativa ai requisiti hardware e software per SharePoint 2010, [determinare i requisiti hardware e software (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="ecada-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="ecada-123">Nella sezione relativa ai **prerequisiti software di installazione**cercare il collegamento per ADO.NET Data Services 3.5 che corrisponde al sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="ecada-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="ecada-124">Fare clic sul collegamento ed eseguire il programma di installazione che consente di installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="ecada-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecada-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecada-125">See Also</span></span>  
 [<span data-ttu-id="ecada-126">Distribuire soluzioni PowerPivot in SharePoint</span><span class="sxs-lookup"><span data-stu-id="ecada-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
