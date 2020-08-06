---
title: bcp_columns | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714327"
---
# <a name="bcp_columns"></a><span data-ttu-id="ea84d-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="ea84d-102">bcp_columns</span></span>
  <span data-ttu-id="ea84d-103">Imposta il numero totale di colonne individuate nel file utente da utilizzare con una copia bulk all'interno o all'esterno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea84d-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea84d-104">è possibile utilizzare [bcp_setbulkmode](bcp-setbulkmode.md) al posto di bcp_columns e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="ea84d-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea84d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea84d-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea84d-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ea84d-106">Arguments</span></span>  
 <span data-ttu-id="ea84d-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="ea84d-107">*hdbc*</span></span>  
 <span data-ttu-id="ea84d-108">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="ea84d-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="ea84d-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="ea84d-109">*nColumns*</span></span>  
 <span data-ttu-id="ea84d-110">Numero totale di colonne nel file utente.</span><span class="sxs-lookup"><span data-stu-id="ea84d-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="ea84d-111">Anche se si prepara la copia bulk di dati dal file utente a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella e non si intende copiare tutte le colonne nel file utente, è comunque necessario impostare *nColumns sul* sul numero totale di colonne del file utente.</span><span class="sxs-lookup"><span data-stu-id="ea84d-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ea84d-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="ea84d-112">Returns</span></span>  
 <span data-ttu-id="ea84d-113">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="ea84d-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea84d-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea84d-114">Remarks</span></span>  
 <span data-ttu-id="ea84d-115">Questa funzione può essere chiamata solo dopo che [bcp_init](bcp-init.md) è stato chiamato con un nome file valido.</span><span class="sxs-lookup"><span data-stu-id="ea84d-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="ea84d-116">È consigliabile chiamare questa funzione solo se si intende utilizzare un formato di file utente diverso da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="ea84d-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="ea84d-117">Per ulteriori informazioni su una descrizione del formato di file utente predefinito, vedere **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="ea84d-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="ea84d-118">Dopo aver chiamato `bcp_columns` , è necessario chiamare [bcp_colfmt](bcp-colfmt.md)per ogni colonna del file utente per definire completamente un formato di file personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ea84d-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea84d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea84d-119">See Also</span></span>  
 [<span data-ttu-id="ea84d-120">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="ea84d-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
