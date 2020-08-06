---
title: Configurare l'accesso in memoria o DirectQuery per un database modello tabulare | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712520"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="92e67-102">Configurare l'accesso in memoria o DirectQuery per un database di modello tabulare</span><span class="sxs-lookup"><span data-stu-id="92e67-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="92e67-103">In questo argomento viene illustrato come modificare le proprietà di connessione di un modello tabulare che è già stato distribuito, per consentire l'utilizzo del modello in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="92e67-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="92e67-104">Per altre informazioni su queste proprietà e sulla configurazione per gli scenari più comuni, vedere [scenari di distribuzione DirectQuery &#40;SSAS tabulare&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="92e67-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e67-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92e67-105">Requirements</span></span>  
 <span data-ttu-id="92e67-106">L'abilitazione dell'utilizzo della modalità DirectQuery su un modello tabulare è un processo a più passaggi.</span><span class="sxs-lookup"><span data-stu-id="92e67-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="92e67-107">È necessario:</span><span class="sxs-lookup"><span data-stu-id="92e67-107">You must:</span></span>  
  
1.  <span data-ttu-id="92e67-108">Verificare che il modello non disponga di funzionalità che potrebbero provocare errori di convalida in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="92e67-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="92e67-109">Modificare la modalità di archiviazione del modello per supportare DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="92e67-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="92e67-110">Distribuire il modello in una modalità che supporti le query in modalità DirectQuery pura o ibrida.</span><span class="sxs-lookup"><span data-stu-id="92e67-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="92e67-111">Modificare la stringa di connessione nel database distribuito per supportare la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="92e67-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="92e67-112">In questo argomento si presuppone che sia stato creato e convalidato il modello e che occorra soltanto abilitare l'accesso DirectQuery da un client quale [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e67-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="92e67-113">Procedura</span><span class="sxs-lookup"><span data-stu-id="92e67-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="92e67-114">Modificare le proprietà della stringa di connessione del modello</span><span class="sxs-lookup"><span data-stu-id="92e67-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="92e67-115">In SQL Server Management Studio aprire l'istanza in cui distribuire il modello.</span><span class="sxs-lookup"><span data-stu-id="92e67-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="92e67-116">In Esplora oggetti fare clic con il pulsante destro del mouse sul nome del database modello e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="92e67-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="92e67-117">Individuare la proprietà **DirectQueryMode**.</span><span class="sxs-lookup"><span data-stu-id="92e67-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="92e67-118">Per abilitare l'utilizzo dell'origine dati relazionale, è necessario impostare questa proprietà su uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="92e67-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="92e67-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="92e67-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="92e67-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="92e67-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="92e67-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="92e67-121">**DirectQueryWithInMemory**</span></span>  
  
  
