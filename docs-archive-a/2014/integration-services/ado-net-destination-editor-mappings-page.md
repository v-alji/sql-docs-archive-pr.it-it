---
title: Editor destinazione ADO NET (pagina mapping) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.mappings.f1
ms.assetid: 842d075f-8b7a-457c-a1a1-a7acbe10e9b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7e7a2397e4e2d16e6eeca93d41f5127dfde4c35e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623455"
---
# <a name="ado-net-destination-editor-mappings-page"></a><span data-ttu-id="aa454-102">Editor destinazione ADO NET (pagina Mapping)</span><span class="sxs-lookup"><span data-stu-id="aa454-102">ADO NET Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="aa454-103">Utilizzare la pagina **Mapping** della finestra di dialogo **Editor destinazione ADO NET** per eseguire il mapping tra colonne di input e colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="aa454-103">Use the **Mappings** page of the **ADO NET Destination Editor** dialog box to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="aa454-104">Per ulteriori informazioni sulla destinazione ADO NET, vedere [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="aa454-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="aa454-105">**Per aprire la pagina Mapping**</span><span class="sxs-lookup"><span data-stu-id="aa454-105">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="aa454-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con la destinazione ADO NET.</span><span class="sxs-lookup"><span data-stu-id="aa454-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="aa454-107">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione ADO NET.</span><span class="sxs-lookup"><span data-stu-id="aa454-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="aa454-108">In **Editor destinazione ADO NET**, fare clic su **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="aa454-108">In the **ADO NET Destination Editor**, click **Mappings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa454-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aa454-109">Options</span></span>  
 <span data-ttu-id="aa454-110">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="aa454-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="aa454-111">Consente di visualizzare l'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="aa454-111">View the list of available input columns.</span></span> <span data-ttu-id="aa454-112">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di input disponibili nella tabella e le colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="aa454-112">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="aa454-113">**Colonne di destinazione disponibili**</span><span class="sxs-lookup"><span data-stu-id="aa454-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="aa454-114">Consente di visualizzare l'elenco delle colonne di destinazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="aa454-114">View the list of available destination columns.</span></span> <span data-ttu-id="aa454-115">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di destinazione disponibili nella tabella e le colonne di input.</span><span class="sxs-lookup"><span data-stu-id="aa454-115">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="aa454-116">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="aa454-116">**Input Column**</span></span>  
 <span data-ttu-id="aa454-117">Consente di visualizzare le colonne di input selezionate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="aa454-117">View the input columns that you selected.</span></span> <span data-ttu-id="aa454-118">È possibile rimuovere i mapping selezionando **\<ignore>** per escludere colonne dall'output.</span><span class="sxs-lookup"><span data-stu-id="aa454-118">You can remove mappings by selecting **\<ignore>** to exclude columns from the output.</span></span>  
  
 <span data-ttu-id="aa454-119">**Colonna di destinazione**</span><span class="sxs-lookup"><span data-stu-id="aa454-119">**Destination Column**</span></span>  
 <span data-ttu-id="aa454-120">Consente di visualizzare ogni colonna di destinazione disponibile, indipendentemente dal fatto che sia mappata o meno.</span><span class="sxs-lookup"><span data-stu-id="aa454-120">View each available destination column, regardless of whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa454-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa454-121">See Also</span></span>  
 <span data-ttu-id="aa454-122">[Editor destinazione ADO NET &#40;pagina Gestione connessione&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="aa454-122">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="aa454-123">Editor destinazione ADO NET &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="aa454-123">ADO NET Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-error-output-page.md)  
  
  
