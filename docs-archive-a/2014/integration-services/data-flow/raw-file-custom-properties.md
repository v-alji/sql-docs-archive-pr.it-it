---
title: Proprietà personalizzate del file non elaborato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626174"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="55d49-102">Proprietà personalizzate del file non elaborato</span><span class="sxs-lookup"><span data-stu-id="55d49-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="55d49-103">**Proprietà personalizzate delle origini**</span><span class="sxs-lookup"><span data-stu-id="55d49-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="55d49-104">L'origine file non elaborato include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="55d49-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="55d49-105">Nella tabella seguente vengono descritte le proprietà personalizzate dell'origine file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="55d49-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="55d49-106">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="55d49-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="55d49-107">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="55d49-107">Property name</span></span>|<span data-ttu-id="55d49-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="55d49-108">Data Type</span></span>|<span data-ttu-id="55d49-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55d49-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="55d49-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="55d49-110">AccessMode</span></span>|<span data-ttu-id="55d49-111">Integer (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="55d49-111">Integer (enumeration)</span></span>|<span data-ttu-id="55d49-112">Modalità utilizzata per accedere ai dati non elaborati.</span><span class="sxs-lookup"><span data-stu-id="55d49-112">The mode used to access the raw data.</span></span> <span data-ttu-id="55d49-113">I valori possibili sono `File name` (0) e `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="55d49-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="55d49-114">Il valore predefinito è `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="55d49-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="55d49-115">FileName</span><span class="sxs-lookup"><span data-stu-id="55d49-115">FileName</span></span>|<span data-ttu-id="55d49-116">string</span><span class="sxs-lookup"><span data-stu-id="55d49-116">String</span></span>|<span data-ttu-id="55d49-117">Percorso e nome del file di origine.</span><span class="sxs-lookup"><span data-stu-id="55d49-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="55d49-118">L'output e le colonne di output dell'origine file non elaborato non includono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="55d49-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="55d49-119">Per ulteriori informazioni, vedere [Raw File Source](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="55d49-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="55d49-120">**Proprietà personalizzate delle destinazioni**</span><span class="sxs-lookup"><span data-stu-id="55d49-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="55d49-121">La destinazione file non elaborato include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="55d49-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="55d49-122">Nella tabella seguente vengono descritte le proprietà personalizzate della destinazione file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="55d49-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="55d49-123">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="55d49-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="55d49-124">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="55d49-124">Property name</span></span>|<span data-ttu-id="55d49-125">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="55d49-125">Data Type</span></span>|<span data-ttu-id="55d49-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55d49-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="55d49-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="55d49-127">AccessMode</span></span>|<span data-ttu-id="55d49-128">Integer (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="55d49-128">Integer (enumeration)</span></span>|<span data-ttu-id="55d49-129">Valore che specifica se la proprietà FileName include un nome file o il nome di una variabile che contiene un nome file.</span><span class="sxs-lookup"><span data-stu-id="55d49-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="55d49-130">Le opzioni valide sono `File name` (0) e `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="55d49-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="55d49-131">FileName</span><span class="sxs-lookup"><span data-stu-id="55d49-131">FileName</span></span>|<span data-ttu-id="55d49-132">string</span><span class="sxs-lookup"><span data-stu-id="55d49-132">String</span></span>|<span data-ttu-id="55d49-133">Nome del file in cui la destinazione file non elaborato scrive.</span><span class="sxs-lookup"><span data-stu-id="55d49-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="55d49-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="55d49-134">WriteOption</span></span>|<span data-ttu-id="55d49-135">Integer (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="55d49-135">Integer (enumeration)</span></span>|<span data-ttu-id="55d49-136">Valore che specifica se la destinazione file non elaborato elimina un file esistente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="55d49-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="55d49-137">Le opzioni valide sono `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) e `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="55d49-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="55d49-138">Il valore predefinito di questa proprietà è `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="55d49-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="55d49-139">È possibile eseguire un'operazione di aggiunta solo se i metadati dei dati aggiunti corrispondono a quelli dei dati già presenti nel file.</span><span class="sxs-lookup"><span data-stu-id="55d49-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="55d49-140">L'input e le colonne di input della destinazione file non elaborato non includono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="55d49-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="55d49-141">Per altre informazioni, vedere [Destinazione file non elaborato](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="55d49-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d49-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55d49-142">See Also</span></span>  
 [<span data-ttu-id="55d49-143">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="55d49-143">Common Properties</span></span>](../common-properties.md)  
  
  
