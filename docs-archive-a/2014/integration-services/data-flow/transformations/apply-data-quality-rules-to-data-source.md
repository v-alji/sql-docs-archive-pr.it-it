---
title: Applicare le regole relative alla qualità dei dati all'origine dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712196"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="cd67a-102">Applicazione delle regole relative alla qualità dei dati all'origine dati</span><span class="sxs-lookup"><span data-stu-id="cd67a-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="cd67a-103">È possibile utilizzare Data Quality Services (DQS) per correggere i dati nel flusso di dati del pacchetto connettendo la trasformazione DQS Cleansing all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cd67a-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="cd67a-104">Per altre informazioni su DQS, vedere [Concetti di Data Quality Services](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="cd67a-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="cd67a-105">Per altre informazioni sulla trasformazione, vedere [Trasformazione DQS Cleansing](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cd67a-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="cd67a-106">Quando si elaborano i dati con la trasformazione DQS Cleansing, viene creato un progetto Data Quality nel server Data Quality.</span><span class="sxs-lookup"><span data-stu-id="cd67a-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="cd67a-107">È possibile utilizzare il client Data Quality per gestire il progetto.</span><span class="sxs-lookup"><span data-stu-id="cd67a-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="cd67a-108">Per altre informazioni, vedere [Gestire un progetto Data Quality &#40;apertura, sblocco, ridenominazione ed eliminazione&#41;](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="cd67a-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="cd67a-109">Per correggere i dati nel flusso di dati</span><span class="sxs-lookup"><span data-stu-id="cd67a-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="cd67a-110">Creare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cd67a-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="cd67a-111">Aggiungere e configurare la trasformazione DQS Cleansing.</span><span class="sxs-lookup"><span data-stu-id="cd67a-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="cd67a-112">Per altre informazioni, vedere [Finestra di dialogo Editor trasformazione DQS Cleansing](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="cd67a-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="cd67a-113">Connettere la trasformazione DQS Cleansing a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cd67a-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
