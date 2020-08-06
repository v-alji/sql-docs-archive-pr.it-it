---
title: Gestione delle modifiche apportate alle viste origine dati e alle origini dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714648"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="fe1b5-102">Gestire modifiche a viste origine dati e origini dati</span><span class="sxs-lookup"><span data-stu-id="fe1b5-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="fe1b5-103">Quando si riesegue la Generazione guidata schema, vengono riutilizzate la stessa origine dei dati e la stessa vista origine dati utilizzate durante la generazione originale.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="fe1b5-104">Se si aggiunge un'origine dei dati oppure una vista origine dati, il nuovo elemento verrà ignorato dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="fe1b5-105">Se si elimina l'origine dei dati o la vista origine dati originale dopo la generazione iniziale, sarà necessario eseguire la procedura guidata dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="fe1b5-106">Verranno inoltre eliminate tutte le impostazioni precedenti della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="fe1b5-107">Tutti gli oggetti esistenti in un database sottostante associati a un'origine dei dati o una vista origine dati eliminata verranno considerati come oggetti creati dall'utente durante la successiva esecuzione della Generazione guidata schema.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="fe1b5-108">Se la vista origine dati non riflette lo stato effettivo del database sottostante al momento della generazione, è possibile che nella Generazione guidata schema vengano rilevati errori durante la generazione dello schema del database dell'area di interesse.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="fe1b5-109">Se il tipo di dati specificato per una colonna nella vista origine dati è **int**ma il tipo di dati effettivo della colonna è **string**, ad esempio, il tipo di dati per la chiave esterna verrà impostato nella Generazione guidata schema su **INT** in conformità con la vista origine dati e si verificherà quindi un errore durante la creazione della relazione poiché il tipo effettivo è **string**.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="fe1b5-110">Se invece si modifica la stringa di connessione dell'origine dei dati impostando un database diverso rispetto alla generazione precedente, non verrà generato alcun errore.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="fe1b5-111">Verrà utilizzato il nuovo database senza alcuna modifica al database precedente.</span><span class="sxs-lookup"><span data-stu-id="fe1b5-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1b5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe1b5-112">See Also</span></span>  
 [<span data-ttu-id="fe1b5-113">Informazioni sulla generazione incrementale</span><span class="sxs-lookup"><span data-stu-id="fe1b5-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  
