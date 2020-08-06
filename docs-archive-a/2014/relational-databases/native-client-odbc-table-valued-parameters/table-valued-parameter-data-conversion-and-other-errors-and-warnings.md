---
title: Conversione di dati dei parametri con valori di tabella e altri errori e avvisi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624101"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="a0183-102">Conversione di dati dei parametri con valori di tabella e altri errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="a0183-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="a0183-103">I valori delle colonne dei parametri con valori di tabella possono essere convertiti tra tipi di dati client e server in modo analogo agli altri valori di colonna e di parametro.</span><span class="sxs-lookup"><span data-stu-id="a0183-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="a0183-104">Poiché un parametro con valori di tabella può contenere più colonne e più righe, è importante poter identificare il valore effettivo in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="a0183-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="a0183-105">Quando viene rilevato un errore o un avviso in una colonna dei parametri con valori di tabella, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client genera un record di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a0183-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="a0183-106">Il messaggio di errore conterrà il numero del parametro con valori di tabella, oltre al numero ordinale di colonna e al numero di riga.</span><span class="sxs-lookup"><span data-stu-id="a0183-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="a0183-107">Un'applicazione può utilizzare anche i campi di diagnostica SQL_DIAG_SS_TABLE_COLUMN_NUMBER e SQL_DIAG_SS_TABLE_ROW_NUMBER all'interno dei record di diagnostica per determinare i valori che vengono associati agli errori e agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a0183-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="a0183-108">Questi campi di diagnostica sono disponibili in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a0183-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="a0183-109">L'identificativo di errore SQLSTATE e il messaggio dei record di diagnostica saranno conformi al comportamento esistente di ODBC in tutti gli altri aspetti,</span><span class="sxs-lookup"><span data-stu-id="a0183-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="a0183-110">Ovvero, ad eccezione delle informazioni di identificazione di parametri, righe e colonne, i messaggi di errore hanno gli stessi valori per i parametri con valori di tabella come per i parametri non con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="a0183-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0183-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0183-111">See Also</span></span>  
 [<span data-ttu-id="a0183-112">Parametri con valori di tabella &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="a0183-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
