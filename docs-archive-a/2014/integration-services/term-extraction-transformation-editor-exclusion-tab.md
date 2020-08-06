---
title: Editor trasformazione Estrazione termini (scheda esclusione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637424"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="83b56-102">Editor trasformazione Estrazione termini (scheda Esclusione)</span><span class="sxs-lookup"><span data-stu-id="83b56-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="83b56-103">Utilizzare la scheda **Esclusione** della finestra di dialogo **Editor trasformazione Estrazione termini** per impostare una connessione a una tabella di esclusione e specificare le colonne che contengono termini di esclusione.</span><span class="sxs-lookup"><span data-stu-id="83b56-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="83b56-104">Per ulteriori informazioni sulla trasformazione Estrazione termini, vedere [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="83b56-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83b56-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="83b56-105">Options</span></span>  
 <span data-ttu-id="83b56-106">**Usa termini di esclusione**</span><span class="sxs-lookup"><span data-stu-id="83b56-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="83b56-107">Consente di indicare se escludere termini specifici durante l'estrazione dei termini specificando una colonna che contiene termini di esclusione.</span><span class="sxs-lookup"><span data-stu-id="83b56-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="83b56-108">Se si sceglie di escludere termini, è necessario specificare le proprietà delle origini dei dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="83b56-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="83b56-109">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="83b56-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="83b56-110">Selezionare una gestione connessione OLE DB esistente oppure fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="83b56-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="83b56-111">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="83b56-111">**New**</span></span>  
 <span data-ttu-id="83b56-112">Consente di creare una nuova connessione a un database usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="83b56-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="83b56-113">**Tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="83b56-113">**Table or view**</span></span>  
 <span data-ttu-id="83b56-114">Consente di specificare la tabella o la vista che contiene i termini di esclusione.</span><span class="sxs-lookup"><span data-stu-id="83b56-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="83b56-115">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="83b56-115">**Column**</span></span>  
 <span data-ttu-id="83b56-116">Consente di selezionare la colonna della tabella o della vista che contiene i termini di esclusione.</span><span class="sxs-lookup"><span data-stu-id="83b56-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="83b56-117">**Configura output errori**</span><span class="sxs-lookup"><span data-stu-id="83b56-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="83b56-118">Usare la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) per specificare la gestione degli errori per le righe che causano errori.</span><span class="sxs-lookup"><span data-stu-id="83b56-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b56-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b56-119">See Also</span></span>  
 <span data-ttu-id="83b56-120">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="83b56-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="83b56-121">[Editor trasformazione Estrazione termini &#40;scheda Estrazione termini&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="83b56-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="83b56-122">[Editor trasformazione Estrazione termini &#40;scheda Avanzate&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="83b56-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="83b56-123">Trasformazione Ricerca termini</span><span class="sxs-lookup"><span data-stu-id="83b56-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
