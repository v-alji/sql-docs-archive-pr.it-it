---
title: Proprietà personalizzate dell'origine XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636282"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="3c665-102">Proprietà personalizzate dell'origine XML</span><span class="sxs-lookup"><span data-stu-id="3c665-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="3c665-103">L'origine XML include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="3c665-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="3c665-104">Nella tabella seguente vengono descritte le proprietà personalizzate dell'origine XML.</span><span class="sxs-lookup"><span data-stu-id="3c665-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="3c665-105">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="3c665-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="3c665-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="3c665-106">Property name</span></span>|<span data-ttu-id="3c665-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3c665-107">Data Type</span></span>|<span data-ttu-id="3c665-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c665-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="3c665-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="3c665-109">AccessMode</span></span>|<span data-ttu-id="3c665-110">Integer</span><span class="sxs-lookup"><span data-stu-id="3c665-110">Integer</span></span>|<span data-ttu-id="3c665-111">Modalità utilizzata per accedere ai dati XML.</span><span class="sxs-lookup"><span data-stu-id="3c665-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="3c665-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="3c665-112">UseInlineSchema</span></span>|<span data-ttu-id="3c665-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="3c665-113">Boolean</span></span>|<span data-ttu-id="3c665-114">Valore che indica se utilizzare una definizione dello schema inline all'interno dell'origine XML.</span><span class="sxs-lookup"><span data-stu-id="3c665-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="3c665-115">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="3c665-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="3c665-116">XMLData</span><span class="sxs-lookup"><span data-stu-id="3c665-116">XMLData</span></span>|<span data-ttu-id="3c665-117">string</span><span class="sxs-lookup"><span data-stu-id="3c665-117">String</span></span>|<span data-ttu-id="3c665-118">File o variabili da cui recuperare i dati XML.</span><span class="sxs-lookup"><span data-stu-id="3c665-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="3c665-119">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c665-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="3c665-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="3c665-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="3c665-121">string</span><span class="sxs-lookup"><span data-stu-id="3c665-121">String</span></span>|<span data-ttu-id="3c665-122">Percorso e nome del file di definizione dello schema (estensione xsd).</span><span class="sxs-lookup"><span data-stu-id="3c665-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="3c665-123">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c665-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="3c665-124">Nella tabella seguente vengono descritte le proprietà personalizzate dell'output dell'origine XML.</span><span class="sxs-lookup"><span data-stu-id="3c665-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="3c665-125">Tutte le proprietà sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="3c665-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="3c665-126">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="3c665-126">Property name</span></span>|<span data-ttu-id="3c665-127">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3c665-127">Data Type</span></span>|<span data-ttu-id="3c665-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c665-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="3c665-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="3c665-129">RowsetID</span></span>|<span data-ttu-id="3c665-130">string</span><span class="sxs-lookup"><span data-stu-id="3c665-130">String</span></span>|<span data-ttu-id="3c665-131">Valore che identifica il set di righe associato all'output.</span><span class="sxs-lookup"><span data-stu-id="3c665-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="3c665-132">Le colonne di output dell'origine XML non includono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="3c665-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="3c665-133">Per altre informazioni, vedere [Origine XML](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="3c665-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c665-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c665-134">See Also</span></span>  
 [<span data-ttu-id="3c665-135">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="3c665-135">Common Properties</span></span>](../common-properties.md)  
  
  
