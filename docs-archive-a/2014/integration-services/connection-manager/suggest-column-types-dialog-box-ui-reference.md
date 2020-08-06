---
title: Riferimento all'interfaccia utente della finestra di dialogo Suggerisci tipi di colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.suggestdatatypes.f1
ms.assetid: 8d5652e0-cf57-483f-828b-10f00c08418b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbca2a3186a58b1148eb9627825fdfddf334339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724860"
---
# <a name="suggest-column-types-dialog-box-ui-reference"></a><span data-ttu-id="dc6c4-102">Riferimento all'interfaccia utente della finestra di dialogo Suggerisci tipi di colonne</span><span class="sxs-lookup"><span data-stu-id="dc6c4-102">Suggest Column Types Dialog Box UI Reference</span></span>
  <span data-ttu-id="dc6c4-103">Utilizzare la finestra di dialogo **Suggerisci tipi di colonne** per identificare il tipo di dati e la lunghezza delle colonne nella gestione connessione file flat sulla base di un campionamento del contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-103">Use the **Suggest Column Types** dialog box to identify the data type and length of columns in a Flat File Connection Manager based on a sampling of the file content.</span></span>  
  
 <span data-ttu-id="dc6c4-104">Per altre informazioni sui tipi di dati usati da [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vedere [Tipi di dati di Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="dc6c4-104">To learn more about the data types used by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dc6c4-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dc6c4-105">Options</span></span>  
 <span data-ttu-id="dc6c4-106">**Numero di righe**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-106">**Number of rows**</span></span>  
 <span data-ttu-id="dc6c4-107">Consente di digitare o selezionare il numero di righe nel campione utilizzato dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-107">Type or select the number of rows in the sample that the algorithm uses.</span></span>  
  
 <span data-ttu-id="dc6c4-108">**Suggerisci tipo di dati integer più piccolo**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-108">**Suggest the smallest integer data type**</span></span>  
 <span data-ttu-id="dc6c4-109">Deselezionare questa casella di controllo per ignorare la valutazione.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-109">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="dc6c4-110">Se questa casella di controllo è selezionata, viene determinato il tipo di dati integer più piccolo possibile per le colonne che contengono dati numerici integrali.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-110">If selected, determines the smallest possible integer data type for columns that contain integral numeric data.</span></span>  
  
 <span data-ttu-id="dc6c4-111">**Suggerisci tipo di dati real più piccolo**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-111">**Suggest the smallest real data type**</span></span>  
 <span data-ttu-id="dc6c4-112">Deselezionare questa casella di controllo per ignorare la valutazione.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-112">Clear this check box to skip the assessment.</span></span> <span data-ttu-id="dc6c4-113">Se questa casella di controllo è selezionata, viene determinato se le colonne contenenti dati numerici real possono utilizzare il tipo di dati real più piccolo, ovvero DT_R4.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-113">If selected, determines whether columns that contain real numeric data can use the smaller real data type, DT_R4.</span></span>  
  
 <span data-ttu-id="dc6c4-114">**Identifica colonne booleane con i valori seguenti**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-114">**Identify Boolean columns using the following values**</span></span>  
 <span data-ttu-id="dc6c4-115">Consente di digitare i due valori che si desidera utilizzare come valori booleani true e false.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-115">Type the two values that you want to use as the Boolean values true and false.</span></span> <span data-ttu-id="dc6c4-116">Digitare i valori separati da una virgola. Il primo valore rappresenta il valore True.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-116">The values must be separated by a comma, and the first value represents True.</span></span>  
  
 <span data-ttu-id="dc6c4-117">**Consenti riempimento colonne stringa**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-117">**Pad string columns**</span></span>  
 <span data-ttu-id="dc6c4-118">Selezionare questa casella di controllo per attivare il riempimento della stringa.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-118">Select this check box to enable string padding.</span></span>  
  
 <span data-ttu-id="dc6c4-119">**Percentuale di riempimento**</span><span class="sxs-lookup"><span data-stu-id="dc6c4-119">**Percent padding**</span></span>  
 <span data-ttu-id="dc6c4-120">Consente di digitare o selezionare la percentuale della lunghezza delle colonne in base alla quale deve essere aumentata la lunghezza delle colonne per i tipi di dati character.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-120">Type or select the percentage of the column lengths by which to increase the length of columns for character data types.</span></span> <span data-ttu-id="dc6c4-121">La percentuale deve essere un numero intero.</span><span class="sxs-lookup"><span data-stu-id="dc6c4-121">The percentage must be an integer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6c4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc6c4-122">See Also</span></span>  
 <span data-ttu-id="dc6c4-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dc6c4-123">[Integration Services Error and Message Reference](../integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="dc6c4-124">Gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="dc6c4-124">Flat File Connection Manager</span></span>](file-connection-manager.md)  
  
  
