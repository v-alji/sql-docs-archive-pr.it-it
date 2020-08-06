---
title: Set di righe dello schema modificati per i parametri con valori di tabella OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723760"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="7974f-102">Set di righe dello schema modificati per i parametri con valori di tabella OLE DB</span><span class="sxs-lookup"><span data-stu-id="7974f-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="7974f-103">Di seguito sono elencati i set di righe dello schema che sono stati modificati o aggiunti per il supporto dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="7974f-104">Set di righe dello schema</span><span class="sxs-lookup"><span data-stu-id="7974f-104">Schema rowset</span></span>|<span data-ttu-id="7974f-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7974f-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="7974f-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7974f-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="7974f-107">Alla fine del set di righe sono state aggiunte due nuove colonne denominate SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMANAME.</span><span class="sxs-lookup"><span data-stu-id="7974f-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="7974f-108">Tali colonne potrebbero essere riutilizzate per i tipi futuri.</span><span class="sxs-lookup"><span data-stu-id="7974f-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="7974f-109">Le colonne TYPE_NAME e LOCAL_TYPE_NAME conterranno il nome del tipo TABLE dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="7974f-110">La colonna DATA_TYPE avrà il valore DBTYPE_TABLE = 143 per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="7974f-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="7974f-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="7974f-112">Questo set di righe è stato aggiunto per supportare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7974f-113">È identico a DBSCHEMA_TABLES, con l'eccezione che restituisce metadati solo per i tipi di tabella, anziché per tabelle, viste o sinonimi.</span><span class="sxs-lookup"><span data-stu-id="7974f-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="7974f-114">La colonna TABLE_TYPE avrà il valore TABLE TYPE.</span><span class="sxs-lookup"><span data-stu-id="7974f-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="7974f-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="7974f-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="7974f-116">Questo set di righe è stato aggiunto per supportare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7974f-117">È identico a DBSCHEMA_PRIMARY_KEYS, con l'eccezione che restituisce chiavi primarie solo per i tipi di tabella, anziché per tabelle, viste o sinonimi.</span><span class="sxs-lookup"><span data-stu-id="7974f-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="7974f-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="7974f-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="7974f-119">Questo set di righe è stato aggiunto per supportare i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="7974f-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="7974f-120">È identico a DBSCHEMA_COLUMNS, con l'eccezione che restituisce metadati di colonna solo per i tipi di tabella, anziché per tabelle, viste o sinonimi.</span><span class="sxs-lookup"><span data-stu-id="7974f-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7974f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7974f-121">See Also</span></span>  
 <span data-ttu-id="7974f-122">[Parametri con valori di tabella &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7974f-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="7974f-123">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7974f-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
