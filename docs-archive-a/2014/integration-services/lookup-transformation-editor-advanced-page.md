---
title: Editor trasformazione Ricerca (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.advanced.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: f3395c65-0320-47f9-8d83-daaa082d8713
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 23f235ef0506da7ac808d832db6ac36d53cfa604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628811"
---
# <a name="lookup-transformation-editor-advanced-page"></a><span data-ttu-id="6514e-102">Editor trasformazione Ricerca (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="6514e-102">Lookup Transformation Editor (Advanced Page)</span></span>
  <span data-ttu-id="6514e-103">La pagina **Avanzate** della finestra di dialogo **Editor trasformazione Ricerca** consente di configurare la memorizzazione nella cache parziale e di modificare l'istruzione SQL della trasformazione Ricerca.</span><span class="sxs-lookup"><span data-stu-id="6514e-103">Use the **Advanced** page of the **Lookup Transformation Editor** dialog box to configure partial caching and to modify the SQL statement for the Lookup transformation.</span></span>  
  
 <span data-ttu-id="6514e-104">Per ulteriori informazioni sulla trasformazione Ricerca, vedere [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6514e-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6514e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6514e-105">Options</span></span>  
 <span data-ttu-id="6514e-106">**Dimensioni cache (32 bit)**</span><span class="sxs-lookup"><span data-stu-id="6514e-106">**Cache size (32-bit)**</span></span>  
 <span data-ttu-id="6514e-107">Consente di regolare le dimensioni della cache (in megabyte) per i computer a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="6514e-107">Adjust the  cache size (in megabytes) for 32-bit computers.</span></span> <span data-ttu-id="6514e-108">Il valore predefinito è 5 MB.</span><span class="sxs-lookup"><span data-stu-id="6514e-108">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="6514e-109">**Dimensioni cache (64 bit)**</span><span class="sxs-lookup"><span data-stu-id="6514e-109">**Cache size (64-bit)**</span></span>  
 <span data-ttu-id="6514e-110">Consente di regolare le dimensioni della cache (in megabyte) per i computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6514e-110">Adjust the cache size (in megabytes) for 64-bit computers.</span></span> <span data-ttu-id="6514e-111">Il valore predefinito è 5 MB.</span><span class="sxs-lookup"><span data-stu-id="6514e-111">The default value is 5 megabytes.</span></span>  
  
 <span data-ttu-id="6514e-112">**Attivare cache per righe senza voci corrispondenti**</span><span class="sxs-lookup"><span data-stu-id="6514e-112">**Enable cache for rows with no matching entries**</span></span>  
 <span data-ttu-id="6514e-113">Consente di memorizzare nella cache le righe senza voci corrispondenti nel set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6514e-113">Cache rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="6514e-114">**Allocazione dalla cache**</span><span class="sxs-lookup"><span data-stu-id="6514e-114">**Allocation from cache**</span></span>  
 <span data-ttu-id="6514e-115">Consente di specificare la percentuale della cache da allocare per le righe senza voci corrispondenti nel set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6514e-115">Specify the percentage of the cache to allocate for rows with no matching entries in the reference dataset.</span></span>  
  
 <span data-ttu-id="6514e-116">**Modifica istruzione SQL**</span><span class="sxs-lookup"><span data-stu-id="6514e-116">**Modify the SQL statement**</span></span>  
 <span data-ttu-id="6514e-117">Consente di modificare l'istruzione SQL utilizzata per generare il set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6514e-117">Modify the SQL statement that is used to generate the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6514e-118">L'istruzione SQL facoltativa specificata in questa pagina sostituisce il nome tabella specificato nella pagina **Connessione** di **Editor trasformazione Ricerca**.</span><span class="sxs-lookup"><span data-stu-id="6514e-118">The optional SQL statement that you specify on this page overrides and replaces the table name that you specified on the **Connection** page of the **Lookup Transformation Editor**.</span></span> <span data-ttu-id="6514e-119">Per altre informazioni, vedere [Editor trasformazione Ricerca &#40;pagina Connessione&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span><span class="sxs-lookup"><span data-stu-id="6514e-119">For more information, see [Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md).</span></span>  
  
 <span data-ttu-id="6514e-120">**Impostazione dei parametri**</span><span class="sxs-lookup"><span data-stu-id="6514e-120">**Set Parameters**</span></span>  
 <span data-ttu-id="6514e-121">Consente di eseguire il mapping delle colonne di input ai parametri mediante la finestra di dialogo **Imposta parametri query** .</span><span class="sxs-lookup"><span data-stu-id="6514e-121">Map input columns to parameters by using the **Set Query Parameters** dialog box.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="6514e-122">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="6514e-122">External Resources</span></span>  
 <span data-ttu-id="6514e-123">Intervento nel blog sulle [modalità cache di ricerca](https://go.microsoft.com/fwlink/?LinkId=219518) su blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="6514e-123">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6514e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6514e-124">See Also</span></span>  
 <span data-ttu-id="6514e-125">[Editor trasformazione Ricerca &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-125">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="6514e-126">[Editor trasformazione Ricerca &#40;pagina connessione&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-126">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="6514e-127">[Editor trasformazione Ricerca &#40;pagina colonne&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-127">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6514e-128">[Editor trasformazione Ricerca &#40;pagina output degli errori&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-128">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="6514e-129">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6514e-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="6514e-130">Ricerca fuzzy - trasformazione</span><span class="sxs-lookup"><span data-stu-id="6514e-130">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
