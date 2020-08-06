---
title: Editor attività servizio Web (pagina Input) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ae876572747b9bb1088fe8b0a1c2c2fdde9f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636777"
---
# <a name="web-service-task-editor-input-page"></a><span data-ttu-id="0049b-102">Editor attività Servizio Web (pagina Input)</span><span class="sxs-lookup"><span data-stu-id="0049b-102">Web Service Task Editor (Input Page)</span></span>
  <span data-ttu-id="0049b-103">Utilizzare la pagina **Input** della finestra di dialogo **Editor attività Servizio Web** per specificare il servizio Web, il metodo Web e i valori da fornire come input al metodo Web.</span><span class="sxs-lookup"><span data-stu-id="0049b-103">Use the **Input** page of the **Web Service Task Editor** dialog box to specify the Web Service, the Web method, and the values to provide to the Web method as input.</span></span> <span data-ttu-id="0049b-104">I valori possono essere immessi digitando direttamente le stringhe nella colonna Valore o selezionando le variabili nella colonna Valore.</span><span class="sxs-lookup"><span data-stu-id="0049b-104">The values can be provided either by typing strings directly in the Value column, or by selecting variables in the Value column.</span></span>  
  
 <span data-ttu-id="0049b-105">Per altre informazioni su questa attività, vedere [Attività Servizio Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="0049b-105">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0049b-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0049b-106">Options</span></span>  
 <span data-ttu-id="0049b-107">**Service**</span><span class="sxs-lookup"><span data-stu-id="0049b-107">**Service**</span></span>  
 <span data-ttu-id="0049b-108">Consente di selezionare un servizio Web nell'elenco da utilizzare per l'esecuzione del metodo Web.</span><span class="sxs-lookup"><span data-stu-id="0049b-108">Select a Web service from the list to use to execute the Web method.</span></span>  
  
 <span data-ttu-id="0049b-109">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="0049b-109">**Method**</span></span>  
 <span data-ttu-id="0049b-110">Consente di selezionare nell'elenco il metodo Web che l'attività deve eseguire.</span><span class="sxs-lookup"><span data-stu-id="0049b-110">Select a Web method from the list for the task to execute.</span></span>  
  
 <span data-ttu-id="0049b-111">**WebMethodDocumentation**</span><span class="sxs-lookup"><span data-stu-id="0049b-111">**WebMethodDocumentation**</span></span>  
 <span data-ttu-id="0049b-112">Digitare una descrizione del metodo Web oppure fare clic sul pulsante sfoglia **(...)** e quindi digitare la descrizione nella finestra di dialogo **Documentazione metodo Web**.</span><span class="sxs-lookup"><span data-stu-id="0049b-112">Type a description of Web method, or the click the browse button **(...)** and then type the description in the **Web Method Documentation** dialog box.</span></span>  
  
 <span data-ttu-id="0049b-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0049b-113">**Name**</span></span>  
 <span data-ttu-id="0049b-114">Elenca i nomi degli input per il metodo Web.</span><span class="sxs-lookup"><span data-stu-id="0049b-114">Lists the names of the inputs to the Web method.</span></span>  
  
 <span data-ttu-id="0049b-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0049b-115">**Type**</span></span>  
 <span data-ttu-id="0049b-116">Elenca il tipo di dati degli input.</span><span class="sxs-lookup"><span data-stu-id="0049b-116">Lists the data type of the inputs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0049b-117">L'attività Servizio Web supporta unicamente i parametri dei tipi di dati seguenti: tipi primitivi come ad esempio valori integer e stringhe, matrici e sequenze di tipi primitivi ed enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="0049b-117">The Web Service task supports parameters of the following data types only: primitive types such as integers and strings; arrays and sequences of primitive types; and enumerations.</span></span>  
  
 <span data-ttu-id="0049b-118">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="0049b-118">**Variable**</span></span>  
 <span data-ttu-id="0049b-119">Selezionare le caselle di controllo per utilizzare le variabili per l'invio degli input.</span><span class="sxs-lookup"><span data-stu-id="0049b-119">Select the check boxes to use variables to provide inputs.</span></span>  
  
 <span data-ttu-id="0049b-120">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0049b-120">**Value**</span></span>  
 <span data-ttu-id="0049b-121">Se le caselle di controllo Variabile sono selezionate, selezionare le variabili nell'elenco per l'invio degli input. In caso contrario, digitare i valori da utilizzare negli input.</span><span class="sxs-lookup"><span data-stu-id="0049b-121">If the Variable check-boxes are selected, select the variables in the list to provide the inputs; otherwise, type the values to use in the inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0049b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0049b-122">See Also</span></span>  
 <span data-ttu-id="0049b-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0049b-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0049b-124">[Editor attività servizio Web &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0049b-124">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0049b-125">[Editor attività servizio Web &#40;pagina output&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="0049b-125">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="0049b-126">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="0049b-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
