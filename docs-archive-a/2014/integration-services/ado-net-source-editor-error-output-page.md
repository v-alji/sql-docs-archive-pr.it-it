---
title: Editor origine ADO NET (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.erroroutput.f1
ms.assetid: 4dd9d129-a95c-4d3a-bbbf-e84a39089950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9ee480caa8764d70b52b25a416f200f353d30c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724067"
---
# <a name="ado-net-source-editor-error-output-page"></a><span data-ttu-id="b9b75-102">Editor origine ADO NET (pagina Output errori)</span><span class="sxs-lookup"><span data-stu-id="b9b75-102">ADO NET Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="b9b75-103">Usare la pagina **Output errori** della finestra di dialogo **Editor origine ADO NET** per selezionare le opzioni di gestione degli errori e impostare le proprietà delle colonne di output degli errori.</span><span class="sxs-lookup"><span data-stu-id="b9b75-103">Use the **Error Output** page of the **ADO NET Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="b9b75-104">Per ulteriori informazioni sull'origine ADO NET, vedere [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="b9b75-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="b9b75-105">**Per aprire la pagina Output errori**</span><span class="sxs-lookup"><span data-stu-id="b9b75-105">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="b9b75-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con l'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="b9b75-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="b9b75-107">Nella scheda **Flusso di dati** fare doppio clic sull'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="b9b75-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="b9b75-108">In **Editor origine ADO NET**, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="b9b75-108">In the **ADO NET Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9b75-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b9b75-109">Options</span></span>  
 <span data-ttu-id="b9b75-110">**Input/Output**</span><span class="sxs-lookup"><span data-stu-id="b9b75-110">**Input/Output**</span></span>  
 <span data-ttu-id="b9b75-111">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="b9b75-111">View the name of the data source.</span></span>  
  
 <span data-ttu-id="b9b75-112">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9b75-112">**Column**</span></span>  
 <span data-ttu-id="b9b75-113">Consente di visualizzare le colonne esterne (di origine) selezionate nella pagina **Gestione connessione** della finestra di dialogo **Editor origine ADO NET** .</span><span class="sxs-lookup"><span data-stu-id="b9b75-113">View the external (source) columns that you selected on the **Connection Manager** page of the **ADO NET Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="b9b75-114">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="b9b75-114">**Error**</span></span>  
 <span data-ttu-id="b9b75-115">Consente di specificare l'azione da eseguire in caso di errori, ovvero ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="b9b75-115">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b9b75-116">**Argomenti correlati:** [Gestione degli errori nei dati](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="b9b75-116">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="b9b75-117">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="b9b75-117">**Truncation**</span></span>  
 <span data-ttu-id="b9b75-118">Consente di specificare l'azione da eseguire in caso di troncamenti, ovvero ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="b9b75-118">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b9b75-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b9b75-119">**Description**</span></span>  
 <span data-ttu-id="b9b75-120">Consente di visualizzare la descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="b9b75-120">View the description of the error.</span></span>  
  
 <span data-ttu-id="b9b75-121">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="b9b75-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="b9b75-122">Consente di specificare l'azione che dovrà interessare tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="b9b75-122">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="b9b75-123">**Applica**</span><span class="sxs-lookup"><span data-stu-id="b9b75-123">**Apply**</span></span>  
 <span data-ttu-id="b9b75-124">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="b9b75-124">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b75-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9b75-125">See Also</span></span>  
 <span data-ttu-id="b9b75-126">[Editor origine ADO NET &#40;pagina Gestione connessione&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="b9b75-126">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="b9b75-127">[Editor origine ADO NET &#40;pagina colonne&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="b9b75-127">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="b9b75-128">Gestione connessione ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9b75-128">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
