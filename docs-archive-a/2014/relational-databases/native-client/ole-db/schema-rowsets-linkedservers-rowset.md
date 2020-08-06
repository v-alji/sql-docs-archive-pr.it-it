---
title: Set di righe LINKEDSERVERS (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625356"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="73acf-102">Set di righe LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="73acf-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="73acf-103">Il set di righe **LINKEDSERVERS** enumera le origini dati dell'organizzazione che possono partecipare nelle query distribuite di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73acf-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="73acf-104">Il set di righe **LINKEDSERVERS** contiene le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="73acf-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="73acf-105">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="73acf-105">Column name</span></span>|<span data-ttu-id="73acf-106">Indicatore del tipo</span><span class="sxs-lookup"><span data-stu-id="73acf-106">Type indicator</span></span>|<span data-ttu-id="73acf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73acf-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="73acf-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="73acf-108">SVR_NAME</span></span>|<span data-ttu-id="73acf-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-110">Nome di un server collegato.</span><span class="sxs-lookup"><span data-stu-id="73acf-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="73acf-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="73acf-111">SVR_PRODUCT</span></span>|<span data-ttu-id="73acf-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-113">Produttore o altro nome che identifica il tipo di archivio dati rappresentato dal nome del server collegato.</span><span class="sxs-lookup"><span data-stu-id="73acf-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="73acf-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="73acf-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="73acf-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-116">Nome descrittivo del provider OLE DB impiegato per utilizzare dati dal server.</span><span class="sxs-lookup"><span data-stu-id="73acf-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="73acf-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="73acf-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="73acf-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-119">Stringa OLE DB DBPROP_INIT_DATASOURCE utilizzata per acquisire un'origine dati dal provider.</span><span class="sxs-lookup"><span data-stu-id="73acf-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="73acf-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="73acf-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="73acf-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-122">Valore OLE DB DBPROP_INIT_PROVIDERSTRING utilizzato per acquisire un'origine dati dal provider.</span><span class="sxs-lookup"><span data-stu-id="73acf-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="73acf-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="73acf-123">SVR_LOCATION</span></span>|<span data-ttu-id="73acf-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="73acf-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="73acf-125">Stringa OLE DB DBPROP_INIT_LOCATION utilizzata per acquisire un'origine dati dal provider.</span><span class="sxs-lookup"><span data-stu-id="73acf-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="73acf-126">Il set di righe viene ordinato su SRV_NAME e una singola restrizione è supportata su SRV_NAME.</span><span class="sxs-lookup"><span data-stu-id="73acf-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73acf-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73acf-127">See Also</span></span>  
 [<span data-ttu-id="73acf-128">Supporto del set di righe dello schema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="73acf-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
