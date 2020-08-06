---
title: Finestra di dialogo Proprietà set di dati, campi | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasetproperties.fields.f1
- "10140"
ms.assetid: e1367556-736e-4a6b-b9e7-10432a3e50b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b9d315f85751c0f73896e809a522613fefece5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625241"
---
# <a name="dataset-properties-dialog-box-fields"></a><span data-ttu-id="bfe93-102">Finestra di dialogo Proprietà set di dati, Campi</span><span class="sxs-lookup"><span data-stu-id="bfe93-102">Dataset Properties Dialog Box, Fields</span></span>
  <span data-ttu-id="bfe93-103">Selezionare **Campi** nella finestra di dialogo **Proprietà set di dati** per modificare la raccolta di campi per il set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="bfe93-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="bfe93-104">L'elenco dei campi viene generato automaticamente, tuttavia è possibile usare la scheda **Campi** per aggiungere, modificare ed eliminare campi di query e calcolati.</span><span class="sxs-lookup"><span data-stu-id="bfe93-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bfe93-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bfe93-105">Options</span></span>  
 <span data-ttu-id="bfe93-106">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="bfe93-106">**Add**</span></span>  
 <span data-ttu-id="bfe93-107">Consente di aggiungere un nuovo campo di query o campo calcolato al set di dati.</span><span class="sxs-lookup"><span data-stu-id="bfe93-107">Add a new query field or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="bfe93-108">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="bfe93-108">**Delete**</span></span>  
 <span data-ttu-id="bfe93-109">Consente di eliminare il campo selezionato dal set di dati.</span><span class="sxs-lookup"><span data-stu-id="bfe93-109">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="bfe93-110">**Nome campo**</span><span class="sxs-lookup"><span data-stu-id="bfe93-110">**Field Name**</span></span>  
 <span data-ttu-id="bfe93-111">Consente di digitare un nome per il campo.</span><span class="sxs-lookup"><span data-stu-id="bfe93-111">Type a name for the field.</span></span> <span data-ttu-id="bfe93-112">Il campo deve essere univoco nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="bfe93-112">The field must be unique within the dataset.</span></span> <span data-ttu-id="bfe93-113">Per ogni campo esistente nella query del set di dati, il nome viene prepopolato.</span><span class="sxs-lookup"><span data-stu-id="bfe93-113">For each existing field in the dataset query, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="bfe93-114">**Origine campo**</span><span class="sxs-lookup"><span data-stu-id="bfe93-114">**Field Source**</span></span>  
 <span data-ttu-id="bfe93-115">Immettere un valore per il campo.</span><span class="sxs-lookup"><span data-stu-id="bfe93-115">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="bfe93-116">Per un campo calcolato, l'origine del campo deve essere il nome di un campo esistente recuperato dalla query del set di dati o da un'espressione creata.</span><span class="sxs-lookup"><span data-stu-id="bfe93-116">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="bfe93-117">Ad esempio, per creare un campo che rappresenta 10 volte il valore nel campo Sales della query, utilizzare l'espressione `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="bfe93-117">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="bfe93-118">Per un campo query, l'origine del campo deve essere il nome di un campo esistente recuperato dalla query del set di dati.</span><span class="sxs-lookup"><span data-stu-id="bfe93-118">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="bfe93-119">**Espressione (fx)**</span><span class="sxs-lookup"><span data-stu-id="bfe93-119">**Expression (fx)**</span></span>  
 <span data-ttu-id="bfe93-120">Consente di aggiungere o modificare un'espressione per il campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="bfe93-120">Add or change an expression for the calculated field.</span></span> <span data-ttu-id="bfe93-121">Questo pulsante viene visualizzato solo quando si fa clic su **Aggiungi** e si seleziona **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="bfe93-121">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe93-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfe93-122">See Also</span></span>  
 <span data-ttu-id="bfe93-123">[Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bfe93-123">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bfe93-124">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bfe93-124">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="bfe93-125">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe93-125">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
