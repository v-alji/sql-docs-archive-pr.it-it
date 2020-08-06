---
title: Elemento Server (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: 9fe0bfb4-3aa6-4eb2-a83e-c0d0e7d4e9f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ab67e0303c2b629c3774886441474f5ef5b10a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635304"
---
# <a name="server-element-dta"></a><span data-ttu-id="db354-102">Elemento Server (DTA)</span><span class="sxs-lookup"><span data-stu-id="db354-102">Server Element (DTA)</span></span>
  <span data-ttu-id="db354-103">Contiene le informazioni di identificazione del server sul quale risiede il database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="db354-103">Contains the identifying information for the server on which the databases reside that you want to tune.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db354-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db354-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
    ...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="db354-105">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="db354-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="db354-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="db354-106">Characteristic</span></span>|<span data-ttu-id="db354-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db354-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="db354-108">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="db354-108">**Data type and length**</span></span>|<span data-ttu-id="db354-109">No.</span><span class="sxs-lookup"><span data-stu-id="db354-109">None.</span></span>|  
|<span data-ttu-id="db354-110">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="db354-110">**Default value**</span></span>|<span data-ttu-id="db354-111">No.</span><span class="sxs-lookup"><span data-stu-id="db354-111">None.</span></span>|  
|<span data-ttu-id="db354-112">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="db354-112">**Occurrence**</span></span>|<span data-ttu-id="db354-113">Obbligatorio una volta per ogni elemento di `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="db354-113">Required once per `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="db354-114">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="db354-114">Element Relationships</span></span>  
  
|<span data-ttu-id="db354-115">Relazione</span><span class="sxs-lookup"><span data-stu-id="db354-115">Relationship</span></span>|<span data-ttu-id="db354-116">Elementi</span><span class="sxs-lookup"><span data-stu-id="db354-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="db354-117">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="db354-117">**Parent element**</span></span>|[<span data-ttu-id="db354-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="db354-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="db354-119">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="db354-119">**Child elements**</span></span>|[<span data-ttu-id="db354-120">Elemento Name per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="db354-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="db354-121">Elemento Database per Server &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="db354-121">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="db354-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db354-122">Remarks</span></span>  
 <span data-ttu-id="db354-123">È possibile specificare un solo `Server` elemento per l' `DTAInput` elemento.</span><span class="sxs-lookup"><span data-stu-id="db354-123">You can specify only one `Server` element for the `DTAInput` element.</span></span> <span data-ttu-id="db354-124">Questo elemento appartiene al nome **ServerDetailsTypecomplexType** nell'XML Schema di DTA.</span><span class="sxs-lookup"><span data-stu-id="db354-124">This element is of the **ServerDetailsTypecomplexType** name in the DTA XML schema.</span></span> <span data-ttu-id="db354-125">Questo elemento `Server` non deve essere confuso con l'elemento figlio di `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="db354-125">Do not confuse this `Server` element with the one that is the child of the `Configuration` element.</span></span> <span data-ttu-id="db354-126">Per altre informazioni, vedere [Elemento Server per Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="db354-126">For more information, see [Server Element for Configuration &#40;DTA&#41;](server-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db354-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="db354-127">Example</span></span>  
 <span data-ttu-id="db354-128">L'esempio seguente mostra come specificare la tabella **Sales.SalesPerson** nel database **AdventureWorks** in SERVER001:</span><span class="sxs-lookup"><span data-stu-id="db354-128">The following example shows how to specify the **Sales.SalesPerson** table in the **AdventureWorks** database on SERVER001:</span></span>  
  
```xml  
<Server>  
  <Name>SERVER001</Name>  
  <Database>  
    <Name>AdventureWorks</Name>  
    <Schema>  
      <Name>Sales</Name>  
      <Table>  
        <Name>SalesPerson</Name>  
      </Table>  
    </Schema>  
  </Database>  
</Server  
```  
  
## <a name="see-also"></a><span data-ttu-id="db354-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db354-129">See Also</span></span>  
 [<span data-ttu-id="db354-130">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="db354-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
