---
title: bcp_done | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623238"
---
# <a name="bcp_done"></a><span data-ttu-id="8fe97-102">bcp_done</span><span class="sxs-lookup"><span data-stu-id="8fe97-102">bcp_done</span></span>
  <span data-ttu-id="8fe97-103">Termina una copia bulk dalle variabili di programma a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguite con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="8fe97-103">Ends a bulk copy from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performed with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fe97-104">Syntax</span></span>  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8fe97-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8fe97-105">Arguments</span></span>  
 <span data-ttu-id="8fe97-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="8fe97-106">*hdbc*</span></span>  
 <span data-ttu-id="8fe97-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="8fe97-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8fe97-108">Restituisce</span><span class="sxs-lookup"><span data-stu-id="8fe97-108">Returns</span></span>  
 <span data-ttu-id="8fe97-109">Il numero di righe salvate in modo permanente dopo l'ultima chiamata a [bcp_batch](bcp-batch.md) o-1 in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="8fe97-109">The number of rows permanently saved after the last call to [bcp_batch](bcp-batch.md) or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fe97-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8fe97-110">Remarks</span></span>  
 <span data-ttu-id="8fe97-111">Chiamare **bcp_done** dopo l'ultima chiamata a [bcp_sendrow](bcp-sendrow.md) o [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="8fe97-111">Call **bcp_done** after the last call to [bcp_sendrow](bcp-sendrow.md) or [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="8fe97-112">La mancata chiamata di **bcp_done** dopo la copia di tutti i dati genera errori.</span><span class="sxs-lookup"><span data-stu-id="8fe97-112">Failure to call **bcp_done** after copying all data results in errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe97-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe97-113">See Also</span></span>  
 [<span data-ttu-id="8fe97-114">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="8fe97-114">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
