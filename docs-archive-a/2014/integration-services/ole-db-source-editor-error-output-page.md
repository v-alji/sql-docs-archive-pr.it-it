---
title: Editor origine OLE DB (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.errorhandling.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 7737c6ae-c16b-4856-aa6e-5882640093b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ded87747f041a4d8451048d4ef4671b029125873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636800"
---
# <a name="ole-db-source-editor-error-output-page"></a><span data-ttu-id="fbdf0-102">Editor origine OLE DB (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="fbdf0-102">OLE DB Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="fbdf0-103">Usare la pagina **Output degli errori** della finestra di dialogo **Editor origine OLE DB** per selezionare le opzioni di gestione degli errori e impostare le proprietà delle colonne di output degli errori.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-103">Use the **Error Output** page of the **OLE DB Source Editor** dialog box to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="fbdf0-104">Per ulteriori informazioni sull'origine OLE DB, vedere [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="fbdf0-104">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fbdf0-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fbdf0-105">Options</span></span>  
 <span data-ttu-id="fbdf0-106">**Input/Output**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-106">**Input/Output**</span></span>  
 <span data-ttu-id="fbdf0-107">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="fbdf0-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-108">**Column**</span></span>  
 <span data-ttu-id="fbdf0-109">Consente di visualizzare le colonne esterne (origine) selezionate nella pagina **Gestione connessione** della finestra di dialogo **Editor origine OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-109">View the external (source) columns that you selected on the **Connection Manager** page of the **OLE DB Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="fbdf0-110">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-110">**Error**</span></span>  
 <span data-ttu-id="fbdf0-111">Consente di specificare l'azione da eseguire in caso di errori, ovvero ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="fbdf0-112">**Argomenti correlati:** [Gestione degli errori nei dati](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="fbdf0-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="fbdf0-113">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-113">**Truncation**</span></span>  
 <span data-ttu-id="fbdf0-114">Consente di specificare l'azione da eseguire in caso di troncamenti, ovvero ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="fbdf0-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-115">**Description**</span></span>  
 <span data-ttu-id="fbdf0-116">Consente di visualizzare la descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="fbdf0-117">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="fbdf0-118">Consente di specificare l'azione che dovrà interessare tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="fbdf0-119">**Applica**</span><span class="sxs-lookup"><span data-stu-id="fbdf0-119">**Apply**</span></span>  
 <span data-ttu-id="fbdf0-120">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="fbdf0-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdf0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbdf0-121">See Also</span></span>  
 <span data-ttu-id="fbdf0-122">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fbdf0-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fbdf0-123">[Editor origine OLE DB &#40;pagina Gestione connessione&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="fbdf0-123">[OLE DB Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ole-db-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="fbdf0-124">[Editor origine OLE DB &#40;pagina colonne&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="fbdf0-124">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="fbdf0-125">[Estrarre dati tramite l'origine OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="fbdf0-125">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="fbdf0-126">Gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="fbdf0-126">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
