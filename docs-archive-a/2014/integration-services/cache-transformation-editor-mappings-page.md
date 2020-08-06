---
title: Editor trasformazione cache (pagina mapping) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636362"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="fa4af-102">Editor trasformazione cache (pagina Mapping)</span><span class="sxs-lookup"><span data-stu-id="fa4af-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="fa4af-103">Utilizzare la pagina **Mapping** di **Editor trasformazione cache** per eseguire il mapping delle colonne di input nella trasformazione Trasformazione cache alle colonne di destinazione nella gestione connessione della cache.</span><span class="sxs-lookup"><span data-stu-id="fa4af-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa4af-104">È necessario eseguire il mapping di ogni colonna di input a una colonna di destinazione e i tipi di dati di colonna devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="fa4af-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="fa4af-105">In caso contrario, in Progettazione [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="fa4af-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="fa4af-106">Per ulteriori informazioni sulla Trasformazione cache, vedere [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="fa4af-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="fa4af-107">Per ulteriori informazioni sulla gestione connessione cache, vedere [cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fa4af-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa4af-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fa4af-108">Options</span></span>  
 <span data-ttu-id="fa4af-109">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="fa4af-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="fa4af-110">Consente di visualizzare l'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="fa4af-110">View the list of available input columns.</span></span> <span data-ttu-id="fa4af-111">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di input disponibili e le colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fa4af-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="fa4af-112">È anche possibile eseguire il mapping delle colonne di input alle colonne di destinazione mediante la tastiera, evidenziando una colonna nella tabella **Colonne di input disponibili** , premendo il tasto MENU, quindi selezionando **Mappa elementi tramite corrispondenza nomi**.</span><span class="sxs-lookup"><span data-stu-id="fa4af-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="fa4af-113">**Colonne di destinazione disponibili**</span><span class="sxs-lookup"><span data-stu-id="fa4af-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="fa4af-114">Consente di visualizzare l'elenco delle colonne di destinazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="fa4af-114">View the list of available destination columns.</span></span> <span data-ttu-id="fa4af-115">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di destinazione disponibili e le colonne di input.</span><span class="sxs-lookup"><span data-stu-id="fa4af-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="fa4af-116">È anche possibile eseguire il mapping delle colonne di input alle colonne di destinazione mediante la tastiera, evidenziando una colonna nella tabella **Colonne di destinazione disponibili** , premendo il tasto MENU, quindi selezionando **Mappa elementi tramite corrispondenza nomi**.</span><span class="sxs-lookup"><span data-stu-id="fa4af-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="fa4af-117">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="fa4af-117">**Input Column**</span></span>  
 <span data-ttu-id="fa4af-118">Consente di visualizzare le colonne di input selezionate più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="fa4af-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="fa4af-119">È possibile modificare i mapping utilizzando l'elenco **Colonne di input disponibili**.</span><span class="sxs-lookup"><span data-stu-id="fa4af-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="fa4af-120">**Colonna di destinazione**</span><span class="sxs-lookup"><span data-stu-id="fa4af-120">**Destination Column**</span></span>  
 <span data-ttu-id="fa4af-121">Consente di visualizzare le colonne di destinazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="fa4af-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4af-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa4af-122">See Also</span></span>  
 [<span data-ttu-id="fa4af-123">Editor trasformazione cache &#40;pagina Gestione connessioni&#41;</span><span class="sxs-lookup"><span data-stu-id="fa4af-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
