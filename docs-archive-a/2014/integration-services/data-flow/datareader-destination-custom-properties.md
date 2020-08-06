---
title: Proprietà personalizzate della destinazione DataReader | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629525"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="1c062-102">Proprietà personalizzate della destinazione DataReader</span><span class="sxs-lookup"><span data-stu-id="1c062-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="1c062-103">La destinazione DataReader include sia proprietà personalizzate che le proprietà comuni a tutti i componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="1c062-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="1c062-104">Nella tabella seguente vengono descritte le proprietà personalizzate della destinazione DataReader.</span><span class="sxs-lookup"><span data-stu-id="1c062-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="1c062-105">Tutte le proprietà, ad eccezione di `DataReader`, sono di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="1c062-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="1c062-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="1c062-106">Property name</span></span>|<span data-ttu-id="1c062-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1c062-107">Data Type</span></span>|<span data-ttu-id="1c062-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c062-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="1c062-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="1c062-109">DataReader</span></span>|<span data-ttu-id="1c062-110">string</span><span class="sxs-lookup"><span data-stu-id="1c062-110">String</span></span>|<span data-ttu-id="1c062-111">Nome di classe della destinazione DataReader.</span><span class="sxs-lookup"><span data-stu-id="1c062-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="1c062-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="1c062-112">FailOnTimeout</span></span>|<span data-ttu-id="1c062-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="1c062-113">Boolean</span></span>|<span data-ttu-id="1c062-114">Indica se generare un errore quando si verifica un `ReadTimeout`.</span><span class="sxs-lookup"><span data-stu-id="1c062-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="1c062-115">Il valore predefinito di questa proprietà è **False**.</span><span class="sxs-lookup"><span data-stu-id="1c062-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="1c062-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="1c062-116">ReadTimeout</span></span>|<span data-ttu-id="1c062-117">Integer</span><span class="sxs-lookup"><span data-stu-id="1c062-117">Integer</span></span>|<span data-ttu-id="1c062-118">Numero di millisecondi prima di un timeout.</span><span class="sxs-lookup"><span data-stu-id="1c062-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="1c062-119">Il valore predefinito di questa proprietà è 30000 (30 secondi).</span><span class="sxs-lookup"><span data-stu-id="1c062-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="1c062-120">L'input e le colonne di input della destinazione DataReader non includono proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1c062-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="1c062-121">Per altre informazioni, vedere [Destinazione DataReader](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="1c062-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c062-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c062-122">See Also</span></span>  
 [<span data-ttu-id="1c062-123">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="1c062-123">Common Properties</span></span>](../common-properties.md)  
  
  
