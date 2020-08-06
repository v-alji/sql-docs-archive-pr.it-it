---
title: SQLSetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637256"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="66a5d-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="66a5d-102">SQLSetDescField</span></span>
  <span data-ttu-id="66a5d-103">SQLSetDescField può essere utilizzato per impostare i campi di descrizione per i parametri con valori di tabella e le colonne dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="66a5d-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="66a5d-104">Per informazioni sui campi disponibili, vedere [campi di descrizione dei parametri con valori di tabella](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) e [campi di descrizione per le colonne costitutive dei parametri con valori di tabella](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66a5d-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="66a5d-105">Remarks</span></span>  
 <span data-ttu-id="66a5d-106">Le colonne dei parametri con valori di tabella sono disponibili solo quando il campo di intestazione di descrizione SQL_SOPT_SS_PARAM_FOCUS è impostato sul numero ordinale di un record in cui SQL_DESC_TYPE è impostato su SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="66a5d-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="66a5d-107">Per ulteriori informazioni su SQL_SOPT_SS_PARAM_FOCUS, vedere [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="66a5d-108">Se viene effettuato un tentativo di impostare SQL_SOPT_SS_PARAM_FOCUS sull'ordinale di un parametro che non è un parametro con valori di tabella, SQLSetStmtAttr restituisce SQL_ERROR e viene creato un record di diagnostica con SQLSTATE = HY024 e il messaggio "valore attributo non valido".</span><span class="sxs-lookup"><span data-stu-id="66a5d-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="66a5d-109">SQL_SOPT_SS_PARAM_FOCUS non viene modificato al momento della restituzione di SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="66a5d-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="66a5d-110">L'impostazione di SQL_SOPT_SS_PARAM_FOCUS su 0 ripristina l'accesso ai record del descrittore per i parametri.</span><span class="sxs-lookup"><span data-stu-id="66a5d-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="66a5d-111">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="66a5d-112">Supporto di SQLSetDescField per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="66a5d-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="66a5d-113">Le caratteristiche di data/ora sono state migliorate in ODBC.</span><span class="sxs-lookup"><span data-stu-id="66a5d-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="66a5d-114">Per informazioni sul campo di descrizione fornito per i nuovi tipi di data/ora, vedere [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="66a5d-115">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="66a5d-116">Supporto di SQLSetDescField per tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="66a5d-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="66a5d-117">SQLSetDescField supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="66a5d-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="66a5d-118">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="66a5d-119">Supporto di SQLSetDescField per colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="66a5d-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="66a5d-120">SQLSetDecField può essere usato per impostare SQL_SOPT_SS_NAME_SCOPE nel descrittore del parametro dell'applicazione (APD) sui valori SQL_SS_NAME_SCOPE_EXTENDED e SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="66a5d-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="66a5d-121">Per ulteriori informazioni, vedere [supporto di colonne di tipo sparse &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="66a5d-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a5d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66a5d-122">See Also</span></span>  
 <span data-ttu-id="66a5d-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="66a5d-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="66a5d-124">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="66a5d-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
