---
title: Supporto UTF-16 in SQL Server Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: f2520424-8ef4-409f-8147-d83da5076e96
author: rothja
ms.author: jroth
ms.openlocfilehash: af8581071400db888fb508b88f8e8ae93bc71f70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635523"
---
# <a name="utf-16-support-in-sql-server-native-client-110"></a><span data-ttu-id="3f4bd-102">Supporto per UTF-16 in SQL Server Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="3f4bd-102">UTF-16 Support in SQL Server Native Client 11.0</span></span>
  <span data-ttu-id="3f4bd-103">A partire da [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , se si fornisce un buffer a lunghezza fissa quando si associa un risultato della colonna o un parametro di output e se il `wchar` carattere scritto nel buffer prima del carattere di terminazione è un punto di codice surrogato alto di una coppia di surrogati e se il `wchar` carattere successivo è un punto di codice surrogato basso, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client non aggiungerà il punto di codice surrogato alto al buffer</span><span class="sxs-lookup"><span data-stu-id="3f4bd-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], if you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4bd-104">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f4bd-104">See Also</span></span>  
 [<span data-ttu-id="3f4bd-105">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="3f4bd-105">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
