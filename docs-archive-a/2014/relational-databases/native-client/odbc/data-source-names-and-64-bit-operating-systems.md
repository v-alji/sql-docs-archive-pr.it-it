---
title: Nomi delle origini dati e sistemi operativi a 64 bit | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: c2f86810-2775-4ddd-8df7-e8373785a7fc
author: rothja
ms.author: jroth
ms.openlocfilehash: ae31584ca3c076919f688d1ef9bdef80706c6940
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626064"
---
# <a name="data-source-names-and-64-bit-operating-systems"></a><span data-ttu-id="fc038-102">Nomi di origine dati e sistemi operativi a 64 bit</span><span class="sxs-lookup"><span data-stu-id="fc038-102">Data Source Names and 64-Bit Operating Systems</span></span>
  <span data-ttu-id="fc038-103">Per compilare ed eseguire un'applicazione come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="fc038-103">To build and run an application as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc038-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fc038-104">Remarks</span></span>  
 <span data-ttu-id="fc038-105">Un sistema operativo Windows a 64 bit include due file odbcad32.exe:</span><span class="sxs-lookup"><span data-stu-id="fc038-105">A 64-bit Windows operating system has two odbcad32.exe files:</span></span>  
  
-   <span data-ttu-id="fc038-106">%SystemRoot%\system32\odbcad32.exe viene utilizzato per creare e gestire nomi di origine dati per applicazioni a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="fc038-106">%SystemRoot%\system32\odbcad32.exe is used to create and maintain data source names for 64-bit applications.</span></span>  
  
-   <span data-ttu-id="fc038-107">%SystemRoot%\SysWOW64\odbcad32.exe viene utilizzato per creare e gestire nomi di origine dati per applicazioni a 32 bit, incluse le applicazioni a 32 bit in esecuzione in sistemi operativi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="fc038-107">%SystemRoot%\SysWOW64\odbcad32.exe is used to create and maintain data source names for 32-bit applications, including 32-bit applications that run on 64-bit operating systems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc038-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc038-108">See Also</span></span>  
 [<span data-ttu-id="fc038-109">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="fc038-109">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
