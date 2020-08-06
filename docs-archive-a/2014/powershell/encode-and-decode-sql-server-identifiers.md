---
title: Codificare e decodificare identificatori di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713228"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="d7a85-102">Codificare e decodificare identificatori di SLQ Server</span><span class="sxs-lookup"><span data-stu-id="d7a85-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="d7a85-103">Gli identificatori delimitati di SQL Server possono contenere caratteri non supportati nei percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a85-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="d7a85-104">È possibile specificare questi caratteri codificando i valori esadecimali.</span><span class="sxs-lookup"><span data-stu-id="d7a85-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="d7a85-105">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="d7a85-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="d7a85-106">**Per elaborare caratteri speciali:**  [Codifica di un identificatore](#EncodeIdent), [Decodifica di un identificatore](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="d7a85-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d7a85-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d7a85-107">Before You Begin</span></span>  
 <span data-ttu-id="d7a85-108">I caratteri non supportati nei nomi dei percorsi di Windows PowerShell possono essere rappresentati o codificati come il carattere "%" seguito dal valore esadecimale per lo schema di bit che rappresenta il carattere, come in " **%** XX".</span><span class="sxs-lookup"><span data-stu-id="d7a85-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="d7a85-109">La codifica può sempre essere utilizzata per gestire i caratteri non supportati nei percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a85-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="d7a85-110">Il cmdlet **Encode-SqlName** accetta come input un identificatore di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7a85-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="d7a85-111">Viene restituita una stringa con tutti i caratteri non supportati dal linguaggio di Windows PowerShell codificati con "% xx".</span><span class="sxs-lookup"><span data-stu-id="d7a85-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="d7a85-112">Il cmdlet **Decode-SqlName** accetta come input un identificatore di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] codificato e restituisce l'identificatore originale.</span><span class="sxs-lookup"><span data-stu-id="d7a85-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="d7a85-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d7a85-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="d7a85-114">Nei cmdlet `Encode-Sqlname` e `Decode-Sqlname` è possibile codificare o decodificare solo i caratteri consentiti negli identificatori delimitati di SQL Server, ma non sono supportati nei percorsi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7a85-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="d7a85-115">Caratteri codificati da **Encode-SqlName** e decodificati da **Decode-SqlName**:</span><span class="sxs-lookup"><span data-stu-id="d7a85-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="d7a85-116">**Carattere**</span><span class="sxs-lookup"><span data-stu-id="d7a85-116">**Character**</span></span>|\ |/|<span data-ttu-id="d7a85-117">:</span><span class="sxs-lookup"><span data-stu-id="d7a85-117">:</span></span>|%|\<|>|*|<span data-ttu-id="d7a85-118">?</span><span class="sxs-lookup"><span data-stu-id="d7a85-118">?</span></span>|<span data-ttu-id="d7a85-119">[</span><span class="sxs-lookup"><span data-stu-id="d7a85-119">[</span></span>|<span data-ttu-id="d7a85-120">]</span><span class="sxs-lookup"><span data-stu-id="d7a85-120">]</span></span>|<span data-ttu-id="d7a85-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="d7a85-121">&#124;</span></span>|  
|<span data-ttu-id="d7a85-122">**Codifica esadecimale**</span><span class="sxs-lookup"><span data-stu-id="d7a85-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="d7a85-123">%5C</span><span class="sxs-lookup"><span data-stu-id="d7a85-123">%5C</span></span>|<span data-ttu-id="d7a85-124">%2F</span><span class="sxs-lookup"><span data-stu-id="d7a85-124">%2F</span></span>|<span data-ttu-id="d7a85-125">%3A</span><span class="sxs-lookup"><span data-stu-id="d7a85-125">%3A</span></span>|<span data-ttu-id="d7a85-126">%25</span><span class="sxs-lookup"><span data-stu-id="d7a85-126">%25</span></span>|<span data-ttu-id="d7a85-127">%3C</span><span class="sxs-lookup"><span data-stu-id="d7a85-127">%3C</span></span>|<span data-ttu-id="d7a85-128">%3E</span><span class="sxs-lookup"><span data-stu-id="d7a85-128">%3E</span></span>|<span data-ttu-id="d7a85-129">%2A</span><span class="sxs-lookup"><span data-stu-id="d7a85-129">%2A</span></span>|<span data-ttu-id="d7a85-130">%3F</span><span class="sxs-lookup"><span data-stu-id="d7a85-130">%3F</span></span>|<span data-ttu-id="d7a85-131">%5B</span><span class="sxs-lookup"><span data-stu-id="d7a85-131">%5B</span></span>|<span data-ttu-id="d7a85-132">%5D</span><span class="sxs-lookup"><span data-stu-id="d7a85-132">%5D</span></span>|<span data-ttu-id="d7a85-133">%7C</span><span class="sxs-lookup"><span data-stu-id="d7a85-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a><span data-ttu-id="d7a85-134">Codifica di un identificatore</span><span class="sxs-lookup"><span data-stu-id="d7a85-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="d7a85-135">**Per codificare un identificatore di SQL Server in un percorso di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d7a85-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="d7a85-136">Utilizzare uno dei due metodi per codificare un identificatore di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d7a85-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="d7a85-137">Specificare il codice esadecimale per il carattere non supportato utilizzando la sintassi% XX, dove XX rappresenta il codice esadecimale.</span><span class="sxs-lookup"><span data-stu-id="d7a85-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="d7a85-138">Passare l'identificatore come stringa tra virgolette al cmdlet `Encode-Sqlname`</span><span class="sxs-lookup"><span data-stu-id="d7a85-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="d7a85-139">Esempi (codifica)</span><span class="sxs-lookup"><span data-stu-id="d7a85-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="d7a85-140">In questo esempio viene specificata la versione codificata del carattere ":" (% 3A):</span><span class="sxs-lookup"><span data-stu-id="d7a85-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="d7a85-141">In alternativa, è possibile usare **Encode-SqlName** per compilare un nome supportato da Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7a85-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a> <span data-ttu-id="d7a85-142">Decodifica di un identificatore</span><span class="sxs-lookup"><span data-stu-id="d7a85-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="d7a85-143">**Per decodificare un identificatore di SQL Server da un percorso di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d7a85-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="d7a85-144">Utilizzare il cmdlet `Decode-Sqlname` per sostituire le codifiche esadecimali con i caratteri rappresentati dalla codifica.</span><span class="sxs-lookup"><span data-stu-id="d7a85-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="d7a85-145">Esempi (decodifica)</span><span class="sxs-lookup"><span data-stu-id="d7a85-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="d7a85-146">In questo esempio viene restituito "Table:Test":</span><span class="sxs-lookup"><span data-stu-id="d7a85-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7a85-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7a85-147">See Also</span></span>  
 <span data-ttu-id="d7a85-148">[Identificatori di SQL Server in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="d7a85-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="d7a85-149">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d7a85-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="d7a85-150">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7a85-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
