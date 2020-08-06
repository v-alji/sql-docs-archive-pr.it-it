---
title: Convalida dei dati (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628785"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="a8168-102">Convalida dei dati (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="a8168-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="a8168-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]quando si pubblicano i dati, vengono eseguiti due tipi di convalida:</span><span class="sxs-lookup"><span data-stu-id="a8168-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="a8168-104">Tutte le regole business definite sono applicate ai dati.</span><span class="sxs-lookup"><span data-stu-id="a8168-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="a8168-105">I dati vengono controllati in base ai valori di attributo consentiti (ad esempio il numero di caratteri o il tipo di dati).</span><span class="sxs-lookup"><span data-stu-id="a8168-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="a8168-106">In ogni caso, i dati validi vengono pubblicati nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a8168-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="a8168-107">I dati non validi vengono evidenziati e i dettagli dell'errore possono essere visualizzati nelle colonne di stato.</span><span class="sxs-lookup"><span data-stu-id="a8168-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="a8168-108">Esecuzione della convalida</span><span class="sxs-lookup"><span data-stu-id="a8168-108">When Validation Occurs</span></span>  
 <span data-ttu-id="a8168-109">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]la convalida viene eseguita quando si pubblicano dati nuovi o modificati oppure quando si applicano manualmente regole business.</span><span class="sxs-lookup"><span data-stu-id="a8168-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="a8168-110">Quando le regole business hanno esito negativo, i dati vengono comunque pubblicati nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a8168-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="a8168-111">Quando la convalida dell'input ha esito negativo, i dati non vengono pubblicati nel repository.</span><span class="sxs-lookup"><span data-stu-id="a8168-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="a8168-112">Stati di convalida</span><span class="sxs-lookup"><span data-stu-id="a8168-112">Validation Statuses</span></span>  
 <span data-ttu-id="a8168-113">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]sono possibili gli stati di convalida seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8168-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="a8168-114">Stato</span><span class="sxs-lookup"><span data-stu-id="a8168-114">Status</span></span>|<span data-ttu-id="a8168-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8168-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a8168-116">Errore</span><span class="sxs-lookup"><span data-stu-id="a8168-116">Error</span></span>|<span data-ttu-id="a8168-117">Si è verificato un errore di convalida di uno o più valori nella riga in base alle regole business definite da un amministratore di MDS.</span><span class="sxs-lookup"><span data-stu-id="a8168-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="a8168-118">Non convalidato</span><span class="sxs-lookup"><span data-stu-id="a8168-118">Not Validated</span></span>|<span data-ttu-id="a8168-119">I valori nella riga non sono ancora stati convalidati in base alle regole business.</span><span class="sxs-lookup"><span data-stu-id="a8168-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="a8168-120">Operazione completata</span><span class="sxs-lookup"><span data-stu-id="a8168-120">Success</span></span>|<span data-ttu-id="a8168-121">Tutti i valori nella riga sono stati convalidati in base alle regole business.</span><span class="sxs-lookup"><span data-stu-id="a8168-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="a8168-122">Stati di input</span><span class="sxs-lookup"><span data-stu-id="a8168-122">Input Statuses</span></span>  
 <span data-ttu-id="a8168-123">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]sono possibili gli stati di input seguenti</span><span class="sxs-lookup"><span data-stu-id="a8168-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="a8168-124">Stato</span><span class="sxs-lookup"><span data-stu-id="a8168-124">Status</span></span>|<span data-ttu-id="a8168-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8168-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a8168-126">Errore</span><span class="sxs-lookup"><span data-stu-id="a8168-126">Error</span></span>|<span data-ttu-id="a8168-127">Uno o più valori nella riga non soddisfano i requisiti di sistema, come la lunghezza o il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a8168-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="a8168-128">Il valore non è aggiornato nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a8168-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="a8168-129">Nuova riga</span><span class="sxs-lookup"><span data-stu-id="a8168-129">New Row</span></span>|<span data-ttu-id="a8168-130">I valori nella riga non sono ancora stati pubblicati nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a8168-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="a8168-131">Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a8168-131">Read Only</span></span>|<span data-ttu-id="a8168-132">L'utente che ha eseguito l'accesso dispone di autorizzazioni di sola lettura per uno o più valori nella riga e non è possibile aggiornare il valore o i valori.</span><span class="sxs-lookup"><span data-stu-id="a8168-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="a8168-133">Non modificato</span><span class="sxs-lookup"><span data-stu-id="a8168-133">Unchanged</span></span>|<span data-ttu-id="a8168-134">Nessun valore nella riga è stato modificato nel foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8168-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="a8168-135">Ciò non significa che i valori nel repository non sono stati modificati. Per ottenere i dati più recenti nel foglio, fare clic su **Carica o aggiorna** nel gruppo **Connetti e carica**.</span><span class="sxs-lookup"><span data-stu-id="a8168-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="a8168-136">Questa è l'impostazione predefinita per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a8168-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="a8168-137">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a8168-137">Related Tasks</span></span>  
  
|<span data-ttu-id="a8168-138">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="a8168-138">Task Description</span></span>|<span data-ttu-id="a8168-139">Argomento</span><span class="sxs-lookup"><span data-stu-id="a8168-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="a8168-140">Determinare quali valori non passano le regole business definite.</span><span class="sxs-lookup"><span data-stu-id="a8168-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="a8168-141">Applicare le regole di business &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a8168-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="a8168-142">Per correggere gli errori di convalida, visualizzare tutte le transazioni eseguite per un membro.</span><span class="sxs-lookup"><span data-stu-id="a8168-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="a8168-143">Visualizzare tutte le annotazioni o transazioni per un membro &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a8168-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="a8168-144">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a8168-144">Related Content</span></span>  
  
-   [<span data-ttu-id="a8168-145">Pubblicazione dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a8168-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
