---
title: bcp_batch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628643"
---
# <a name="bcp_batch"></a><span data-ttu-id="19545-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="19545-102">bcp_batch</span></span>
  <span data-ttu-id="19545-103">Esegue il commit di tutte le righe precedentemente copiate in massa dalle variabili di programma e inviate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="19545-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19545-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19545-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="19545-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="19545-105">Arguments</span></span>  
 <span data-ttu-id="19545-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="19545-106">*hdbc*</span></span>  
 <span data-ttu-id="19545-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="19545-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="19545-108">Restituisce</span><span class="sxs-lookup"><span data-stu-id="19545-108">Returns</span></span>  
 <span data-ttu-id="19545-109">Numero di righe salvate dopo l'ultima chiamata a **bcp_batch**, oppure-1 in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="19545-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19545-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="19545-110">Remarks</span></span>  
 <span data-ttu-id="19545-111">I batch della copia bulk definiscono le transazioni.</span><span class="sxs-lookup"><span data-stu-id="19545-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="19545-112">Quando un'applicazione utilizza [bcp_bind](bcp-bind.md) e **bcp_sendrow** per eseguire la copia bulk delle righe dalle variabili di programma alle tabelle SQL Server, viene eseguito il commit delle righe solo quando il programma chiama **bcp_batch** o [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="19545-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="19545-113">È possibile chiamare **bcp_batch** una volta ogni *n* righe o quando si verifica una pausa nei dati in ingresso, come in un'applicazione di telemetria.</span><span class="sxs-lookup"><span data-stu-id="19545-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="19545-114">Se un'applicazione non chiama **bcp_batch** viene eseguito il commit delle righe di cui è stata eseguita la copia bulk solo quando viene chiamato **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="19545-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19545-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19545-115">See Also</span></span>  
 [<span data-ttu-id="19545-116">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="19545-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
