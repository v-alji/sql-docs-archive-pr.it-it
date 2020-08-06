---
title: Editor della risoluzione dei riferimenti alle colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629523"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="47239-102">Editor della risoluzione dei riferimenti alle colonne</span><span class="sxs-lookup"><span data-stu-id="47239-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="47239-103">Quando un percorso di input viene disconnesso o se contiene colonne senza mapping, viene visualizzata un'icona di errore accanto al percorso di dati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="47239-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="47239-104">Per semplificare la risoluzione degli errori di riferimento alle colonne, il nuovo editor per la risoluzione dei riferimenti consente di collegare le colonne di output senza mapping alle colonne di input senza mapping per tutti i percorsi nell'albero di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="47239-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="47239-105">Nell'editor per la risoluzioni dei riferimenti verranno inoltre evidenziati i percorsi risolti.</span><span class="sxs-lookup"><span data-stu-id="47239-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="47239-106">È ora possibile modificare un componente quando il relativo percorso di input è disconnesso</span><span class="sxs-lookup"><span data-stu-id="47239-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="47239-107">Dopo che sono stati risolti tutti i riferimenti alle colonne, in assenza di altri errori del percorso dati, accanto al percorso dati non verranno più visualizzate altre icone di errore.</span><span class="sxs-lookup"><span data-stu-id="47239-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="47239-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="47239-108">Options</span></span>  
 <span data-ttu-id="47239-109">Colonne di output senza mapping (Origine):</span><span class="sxs-lookup"><span data-stu-id="47239-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="47239-110">Colonne del percorso a monte di cui non è stato eseguito il mapping</span><span class="sxs-lookup"><span data-stu-id="47239-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="47239-111">Colonne con mapping (Origine):</span><span class="sxs-lookup"><span data-stu-id="47239-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="47239-112">Colonne del percorso a monte di cui è stato eseguito il mapping alle colonne del percorso a valle</span><span class="sxs-lookup"><span data-stu-id="47239-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="47239-113">Colonne con mapping (Destinazione):</span><span class="sxs-lookup"><span data-stu-id="47239-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="47239-114">Colonne del percorso a monte di cui è stato eseguito il mapping alle colonne del percorso a valle</span><span class="sxs-lookup"><span data-stu-id="47239-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="47239-115">Colonne di input senza mapping (Destinazione):</span><span class="sxs-lookup"><span data-stu-id="47239-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="47239-116">Colonne del percorso a valle di cui non è stato eseguito il mapping</span><span class="sxs-lookup"><span data-stu-id="47239-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="47239-117">Elimina colonne input senza mapping</span><span class="sxs-lookup"><span data-stu-id="47239-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="47239-118">Selezionare Elimina colonne input senza mapping per ignorare le colonne senza mapping alla destinazione del percorso dati.</span><span class="sxs-lookup"><span data-stu-id="47239-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="47239-119">Il pulsante Anteprima modifiche consente di visualizzare un elenco delle modifiche che si verificheranno alla pressione del pulsante OK.</span><span class="sxs-lookup"><span data-stu-id="47239-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  
