---
title: Proprietà personalizzate del file flat | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726100"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="64781-102">Proprietà personalizzate del file flat</span><span class="sxs-lookup"><span data-stu-id="64781-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="64781-103">**Proprietà personalizzate delle origini**</span><span class="sxs-lookup"><span data-stu-id="64781-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="64781-104">L'origine file flat include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="64781-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="64781-105">Nella tabella seguente vengono descritte le proprietà personalizzate dell'origine file flat.</span><span class="sxs-lookup"><span data-stu-id="64781-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="64781-106">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="64781-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="64781-107">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="64781-107">Property name</span></span>|<span data-ttu-id="64781-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="64781-108">Data Type</span></span>|<span data-ttu-id="64781-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64781-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="64781-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="64781-110">FileNameColumnName</span></span>|<span data-ttu-id="64781-111">string</span><span class="sxs-lookup"><span data-stu-id="64781-111">String</span></span>|<span data-ttu-id="64781-112">Nome di una colonna di output contenente il nome file.</span><span class="sxs-lookup"><span data-stu-id="64781-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="64781-113">Se non si specifica alcun nome, non verrà generata alcuna colonna contenente il nome file.</span><span class="sxs-lookup"><span data-stu-id="64781-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="64781-114">Nota: questa proprietà non è disponibile in **Editor origine file flat**, ma può essere impostata tramite **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="64781-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="64781-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="64781-115">RetainNulls</span></span>|<span data-ttu-id="64781-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="64781-116">Boolean</span></span>|<span data-ttu-id="64781-117">Valore che specifica se i valori Null dal file di origine devono essere mantenuti come tali durante l'elaborazione dei dati tramite il motore della pipeline di trasformazione dati.</span><span class="sxs-lookup"><span data-stu-id="64781-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="64781-118">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="64781-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="64781-119">L'output dell'origine file flat non include proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="64781-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="64781-120">Nella tabella seguente vengono descritte le proprietà personalizzate delle colonne di output dell'origine file flat.</span><span class="sxs-lookup"><span data-stu-id="64781-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="64781-121">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="64781-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="64781-122">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="64781-122">Property name</span></span>|<span data-ttu-id="64781-123">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="64781-123">Data Type</span></span>|<span data-ttu-id="64781-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64781-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="64781-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="64781-125">FastParse</span></span>|<span data-ttu-id="64781-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="64781-126">Boolean</span></span>|<span data-ttu-id="64781-127">Valore che indica se la colonna utilizza le routine di analisi più veloci ma indipendenti dalle impostazioni locali disponibili in DTS oppure le routine di analisi standard dipendenti dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="64781-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="64781-128">Per altre informazioni, vedere [Analisi veloce](../fast-parse.md) e [Analisi standard](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="64781-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="64781-129">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="64781-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="64781-130">Nota: questa proprietà non è disponibile in **Editor origine file flat**, ma può essere impostata tramite **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="64781-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="64781-131">Per altre informazioni, vedere [Origine file flat](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="64781-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="64781-132">**Proprietà personalizzate delle destinazioni**</span><span class="sxs-lookup"><span data-stu-id="64781-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="64781-133">La destinazione file flat include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="64781-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="64781-134">Nella tabella seguente vengono descritte le proprietà personalizzate della destinazione file flat.</span><span class="sxs-lookup"><span data-stu-id="64781-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="64781-135">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="64781-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="64781-136">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="64781-136">Property name</span></span>|<span data-ttu-id="64781-137">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="64781-137">Data Type</span></span>|<span data-ttu-id="64781-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64781-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="64781-139">Intestazione</span><span class="sxs-lookup"><span data-stu-id="64781-139">Header</span></span>|<span data-ttu-id="64781-140">string</span><span class="sxs-lookup"><span data-stu-id="64781-140">String</span></span>|<span data-ttu-id="64781-141">Blocco di testo inserito nel file prima di iniziare a scrivere i dati.</span><span class="sxs-lookup"><span data-stu-id="64781-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="64781-142">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="64781-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="64781-143">Overwrite</span><span class="sxs-lookup"><span data-stu-id="64781-143">Overwrite</span></span>|<span data-ttu-id="64781-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="64781-144">Boolean</span></span>|<span data-ttu-id="64781-145">Valore che specifica se sovrascrivere o aggiungere dati a un file di destinazione esistente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="64781-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="64781-146">Il valore predefinito di questa proprietà è `True`.</span><span class="sxs-lookup"><span data-stu-id="64781-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="64781-147">L'input e le colonne di input della destinazione file flat non includono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="64781-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="64781-148">Per altre informazioni, vedere [Destinazione file flat](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="64781-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64781-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64781-149">See Also</span></span>  
 [<span data-ttu-id="64781-150">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="64781-150">Common Properties</span></span>](../common-properties.md)  
  
  
