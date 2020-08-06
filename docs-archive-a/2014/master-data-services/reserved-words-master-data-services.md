---
title: Parole riservate (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629458"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="2b790-102">Parole riservate (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2b790-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="2b790-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], quando si creano oggetti modello o membri, alcune parole non possono essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="2b790-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="2b790-104">È possibile che l'utilizzo di queste parole provochi errori.</span><span class="sxs-lookup"><span data-stu-id="2b790-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b790-105">Inoltre, è necessario limitare l'utilizzo di caratteri speciali (simboli, sillabazione e così via).</span><span class="sxs-lookup"><span data-stu-id="2b790-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="2b790-106">Modelli</span><span class="sxs-lookup"><span data-stu-id="2b790-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="2b790-107">Entità</span><span class="sxs-lookup"><span data-stu-id="2b790-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="2b790-108">Gerarchie esplicite</span><span class="sxs-lookup"><span data-stu-id="2b790-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="2b790-109">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="2b790-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="2b790-110">Membri</span><span class="sxs-lookup"><span data-stu-id="2b790-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="2b790-111">Modelli</span><span class="sxs-lookup"><span data-stu-id="2b790-111">Models</span></span>  
 <span data-ttu-id="2b790-112">Se si crea un modello con il nome impostato su **nome**, non selezionare **Crea entità con lo stesso nome del modello** perché non è possibile utilizzare il **nome** per il nome di un'entità.</span><span class="sxs-lookup"><span data-stu-id="2b790-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="2b790-113">Entità</span><span class="sxs-lookup"><span data-stu-id="2b790-113">Entities</span></span>  
 <span data-ttu-id="2b790-114">Per i nomi dell'entità, non è possibile utilizzare **Name** o **Code**.</span><span class="sxs-lookup"><span data-stu-id="2b790-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="2b790-115">Gerarchie esplicite</span><span class="sxs-lookup"><span data-stu-id="2b790-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="2b790-116">Per i nomi della gerarchia espliciti, non è possibile utilizzare **Name** o **Code**.</span><span class="sxs-lookup"><span data-stu-id="2b790-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="2b790-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b790-117">Attributes</span></span>  
  
-   <span data-ttu-id="2b790-118">**ID**</span><span class="sxs-lookup"><span data-stu-id="2b790-118">**ID**</span></span>  
  
-   <span data-ttu-id="2b790-119">**Codice**</span><span class="sxs-lookup"><span data-stu-id="2b790-119">**Code**</span></span>  
  
-   <span data-ttu-id="2b790-120">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2b790-120">**Name**</span></span>  
  
-   <span data-ttu-id="2b790-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="2b790-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="2b790-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="2b790-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="2b790-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="2b790-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="2b790-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="2b790-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="2b790-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="2b790-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="2b790-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="2b790-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="2b790-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="2b790-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="2b790-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="2b790-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="2b790-129">Membri</span><span class="sxs-lookup"><span data-stu-id="2b790-129">Members</span></span>  
 <span data-ttu-id="2b790-130">Per i membri, non è possibile usare **MDMMemberStatus** o **root** per il valore dell'attributo **Code** .</span><span class="sxs-lookup"><span data-stu-id="2b790-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b790-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b790-131">See Also</span></span>  
 [<span data-ttu-id="2b790-132">Panoramica di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="2b790-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
