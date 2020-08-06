---
title: bcp_sendrow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626752"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="739f8-102">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="739f8-102">bcp_sendrow</span></span>
  <span data-ttu-id="739f8-103">Invia una riga di dati dalle variabili di programma a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="739f8-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="739f8-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="739f8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="739f8-105">Arguments</span></span>  
 <span data-ttu-id="739f8-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="739f8-106">*hdbc*</span></span>  
 <span data-ttu-id="739f8-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="739f8-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="739f8-108">Restituisce</span><span class="sxs-lookup"><span data-stu-id="739f8-108">Returns</span></span>  
 <span data-ttu-id="739f8-109">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="739f8-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739f8-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="739f8-110">Remarks</span></span>  
 <span data-ttu-id="739f8-111">La funzione **bcp_sendrow** compila una riga dalle variabili di programma e la invia a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="739f8-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="739f8-112">Prima di chiamare **bcp_sendrow**, è necessario effettuare chiamate a [bcp_bind](bcp-bind.md) per specificare le variabili di programma contenenti i dati delle righe.</span><span class="sxs-lookup"><span data-stu-id="739f8-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="739f8-113">Se **bcp_bind** viene chiamato specificando un tipo di dati Long a lunghezza variabile, ad esempio un parametro *EDATATYPE* di SQLTEXT e un parametro *pData* non null, **bcp_sendrow** invierà il valore entiredata, proprio come per qualsiasi altro tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="739f8-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="739f8-114">Se, tuttavia, **bcp_bind** dispone di un parametro *pData* null, **bcp_sendrow** restituisce il controllo all'applicazione immediatamente dopo l'invio di tutte le colonne con i dati specificati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="739f8-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="739f8-115">L'applicazione può quindi chiamare ripetutamente [bcp_moretext](bcp-moretext.md) per inviare i dati Long a lunghezza variabile a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un blocco alla volta.</span><span class="sxs-lookup"><span data-stu-id="739f8-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="739f8-116">Per ulteriori informazioni, vedere [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="739f8-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="739f8-117">Quando **bcp_sendrow** viene utilizzata per eseguire la copia bulk delle righe dalle variabili di programma alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelle, viene eseguito il commit delle righe solo quando l'utente chiama [bcp_batch](bcp-batch.md) o [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="739f8-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="739f8-118">L'utente può scegliere di chiamare **bcp_batch** una volta ogni *n* righe o quando si verifica una pausa tra i periodi di dati in arrivo.</span><span class="sxs-lookup"><span data-stu-id="739f8-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="739f8-119">Se **bcp_batch** non viene mai chiamato, viene eseguito il commit delle righe quando viene chiamato **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="739f8-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="739f8-120">Per informazioni sulle modifiche di rilievo apportate alla copia bulk a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vedere [esecuzione di operazioni di copia bulk &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="739f8-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739f8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="739f8-121">See Also</span></span>  
 [<span data-ttu-id="739f8-122">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="739f8-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
