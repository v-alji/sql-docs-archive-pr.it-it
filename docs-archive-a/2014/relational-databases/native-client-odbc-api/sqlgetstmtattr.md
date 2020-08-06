---
title: SQLGetStmtAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629381"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="0e0ad-102">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="0e0ad-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="0e0ad-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client estende SQLGetStmtAttr per esporre gli attributi di istruzione specifici del driver.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="0e0ad-104">[SQLSetStmtAttr](sqlsetstmtattr.md) elenca gli attributi di istruzione che sono sia di lettura che di scrittura.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="0e0ad-105">In questo argomento vengono elencati gli attributi dell'istruzione di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="0e0ad-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="0e0ad-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="0e0ad-107">L'attributo SQL_SOPT_SS_CURRENT_COMMAND espone il comando corrente di un batch di comandi.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="0e0ad-108">Il valore restituito è un numero intero che specifica il percorso del comando nel batch.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="0e0ad-109">Il valore *ValuePtr* è di tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="0e0ad-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="0e0ad-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="0e0ad-111">L'attributo SQL_SOPT_SS_NOCOUNT_STATUS indica l'impostazione corrente dell'opzione NOCOUNT, che controlla se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] segnala il numero di righe interessate da un'istruzione quando viene chiamato [SQLRowCount](sqlrowcount.md) .</span><span class="sxs-lookup"><span data-stu-id="0e0ad-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="0e0ad-112">Il valore *ValuePtr* è di tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="0e0ad-113">Valore</span><span class="sxs-lookup"><span data-stu-id="0e0ad-113">Value</span></span>|<span data-ttu-id="0e0ad-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e0ad-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e0ad-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="0e0ad-115">SQL_NC_OFF</span></span>|<span data-ttu-id="0e0ad-116">NOCOUNT è OFF.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="0e0ad-117">SQLRowCount restituisce il numero di righe interessate.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="0e0ad-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="0e0ad-118">SQL_NC_ON</span></span>|<span data-ttu-id="0e0ad-119">NOCOUNT è ON.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-119">NOCOUNT is ON.</span></span> <span data-ttu-id="0e0ad-120">Il numero di righe interessate non viene restituito da SQLRowCount e il valore restituito è 0.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="0e0ad-121">Se SQLRowCount restituisce 0, l'applicazione deve testare SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="0e0ad-122">Se viene restituito SQL_NC_ON, il valore 0 di SQLRowCount indica solo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non ha restituito un conteggio di righe.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="0e0ad-123">Se viene restituito SQL_NC_OFF, NOCOUNT è disattivato e il valore 0 di SQLRowCount indica che l'istruzione non ha influito sulle righe.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="0e0ad-124">Quando SQL_SOPT_SS_NOCOUNT_STATUS è SQL_NC_OFF, le applicazioni non dovrebbero visualizzare il valore di SQLRowCount.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="0e0ad-125">Le stored procedure o i batch di grandi dimensioni possono contenere più istruzioni SET NOCOUNT, pertanto non è possibile presupporre che SQL_SOPT_SS_NOCOUNT_STATUS rimanga costante.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="0e0ad-126">Questa opzione deve essere testata ogni volta che SQLRowCount restituisce 0.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="0e0ad-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="0e0ad-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="0e0ad-128">L'attributo SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT restituisce il testo del messaggio per la richiesta di notifica di query.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="0e0ad-129">SQLGetStmtAttr e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="0e0ad-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="0e0ad-130">È possibile chiamare SQLGetStmtAttr per ottenere il valore di SQL_SOPT_SS_PARAM_FOCUS nel descrittore del parametro dell'applicazione (APD) quando si utilizzano parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="0e0ad-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="0e0ad-131">Per ulteriori informazioni su SQL_SOPT_SS_PARAM_FOCUS, vedere [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="0e0ad-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="0e0ad-132">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0e0ad-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e0ad-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e0ad-133">See Also</span></span>  
 <span data-ttu-id="0e0ad-134">[SQLSetStmtAttr (funzione)](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="0e0ad-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="0e0ad-135">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="0e0ad-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
