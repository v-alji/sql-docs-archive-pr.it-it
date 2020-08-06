---
title: Definire chiavi primarie logiche in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629093"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="74cb9-102">Definire chiavi primarie logiche in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="74cb9-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="74cb9-103">La Creazione guidata vista origine dati e Progettazione vista origine dati consentono di definire automaticamente una chiave primaria per una tabella che viene aggiunta a una vista origine dati in base alla tabella di database sottostante.</span><span class="sxs-lookup"><span data-stu-id="74cb9-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="74cb9-104">Talvolta, può essere necessario definire manualmente una chiave primaria nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="74cb9-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="74cb9-105">Ad esempio, per motivi correlati alle prestazioni o alla progettazione, nelle tabelle di un'origine dati potrebbero non essere incluse colonne chiave primarie definite in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="74cb9-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="74cb9-106">La colonna chiave primaria per una tabella può inoltre essere omessa in viste e query denominate.</span><span class="sxs-lookup"><span data-stu-id="74cb9-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="74cb9-107">Se in una tabella, in una vista o in una query denominata non è inclusa una chiave primaria fisica definita, è possibile definire manualmente una chiave primaria logica tramite Progettazione vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="74cb9-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="74cb9-108">Impostare una chiave primaria logica</span><span class="sxs-lookup"><span data-stu-id="74cb9-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="74cb9-109">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] le chiavi primarie sono necessarie per identificare in modo univoco i record in una tabella, identificare le colonne chiave nelle tabelle delle dimensioni e supportare le relazioni tra tabelle, viste e query denominate.</span><span class="sxs-lookup"><span data-stu-id="74cb9-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="74cb9-110">Tali relazioni vengono utilizzate per costruire query per il recupero di dati e metadati dalle origini dati sottostanti e per sfruttare caratteristiche avanzate di Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="74cb9-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="74cb9-111">Per la chiave primaria logica è possibile utilizzare qualsiasi colonna, incluso un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="74cb9-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="74cb9-112">Durante la creazione di una chiave primaria logica, nella vista origine dati viene creato un vincolo UNIQUE contrassegnato come vincolo di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="74cb9-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="74cb9-113">Ogni altra chiave primaria logica esistente specificata nella tabella selezionata verrà eliminata.</span><span class="sxs-lookup"><span data-stu-id="74cb9-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="74cb9-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si desidera impostare una chiave primaria logica.</span><span class="sxs-lookup"><span data-stu-id="74cb9-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="74cb9-115">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="74cb9-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="74cb9-116">Per individuare una tabella o una vista, è possibile utilizzare l'opzione **Trova tabella** facendo clic sul menu **vista origine dati** o facendo clic con il pulsante destro del mouse su un'area aperta dei riquadri **tabelle** o **diagramma** .</span><span class="sxs-lookup"><span data-stu-id="74cb9-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="74cb9-117">Nel riquadro **Tabelle** o **Diagramma** fare clic con il pulsante destro del mouse sulle colonne da usare per definire una chiave primaria logica, quindi scegliere **Imposta chiave primaria logica**.</span><span class="sxs-lookup"><span data-stu-id="74cb9-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="74cb9-118">L'opzione per impostare una chiave primaria logica è disponibile solo per le tabelle in cui non è inclusa alcuna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="74cb9-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="74cb9-119">Una volta impostata la chiave, le colonne chiave primaria saranno identificate da un'icona a forma di chiave.</span><span class="sxs-lookup"><span data-stu-id="74cb9-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cb9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74cb9-120">See Also</span></span>  
 <span data-ttu-id="74cb9-121">[Viste origine dati in modelli multidimensionali](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="74cb9-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="74cb9-122">Definire calcoli denominati in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="74cb9-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
