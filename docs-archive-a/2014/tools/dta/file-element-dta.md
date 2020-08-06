---
title: Elemento File (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- File element
ms.assetid: 73dce835-9a80-4aef-8e0f-9dcf07dd5b80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0eeb2bdcc9513ca6283447daca63c8bbc4fa1726
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720663"
---
# <a name="file-element-dta"></a><span data-ttu-id="b3a3d-102">Elemento File (DTA)</span><span class="sxs-lookup"><span data-stu-id="b3a3d-102">File Element (DTA)</span></span>
  <span data-ttu-id="b3a3d-103">Specifica il file del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-103">Specifies the workload file.</span></span> <span data-ttu-id="b3a3d-104">Un carico di lavoro è un set di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sui database che si desidera ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-104">A workload is a set of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that execute against a database or databases that you want to tune.</span></span> <span data-ttu-id="b3a3d-105">I file del carico di lavoro possono essere costituiti da script [!INCLUDE[tsql](../../includes/tsql-md.md)] (sql) o file di traccia (trc).</span><span class="sxs-lookup"><span data-stu-id="b3a3d-105">Workload files can be [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts (.sql) or trace files (.trc).</span></span> <span data-ttu-id="b3a3d-106">Per altre informazioni, vedere [Avvio e utilizzo di Ottimizzazione guidata motore di database](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="b3a3d-106">For more information, see [Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3a3d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3a3d-107">Syntax</span></span>  
  
```  
  
<DTAInput>  
  <Server>...</Server>  
  <Workload>  
    <File>...</File>  
  </Workload>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="b3a3d-108">Caratteristiche elemento</span><span class="sxs-lookup"><span data-stu-id="b3a3d-108">Element Characteristics</span></span>  
  
|<span data-ttu-id="b3a3d-109">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="b3a3d-109">Characteristic</span></span>|<span data-ttu-id="b3a3d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3a3d-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b3a3d-111">**Tipo di dati e lunghezza**</span><span class="sxs-lookup"><span data-stu-id="b3a3d-111">**Data type and length**</span></span>|<span data-ttu-id="b3a3d-112">Utilizzare il tipo di dati `string` per specificare il percorso della directory del file del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-112">Use the `string` data type to specify the directory path to your workload file.</span></span> <span data-ttu-id="b3a3d-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b3a3d-113">For example:</span></span><br /><br /> `<File>C:\Tuning\tun.sql</File>`<br /><br /> <span data-ttu-id="b3a3d-114">Il limite della lunghezza è imposto dal server.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-114">Length limit is enforced by the server.</span></span>|  
|<span data-ttu-id="b3a3d-115">**Valore predefinito**</span><span class="sxs-lookup"><span data-stu-id="b3a3d-115">**Default value**</span></span>|<span data-ttu-id="b3a3d-116">No.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-116">None.</span></span>|  
|<span data-ttu-id="b3a3d-117">**Occorrenza**</span><span class="sxs-lookup"><span data-stu-id="b3a3d-117">**Occurrence**</span></span>|<span data-ttu-id="b3a3d-118">Obbligatorio una sola volta se non viene specificato un altro tipo di carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-118">Required once if no other type of workload is specified.</span></span> <span data-ttu-id="b3a3d-119">È necessario specificare un elemento figlio **EventString**, **File**o **Database** per l'elemento padre **Workload** , ma è possibile utilizzare un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-119">You must specify an **EventString**, a **File**, or a **Database** child element for the **Workload** parent, but only one type can be used.</span></span> <span data-ttu-id="b3a3d-120">Se ad esempio si specifica un carico di lavoro con l'elemento **File** , non sarà possibile specificare anche un carico di lavoro con l'elemento **Database** nello stesso file di input XML.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-120">For example, if you specify a workload with the **File** element, then you cannot also specify a workload with the **Database** element in the same XML input file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="b3a3d-121">Relazioni elemento</span><span class="sxs-lookup"><span data-stu-id="b3a3d-121">Element Relationships</span></span>  
  
|<span data-ttu-id="b3a3d-122">Relazione</span><span class="sxs-lookup"><span data-stu-id="b3a3d-122">Relationship</span></span>|<span data-ttu-id="b3a3d-123">Elementi</span><span class="sxs-lookup"><span data-stu-id="b3a3d-123">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="b3a3d-124">**Elemento padre**</span><span class="sxs-lookup"><span data-stu-id="b3a3d-124">**Parent element**</span></span>|[<span data-ttu-id="b3a3d-125">Elemento Workload &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a3d-125">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)|  
|<span data-ttu-id="b3a3d-126">**Elementi figlio**</span><span class="sxs-lookup"><span data-stu-id="b3a3d-126">**Child elements**</span></span>|<span data-ttu-id="b3a3d-127">No.</span><span class="sxs-lookup"><span data-stu-id="b3a3d-127">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b3a3d-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3a3d-128">Example</span></span>  
 <span data-ttu-id="b3a3d-129">Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="b3a3d-129">For a usage example of this element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a3d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3a3d-130">See Also</span></span>  
 [<span data-ttu-id="b3a3d-131">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a3d-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
