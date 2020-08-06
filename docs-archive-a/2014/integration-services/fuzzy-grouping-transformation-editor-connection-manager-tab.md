---
title: Editor trasformazione Raggruppamento fuzzy (scheda Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636273"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="cf31f-102">Editor trasformazione Raggruppamento fuzzy (scheda Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="cf31f-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="cf31f-103">Utilizzare la scheda **Gestione connessione** della finestra di dialogo **Editor trasformazione Raggruppamento fuzzy** per selezionare una connessione esistente o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="cf31f-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf31f-104">Sul server specificato dalla connessione deve essere in esecuzione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf31f-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cf31f-105">La trasformazione Raggruppamento fuzzy crea in tempdb oggetti dati temporanei che possono avere le stesse dimensioni dell'intero input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="cf31f-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="cf31f-106">Durante l'esecuzione della trasformazione vengono eseguite query del server su tali oggetti temporanei.</span><span class="sxs-lookup"><span data-stu-id="cf31f-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="cf31f-107">Queste query possono influire sulle prestazioni generali del server.</span><span class="sxs-lookup"><span data-stu-id="cf31f-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="cf31f-108">Per ulteriori informazioni sulla trasformazione Raggruppamento fuzzy, vedere [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cf31f-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cf31f-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cf31f-109">Options</span></span>  
 <span data-ttu-id="cf31f-110">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="cf31f-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="cf31f-111">Consente di selezionare una gestione connessione OLE DB esistente usando la casella di riepilogo o di creare una nuova connessione tramite il pulsante **Nuova** .</span><span class="sxs-lookup"><span data-stu-id="cf31f-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="cf31f-112">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="cf31f-112">**New**</span></span>  
 <span data-ttu-id="cf31f-113">Consente di creare una nuova connessione usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="cf31f-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf31f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf31f-114">See Also</span></span>  
 <span data-ttu-id="cf31f-115">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cf31f-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="cf31f-116">Identificazione di righe di dati simili tramite la trasformazione Raggruppamento fuzzy</span><span class="sxs-lookup"><span data-stu-id="cf31f-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
