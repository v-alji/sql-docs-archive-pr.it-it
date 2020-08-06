---
title: Modificare le stored procedure che utilizzano proprietà della ricerca full-text obsolete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628177"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="e66c7-102">Modificare le stored procedure che utilizzano proprietà della ricerca full-text obsolete</span><span class="sxs-lookup"><span data-stu-id="e66c7-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="e66c7-103">Per garantire la corretta esecuzione delle stored procedure, modificare le procedure esistenti e rimuovere le proprietà e le impostazioni relative alla ricerca full-text che sono state rimosse o deprecate.</span><span class="sxs-lookup"><span data-stu-id="e66c7-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e66c7-104">Componente</span><span class="sxs-lookup"><span data-stu-id="e66c7-104">Component</span></span>  
 <span data-ttu-id="e66c7-105">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="e66c7-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="e66c7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e66c7-106">Description</span></span>  
 <span data-ttu-id="e66c7-107">Le seguenti proprietà e impostazioni relative alla ricerca full-text sono state rimosse.</span><span class="sxs-lookup"><span data-stu-id="e66c7-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="e66c7-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="e66c7-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="e66c7-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="e66c7-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="e66c7-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="e66c7-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="e66c7-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="e66c7-111">**LogSize**</span></span>  
  
 <span data-ttu-id="e66c7-112">Le seguenti proprietà e impostazioni relative alla ricerca full-text sono state rimosse o deprecate:</span><span class="sxs-lookup"><span data-stu-id="e66c7-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="e66c7-113">Percorso del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="e66c7-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="e66c7-114">Il catalogo full-text è un oggetto logico senza un percorso di file specifico nel sistema.</span><span class="sxs-lookup"><span data-stu-id="e66c7-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="e66c7-115">L'attivazione/disabilitazione in SP_FULLTEXT_DATABASE non ha più effetto, poiché i database sono sempre attivati per la ricerca full-text e per impostazione predefinita in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e66c7-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e66c7-116">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="e66c7-116">Corrective Action</span></span>  
 <span data-ttu-id="e66c7-117">Modificare le stored procedure per rimuovere queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="e66c7-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66c7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e66c7-118">See Also</span></span>  
 [<span data-ttu-id="e66c7-119">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e66c7-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
