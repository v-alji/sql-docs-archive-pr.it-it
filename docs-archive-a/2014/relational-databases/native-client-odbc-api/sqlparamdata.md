---
title: SQLParamData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637273"
---
# <a name="sqlparamdata"></a><span data-ttu-id="08a3e-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="08a3e-102">SQLParamData</span></span>
  <span data-ttu-id="08a3e-103">Quando SQLParamData restituisce il *ValuePtrPtr* associato a un parametro con valori di tabella, l'applicazione deve chiamare SQLPutData con *StrLen_Or_Ind*.</span><span class="sxs-lookup"><span data-stu-id="08a3e-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="08a3e-104">Se *StrLen_Or_Ind* ha un valore maggiore di 0, significa che l'applicazione è pronta per la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raccolta di dati di parametro da parte di Native Client per la successiva riga di parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="08a3e-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="08a3e-105">Se *StrLen_Or_Ind* ha un valore pari a 0, significa che non sono presenti più righe di dati per il parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="08a3e-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="08a3e-106">Per ulteriori informazioni, vedere [associazione e trasferimento dati di parametri con valori di tabella e valori di colonna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="08a3e-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="08a3e-107">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="08a3e-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a3e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08a3e-108">See Also</span></span>  
 <span data-ttu-id="08a3e-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="08a3e-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="08a3e-110">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="08a3e-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
