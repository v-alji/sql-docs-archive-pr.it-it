---
title: Editor avanzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626239"
---
# <a name="advanced-editor"></a><span data-ttu-id="4c60a-102">Editor avanzato</span><span class="sxs-lookup"><span data-stu-id="4c60a-102">Advanced Editor</span></span>
  <span data-ttu-id="4c60a-103">Utilizzare la finestra di dialogo **Editor avanzato** per configurare le proprietà per l'oggetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="4c60a-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="4c60a-104">L' **Editor avanzato** è disponibile per la maggior parte degli oggetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che dispongono di proprietà configurabili.</span><span class="sxs-lookup"><span data-stu-id="4c60a-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="4c60a-105">Questo è l'unico editor disponibile per gli oggetti che non espongono un'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c60a-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="4c60a-106">sono disponibili proprietà che è possibile impostare a livello di componente, a livello di input e output e a livello delle colonne di input e output.</span><span class="sxs-lookup"><span data-stu-id="4c60a-106">data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="4c60a-107">Nell' **Editor avanzato** vengono enumerate tutte le proprietà comuni e personalizzate dell'oggetto selezionato e tali proprietà possono essere visualizzate in massimo quattro delle cinque schede seguenti, in base al contesto appropriato:</span><span class="sxs-lookup"><span data-stu-id="4c60a-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="4c60a-108">**Gestioni connessioni** : usare questa scheda per impostare le proprietà di connessione</span><span class="sxs-lookup"><span data-stu-id="4c60a-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="4c60a-109">**Proprietà componente** : usare questa scheda per impostare le proprietà a livello di componente</span><span class="sxs-lookup"><span data-stu-id="4c60a-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="4c60a-110">**Mapping colonne** : usare questa scheda per eseguire il mapping delle colonne disponibili come colonne di output</span><span class="sxs-lookup"><span data-stu-id="4c60a-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="4c60a-111">**Colonne di input** : usare questa scheda per selezionare colonne di input</span><span class="sxs-lookup"><span data-stu-id="4c60a-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="4c60a-112">**Proprietà input e output** : usare questa scheda per impostare le proprietà di input e output, aggiungere e rimuovere output, selezionare o rimuovere colonne per input e output e impostare proprietà per input e output</span><span class="sxs-lookup"><span data-stu-id="4c60a-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="4c60a-113">Le proprietà visualizzate variano a seconda del componente.</span><span class="sxs-lookup"><span data-stu-id="4c60a-113">The properties displayed vary by component.</span></span> <span data-ttu-id="4c60a-114">Per ulteriori informazioni sulle proprietà che possono essere visualizzate nell' **Editor avanzato**, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c60a-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4c60a-115">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="4c60a-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="4c60a-116">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="4c60a-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="4c60a-117">Proprietà del percorso</span><span class="sxs-lookup"><span data-stu-id="4c60a-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="4c60a-118">Per ulteriori informazioni sul componente specifico da modificare, vedere la relativa descrizione nella sezione Elementi dei flussi di dati della documentazione Oggetti e concetti di base di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4c60a-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="4c60a-119">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="4c60a-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c60a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c60a-120">See Also</span></span>  
 [<span data-ttu-id="4c60a-121">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="4c60a-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
