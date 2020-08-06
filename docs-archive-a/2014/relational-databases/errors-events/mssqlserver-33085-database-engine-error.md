---
title: MSSQLSERVER_33085 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627764"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="9e656-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="9e656-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="9e656-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9e656-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e656-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9e656-104">Product Name</span></span>|<span data-ttu-id="9e656-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e656-105">SQL Server</span></span>|  
|<span data-ttu-id="9e656-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9e656-106">Event ID</span></span>|<span data-ttu-id="9e656-107">33085</span><span class="sxs-lookup"><span data-stu-id="9e656-107">33085</span></span>|  
|<span data-ttu-id="9e656-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9e656-108">Event Source</span></span>|<span data-ttu-id="9e656-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9e656-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9e656-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9e656-110">Component</span></span>|<span data-ttu-id="9e656-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9e656-111">SQLEngine</span></span>|  
|<span data-ttu-id="9e656-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9e656-112">Symbolic Name</span></span>|<span data-ttu-id="9e656-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9e656-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="9e656-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9e656-114">Message Text</span></span>|<span data-ttu-id="9e656-115">Impossibile trovare uno o più metodi nella libreria del provider del servizio di crittografia '%.\* ls.'</span><span class="sxs-lookup"><span data-stu-id="9e656-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e656-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9e656-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9e656-117">non è stato in grado di usare il provider del servizio di crittografia elencato nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9e656-117">was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="9e656-118">Il provider del servizio di crittografia non supporta un metodo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e656-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="9e656-119">Lo stato dell'errore indica il metodo non trovato.</span><span class="sxs-lookup"><span data-stu-id="9e656-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="9e656-120">State</span><span class="sxs-lookup"><span data-stu-id="9e656-120">State</span></span>|<span data-ttu-id="9e656-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e656-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e656-122">1</span><span class="sxs-lookup"><span data-stu-id="9e656-122">1</span></span>|<span data-ttu-id="9e656-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="9e656-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="9e656-124">2</span><span class="sxs-lookup"><span data-stu-id="9e656-124">2</span></span>|<span data-ttu-id="9e656-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="9e656-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="9e656-126">3</span><span class="sxs-lookup"><span data-stu-id="9e656-126">3</span></span>|<span data-ttu-id="9e656-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="9e656-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="9e656-128">4</span><span class="sxs-lookup"><span data-stu-id="9e656-128">4</span></span>|<span data-ttu-id="9e656-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="9e656-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="9e656-130">5</span><span class="sxs-lookup"><span data-stu-id="9e656-130">5</span></span>|<span data-ttu-id="9e656-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="9e656-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="9e656-132">6</span><span class="sxs-lookup"><span data-stu-id="9e656-132">6</span></span>|<span data-ttu-id="9e656-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="9e656-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="9e656-134">7</span><span class="sxs-lookup"><span data-stu-id="9e656-134">7</span></span>|<span data-ttu-id="9e656-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="9e656-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="9e656-136">8</span><span class="sxs-lookup"><span data-stu-id="9e656-136">8</span></span>|<span data-ttu-id="9e656-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="9e656-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="9e656-138">9</span><span class="sxs-lookup"><span data-stu-id="9e656-138">9</span></span>|<span data-ttu-id="9e656-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="9e656-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="9e656-140">10</span><span class="sxs-lookup"><span data-stu-id="9e656-140">10</span></span>|<span data-ttu-id="9e656-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="9e656-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="9e656-142">11</span><span class="sxs-lookup"><span data-stu-id="9e656-142">11</span></span>|<span data-ttu-id="9e656-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="9e656-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="9e656-144">12</span><span class="sxs-lookup"><span data-stu-id="9e656-144">12</span></span>|<span data-ttu-id="9e656-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="9e656-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="9e656-146">13</span><span class="sxs-lookup"><span data-stu-id="9e656-146">13</span></span>|<span data-ttu-id="9e656-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="9e656-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="9e656-148">14</span><span class="sxs-lookup"><span data-stu-id="9e656-148">14</span></span>|<span data-ttu-id="9e656-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="9e656-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="9e656-150">15</span><span class="sxs-lookup"><span data-stu-id="9e656-150">15</span></span>|<span data-ttu-id="9e656-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="9e656-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="9e656-152">16</span><span class="sxs-lookup"><span data-stu-id="9e656-152">16</span></span>|<span data-ttu-id="9e656-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="9e656-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="9e656-154">17</span><span class="sxs-lookup"><span data-stu-id="9e656-154">17</span></span>|<span data-ttu-id="9e656-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="9e656-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="9e656-156">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9e656-156">User Action</span></span>  
 <span data-ttu-id="9e656-157">Per ulteriori informazioni, contattare il provider del servizio di crittografia.</span><span class="sxs-lookup"><span data-stu-id="9e656-157">Contact the cryptographic provider for more information.</span></span>  
  
  
