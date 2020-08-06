---
title: Editor trasformazione Ricerca (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628806"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="eaa08-102">Editor trasformazione Ricerca (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="eaa08-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="eaa08-103">Usare la pagina **Output degli errori** della finestra di dialogo **Editor trasformazione Ricerca** per specificare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="eaa08-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="eaa08-104">Per ulteriori informazioni sulla trasformazione Ricerca, vedere [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="eaa08-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eaa08-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="eaa08-105">Options</span></span>  
 <span data-ttu-id="eaa08-106">**Input/Output**</span><span class="sxs-lookup"><span data-stu-id="eaa08-106">**Input/Output**</span></span>  
 <span data-ttu-id="eaa08-107">Consente di visualizzare il nome dell'input.</span><span class="sxs-lookup"><span data-stu-id="eaa08-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="eaa08-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="eaa08-108">**Column**</span></span>  
 <span data-ttu-id="eaa08-109">Non usato.</span><span class="sxs-lookup"><span data-stu-id="eaa08-109">Not used.</span></span>  
  
 <span data-ttu-id="eaa08-110">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="eaa08-110">**Error**</span></span>  
 <span data-ttu-id="eaa08-111">Consente di specificare il tipo di errore che si verifica quando vengono gestite righe prive di voci corrispondenti nel set di dati di riferimento:</span><span class="sxs-lookup"><span data-stu-id="eaa08-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="eaa08-112">Ignorare l'errore e inviare le righe a un output.</span><span class="sxs-lookup"><span data-stu-id="eaa08-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="eaa08-113">Reindirizzare le righe a un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="eaa08-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="eaa08-114">Interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="eaa08-114">Fail the component.</span></span>  
  
 <span data-ttu-id="eaa08-115">Questa opzione non è disponibile quando si seleziona **Reindirizza righe all'output nessuna corrispondenza** nell'elenco **Specificare come gestire le righe senza voci corrispondenti** .</span><span class="sxs-lookup"><span data-stu-id="eaa08-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="eaa08-116">Questo elenco si trova nella pagina **Generale** della finestra di dialogo **Editor trasformazione Ricerca** .</span><span class="sxs-lookup"><span data-stu-id="eaa08-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="eaa08-117">**Argomenti correlati:** [Gestione degli errori nei dati](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="eaa08-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="eaa08-118">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="eaa08-118">**Truncation**</span></span>  
 <span data-ttu-id="eaa08-119">Consente di specificare l'azione da eseguire quando si verifica il troncamento:</span><span class="sxs-lookup"><span data-stu-id="eaa08-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="eaa08-120">Ignorare l'errore.</span><span class="sxs-lookup"><span data-stu-id="eaa08-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="eaa08-121">Reindirizzare la riga.</span><span class="sxs-lookup"><span data-stu-id="eaa08-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="eaa08-122">Interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="eaa08-122">Fail the component.</span></span>  
  
 <span data-ttu-id="eaa08-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="eaa08-123">**Description**</span></span>  
 <span data-ttu-id="eaa08-124">Consente di visualizzare la descrizione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="eaa08-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="eaa08-125">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="eaa08-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="eaa08-126">Consente di specificare l'azione da eseguire su tutte le celle selezionate quando si verifica un errore o un troncamento:</span><span class="sxs-lookup"><span data-stu-id="eaa08-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="eaa08-127">Ignorare l'errore.</span><span class="sxs-lookup"><span data-stu-id="eaa08-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="eaa08-128">Reindirizzare la riga.</span><span class="sxs-lookup"><span data-stu-id="eaa08-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="eaa08-129">Interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="eaa08-129">Fail the component.</span></span>  
  
 <span data-ttu-id="eaa08-130">**Applica**</span><span class="sxs-lookup"><span data-stu-id="eaa08-130">**Apply**</span></span>  
 <span data-ttu-id="eaa08-131">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="eaa08-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaa08-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eaa08-132">See Also</span></span>  
 [<span data-ttu-id="eaa08-133">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="eaa08-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
