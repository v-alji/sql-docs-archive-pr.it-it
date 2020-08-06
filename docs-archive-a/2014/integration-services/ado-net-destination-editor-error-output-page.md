---
title: Editor destinazione ADO NET (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.erroroutput.f1
ms.assetid: 1a56c3cf-fb6a-416d-a62c-bb19fe441ae5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9cfd69d3adec2aa617f5e9d3add35a1a6923804
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628941"
---
# <a name="ado-net-destination-editor-error-output-page"></a><span data-ttu-id="7c6a8-102">Editor destinazione ADO NET (pagina Output errori)</span><span class="sxs-lookup"><span data-stu-id="7c6a8-102">ADO NET Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="7c6a8-103">Usare la pagina **Output errori** della finestra di dialogo **Editor destinazione ADO NET** per specificare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-103">Use the **Error Output** page of the **ADO NET Destination Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="7c6a8-104">Per ulteriori informazioni sulla destinazione ADO NET, vedere [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="7c6a8-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="7c6a8-105">**Per aprire la pagina Output errori**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="7c6a8-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con la destinazione ADO NET.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="7c6a8-107">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione ADO NET.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="7c6a8-108">In **Editor destinazione ADO NET**fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-108">In the **ADO NET Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7c6a8-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7c6a8-109">Options</span></span>  
 <span data-ttu-id="7c6a8-110">**Input o output**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-110">**Input or Output**</span></span>  
 <span data-ttu-id="7c6a8-111">Consente di visualizzare il nome dell'input.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-111">View the name of the input.</span></span>  
  
 <span data-ttu-id="7c6a8-112">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-112">**Column**</span></span>  
 <span data-ttu-id="7c6a8-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-113">Not used.</span></span>  
  
 <span data-ttu-id="7c6a8-114">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-114">**Error**</span></span>  
 <span data-ttu-id="7c6a8-115">Consente di specificare l'azione da eseguire in caso di errori, ovvero ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7c6a8-116">**Argomenti correlati:** [Gestione degli errori nei dati](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="7c6a8-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="7c6a8-117">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-117">**Truncation**</span></span>  
 <span data-ttu-id="7c6a8-118">Non usato.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-118">Not used.</span></span>  
  
 <span data-ttu-id="7c6a8-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-119">**Description**</span></span>  
 <span data-ttu-id="7c6a8-120">Consente di visualizzare la descrizione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-120">View the description of the operation.</span></span>  
  
 <span data-ttu-id="7c6a8-121">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="7c6a8-122">Consente di specificare l'azione che dovrà interessare tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="7c6a8-123">**Applica**</span><span class="sxs-lookup"><span data-stu-id="7c6a8-123">**Apply**</span></span>  
 <span data-ttu-id="7c6a8-124">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="7c6a8-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6a8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c6a8-125">See Also</span></span>  
 <span data-ttu-id="7c6a8-126">[Editor destinazione ADO NET &#40;pagina Gestione connessione&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="7c6a8-126">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="7c6a8-127">Editor destinazione ADO NET &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="7c6a8-127">ADO NET Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-mappings-page.md)  
  
  
