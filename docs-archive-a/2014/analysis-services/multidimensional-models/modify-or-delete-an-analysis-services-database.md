---
title: Modificare o eliminare un database di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724264"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="cd233-102">Modificare o eliminare un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd233-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="cd233-103">È possibile modificare il nome e la descrizione di un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] prima della distribuzione in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e dopo la distribuzione in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd233-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cd233-104">A seconda dell'ambiente di lavoro, è inoltre possibile modificare altre impostazioni di un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd233-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd233-105">Le proprietà del database tuttavia non possono essere modificate quando [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] è nella modalità online.</span><span class="sxs-lookup"><span data-stu-id="cd233-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="cd233-106">Modifica di databases tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cd233-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="cd233-107">Dopo la distribuzione di un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] è possibile modificare la modalità di rappresentazione utilizzata da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] durante la connessione alle origini dei dati contenute nel database.</span><span class="sxs-lookup"><span data-stu-id="cd233-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="cd233-108">Nella modalità di rappresentazione è possibile specificare il contesto di sicurezza utilizzato da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nei tentativi di connessione a un'origine dati a scopo di elaborazione, esplorazione e drill-through.</span><span class="sxs-lookup"><span data-stu-id="cd233-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="cd233-109">Modifica di database tramite SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="cd233-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="cd233-110">È possibile usare [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] nella modalità progetto per modificare le traduzioni della didascalia e della descrizione di un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usato per definire un database.</span><span class="sxs-lookup"><span data-stu-id="cd233-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="cd233-111">Per ulteriori informazioni sull'utilizzo delle traduzioni in un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, vedere [scenari di globalizzazione per Analysis Services multidimensionale](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="cd233-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="cd233-112">È inoltre possibile impostare gli alias e le funzioni di aggregazione associate ai tipi di conto utilizzati dagli attributi Conto nelle dimensioni incluse in un database.</span><span class="sxs-lookup"><span data-stu-id="cd233-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="cd233-113">Gli alias consentono di selezionare la terminologia aziendale specifica utilizzata all'interno di un'organizzazione per i tipi di conto in un grafico dei conti.</span><span class="sxs-lookup"><span data-stu-id="cd233-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="cd233-114">I tipi di conto vengono utilizzati dai membri di un attributo Conto per indicare la modalità di aggregazione delle misure per ogni membro tramite le funzioni di aggregazione specificate per ogni tipo di conto incluso nel database.</span><span class="sxs-lookup"><span data-stu-id="cd233-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="cd233-115">Per altre informazioni sugli attributi dell'account, vedere [Attributi e gerarchie di attributi](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="cd233-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="cd233-116">eliminazione di database</span><span class="sxs-lookup"><span data-stu-id="cd233-116">Deleting Databases</span></span>  
 <span data-ttu-id="cd233-117">Quando si elimina un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esistente vengono eliminati anche tutti i cubi, le dimensioni e i modelli di data mining del database.</span><span class="sxs-lookup"><span data-stu-id="cd233-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="cd233-118">È possibile eliminare solo un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] esistente in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd233-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="cd233-119">Per eliminare un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd233-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="cd233-120">Connettersi a un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd233-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="cd233-121">In **Esplora oggetti**espandere il nodo dell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connessa e verificare che l'oggetto da eliminare sia visibile.</span><span class="sxs-lookup"><span data-stu-id="cd233-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="cd233-122">Fare clic con il pulsante destro del mouse sull'oggetto da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cd233-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="cd233-123">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd233-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd233-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd233-124">See Also</span></span>  
 [<span data-ttu-id="cd233-125">Documentazione e script per un database di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cd233-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
