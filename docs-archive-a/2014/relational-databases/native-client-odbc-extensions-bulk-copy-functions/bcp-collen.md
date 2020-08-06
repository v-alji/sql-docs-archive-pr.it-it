---
title: bcp_collen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725688"
---
# <a name="bcp_collen"></a><span data-ttu-id="d350e-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="d350e-102">bcp_collen</span></span>
  <span data-ttu-id="d350e-103">Imposta la lunghezza dei dati nella variabile di programma per la copia bulk corrente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d350e-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d350e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d350e-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d350e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d350e-105">Arguments</span></span>  
 <span data-ttu-id="d350e-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="d350e-106">*hdbc*</span></span>  
 <span data-ttu-id="d350e-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="d350e-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="d350e-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="d350e-108">*cbData*</span></span>  
 <span data-ttu-id="d350e-109">Lunghezza dei dati nella variabile di programma esclusa la lunghezza dei caratteri di terminazione o degli indicatori di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d350e-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="d350e-110">L'impostazione di *cbData* su SQL_NULL_DATA indica che tutte le righe copiate nel server contengono un valore null per la colonna.</span><span class="sxs-lookup"><span data-stu-id="d350e-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="d350e-111">L'impostazione di cbData su SQL_VARLEN_DATA indica che verrà utilizzato un carattere di terminazione della stringa o un altro metodo per determinare la lunghezza dei dati copiati.</span><span class="sxs-lookup"><span data-stu-id="d350e-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="d350e-112">Se sono presenti sia un indicatore di lunghezza che un carattere di terminazione, il sistema utilizzerà il metodo che comporta la copia del minor numero di dati.</span><span class="sxs-lookup"><span data-stu-id="d350e-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="d350e-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="d350e-113">*idxServerCol*</span></span>  
 <span data-ttu-id="d350e-114">Posizione ordinale della colonna nella tabella in cui vengono copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="d350e-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="d350e-115">La prima colonna è 1.</span><span class="sxs-lookup"><span data-stu-id="d350e-115">The first column is 1.</span></span> <span data-ttu-id="d350e-116">La posizione ordinale di una colonna viene segnalata da [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="d350e-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d350e-117">Restituisce</span><span class="sxs-lookup"><span data-stu-id="d350e-117">Returns</span></span>  
 <span data-ttu-id="d350e-118">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="d350e-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d350e-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d350e-119">Remarks</span></span>  
 <span data-ttu-id="d350e-120">La funzione **bcp_collen** consente di modificare la lunghezza dei dati nella variabile di programma per una determinata colonna durante la copia dei dati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="d350e-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="d350e-121">Inizialmente, la lunghezza dei dati viene determinata quando viene chiamato [bcp_bind](bcp-bind.md) .</span><span class="sxs-lookup"><span data-stu-id="d350e-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="d350e-122">Se la lunghezza dei dati viene modificata tra le chiamate a **bcp_sendrow** e non viene utilizzato alcun prefisso di lunghezza o carattere di terminazione, è possibile chiamare **bcp_collen** per reimpostare la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="d350e-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="d350e-123">La chiamata successiva a **bcp_sendrow** utilizza la lunghezza impostata dalla chiamata al **bcp_collen**.</span><span class="sxs-lookup"><span data-stu-id="d350e-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="d350e-124">È necessario chiamare **bcp_collen** una volta per ogni colonna della tabella di cui si desidera modificare la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="d350e-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d350e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d350e-125">See Also</span></span>  
 [<span data-ttu-id="d350e-126">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="d350e-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
