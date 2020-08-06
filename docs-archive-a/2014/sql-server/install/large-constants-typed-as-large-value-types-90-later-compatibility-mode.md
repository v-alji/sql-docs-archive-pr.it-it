---
title: Le costanti di grandi dimensioni sono tipizzate come tipi di valori di grandi dimensioni in modalità di compatibilità 90 o successive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624525"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="4c09c-102">In modalità di compatibilità 90 o successiva per le costanti di grandi dimensioni vengono utilizzati i tipi di dati per valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="4c09c-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="4c09c-103">È stata rilevata la presenza di costanti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4c09c-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="4c09c-104">Le costanti stringa di caratteri e le costanti binarie di dimensioni maggiori di 8.000 byte vengono considerate come tipi di dati di oggetti di grandi dimensioni in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c09c-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="4c09c-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versioni successive le costanti carattere, Unicode e binarie di grandi dimensioni vengono tipizzate come tipi di valori di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4c09c-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4c09c-106">Componente</span><span class="sxs-lookup"><span data-stu-id="4c09c-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4c09c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c09c-107">Description</span></span>  
 <span data-ttu-id="4c09c-108">Quando si utilizzano funzioni stringa, ad esempio CHARINDEX e PATINDEX, con costanti stringa di dimensioni maggiori di 8.000 byte, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] restituisce il numero di errore 8116 e [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versioni successive restituiscono il numero di errore 8152.</span><span class="sxs-lookup"><span data-stu-id="4c09c-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="4c09c-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] le funzioni stringa restituiscono l'errore 8116 quando vengono utilizzate con i tipi di dati `text`, `ntext` e `image`.</span><span class="sxs-lookup"><span data-stu-id="4c09c-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="4c09c-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versioni successive, le costanti di grandi dimensioni vengono considerate rispettivamente come tipi di dati `varchar(max)`, `nvarchar(max)` e `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="4c09c-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="4c09c-111">Questi tipi di dati sono compatibili con le funzioni stringa.</span><span class="sxs-lookup"><span data-stu-id="4c09c-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="4c09c-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versioni successive le funzioni stringhe, ad esempio CHARINDEX e PATINDEX, presuppongono che la stringa contenente la sequenza di caratteri da trovare sia minore di 8.000 byte.</span><span class="sxs-lookup"><span data-stu-id="4c09c-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="4c09c-113">Per questo motivo, per CHARINDEX e PATINDEX viene generato l'errore 8152.</span><span class="sxs-lookup"><span data-stu-id="4c09c-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c09c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c09c-114">See Also</span></span>  
 <span data-ttu-id="4c09c-115">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4c09c-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4c09c-116">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="4c09c-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
