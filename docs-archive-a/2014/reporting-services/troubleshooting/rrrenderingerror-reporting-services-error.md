---
title: rrRenderingError - Errore di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715980"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="4cc65-102">rrRenderingError - Errore di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4cc65-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="4cc65-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4cc65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cc65-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4cc65-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="4cc65-105">ID evento</span><span class="sxs-lookup"><span data-stu-id="4cc65-105">Event ID</span></span>|<span data-ttu-id="4cc65-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="4cc65-106">rrRenderingError</span></span>|  
|<span data-ttu-id="4cc65-107">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4cc65-107">Event Source</span></span>|<span data-ttu-id="4cc65-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="4cc65-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="4cc65-109">Componente</span><span class="sxs-lookup"><span data-stu-id="4cc65-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="4cc65-110">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4cc65-110">Message Text</span></span>|<span data-ttu-id="4cc65-111">Errore durante il rendering del report.</span><span class="sxs-lookup"><span data-stu-id="4cc65-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="4cc65-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="4cc65-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4cc65-113">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4cc65-113">Explanation</span></span>  
 <span data-ttu-id="4cc65-114">Questo messaggio viene restituito quando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non è in grado di eseguire il rendering del report o di esportarlo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="4cc65-115">Un messaggio che indica che le dimensioni non sono supportate viene in genere visualizzato quando le dimensioni della pagina RDL non sono valide.</span><span class="sxs-lookup"><span data-stu-id="4cc65-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="4cc65-116">Specificare una dimensione RDL della pagina valida, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-117">Un messaggio che indica che l'unità di misura delle dimensioni RDL non è supportata viene in genere visualizzato quando il tipo di unità di misura specificato non è supportato.</span><span class="sxs-lookup"><span data-stu-id="4cc65-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="4cc65-118">Tipi di unità validi sono cm, in, mm, PC e pt.</span><span class="sxs-lookup"><span data-stu-id="4cc65-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="4cc65-119">Specificare un tipo di unità valido, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-120">Un messaggio che indica che la dimensione negativa non è supportata viene in genere visualizzato quando viene specificata una dimensione negativa, ad esempio -5, per le dimensioni della pagina.</span><span class="sxs-lookup"><span data-stu-id="4cc65-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="4cc65-121">Specificare un numero positivo per la dimensione della pagina, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-122">Un messaggio che indica che le dimensioni RDL specificate non sono comprese nell'intervallo dei valori consentiti viene in genere visualizzato quando la misura relativa alle dimensioni della pagina non rientra nelle dimensioni valide per i margini della pagina.</span><span class="sxs-lookup"><span data-stu-id="4cc65-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="4cc65-123">Specificare una misura per le dimensioni della pagina che sia all'interno delle dimensioni di margine di pagina valide.</span><span class="sxs-lookup"><span data-stu-id="4cc65-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="4cc65-124">Un messaggio che indica che il colore specificato non è supportato viene in genere visualizzato quando un colore specificato in RDL non è valido.</span><span class="sxs-lookup"><span data-stu-id="4cc65-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="4cc65-125">Scegliere un colore supportato da RDL, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-126">Un messaggio che indica che l'etichetta dell'azione è facoltativa solo quando si utilizza una sola azione e che l'aggiunta di più azioni richiede un'etichetta per ognuna di esse viene in genere visualizzato quando un'etichetta di un'azione specificata non è valida.</span><span class="sxs-lookup"><span data-stu-id="4cc65-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="4cc65-127">Specificare un'etichetta valida per ciascuna azione.</span><span class="sxs-lookup"><span data-stu-id="4cc65-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="4cc65-128">Un messaggio che indica che l'argomento dello stile deve essere di un tipo specifico viene in genere visualizzato quando viene specificato un valore di stile non corretto per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4cc65-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="4cc65-129">La specifica RDL identifica i tipi validi che è possibile usare nei valori dello stile di diversi elementi RDL.</span><span class="sxs-lookup"><span data-stu-id="4cc65-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="4cc65-130">Ad esempio, un valore di stile non corretto per il colore di sfondo è "2 pt" e un valore non corretto per l'altezza è "true".</span><span class="sxs-lookup"><span data-stu-id="4cc65-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="4cc65-131">Specificare un valore corretto, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-132">Un messaggio che indica che lo stile del bordo non è supportato viene in genere visualizzato quando lo stile del bordo specificato non è valido.</span><span class="sxs-lookup"><span data-stu-id="4cc65-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="4cc65-133">Specificare un stile del bordo supportato, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-134">Un messaggio che indica che il formato MimeType per l'immagine non è supportato viene in genere visualizzato quando il formato MimeType specificato per un elemento del report non è valido.</span><span class="sxs-lookup"><span data-stu-id="4cc65-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="4cc65-135">Specificare un formato MimeType supportato per l'elemento del report, quindi effettuare un nuovo tentativo.</span><span class="sxs-lookup"><span data-stu-id="4cc65-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="4cc65-136">Un messaggio che indica che il numero di righe supera il numero massimo di righe possibili per foglio di lavoro viene in genere visualizzato quando viene superato il numero massimo di righe in un foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="4cc65-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="4cc65-137">Un foglio di lavoro di Excel supporta fino a 65.000 righe.</span><span class="sxs-lookup"><span data-stu-id="4cc65-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="4cc65-138">Un messaggio che indica che il numero di colonne supera il numero massimo di colonne possibili per foglio di lavoro viene in genere visualizzato quando viene superato il numero massimo di colonne in un foglio di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="4cc65-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4cc65-139">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4cc65-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="4cc65-140">Solo interno</span><span class="sxs-lookup"><span data-stu-id="4cc65-140">Internal-Only</span></span>  
  
