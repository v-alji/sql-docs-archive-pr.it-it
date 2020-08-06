---
title: Tipo SQL ODBC per parametri con valori di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636067"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="417f5-102">Tipo SQL ODBC per parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="417f5-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="417f5-103">Il supporto per i parametri con valori di tabella viene fornito da un nuovo tipo ODBC SQL, SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="417f5-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="417f5-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="417f5-104">Remarks</span></span>  
 <span data-ttu-id="417f5-105">SQL_SS_TABLE non può essere convertito in un altro tipo di dati ODBC o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="417f5-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="417f5-106">Se SQL_SS_TABLE viene usato come tipo di dati C nel parametro *ValueType* di SQLBindParameter o viene effettuato un tentativo di impostare SQL_DESC_TYPE in un record del descrittore del parametro dell'applicazione (APD) per SQL_SS_TABLE, SQL_ERROR viene restituito e viene generato un record di diagnostica con SQLSTATE = HY003, "tipo di buffer dell'applicazione non valido".</span><span class="sxs-lookup"><span data-stu-id="417f5-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="417f5-107">Se SQL_DESC_TYPE è impostato su SQL_SS_TABLE in un record IPD e il record del descrittore del parametro dell'applicazione corrispondente non è SQL_C_DEFAULT, viene restituito SQL_ERROR e viene generato un record di diagnostica con SQLSTATE=HY003, "Tipo di buffer dall'applicazione non valido".</span><span class="sxs-lookup"><span data-stu-id="417f5-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="417f5-108">Questa situazione può verificarsi con *ParameterType* di un SQLSetDescField, SQLSetDescRec o SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="417f5-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="417f5-109">Se il parametro *targetType* è SQL_SS_TABLE quando si chiama SQLGetData, viene restituito SQL_ERROR e viene generato un record di diagnostica con SQLSTATE = HY003, "tipo di buffer dell'applicazione non valido".</span><span class="sxs-lookup"><span data-stu-id="417f5-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="417f5-110">Non è possibile associare una colonna di parametri con valori di tabella come tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="417f5-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="417f5-111">Se `SQLBindParameter` viene chiamato con *ParameterType* impostato su SQL_SS_TABLE, viene restituito SQL_ERROR e viene generato un record di diagnostica con SQLSTATE = HY004, "tipo di dati SQL non valido".</span><span class="sxs-lookup"><span data-stu-id="417f5-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="417f5-112">Questa situazione può verificarsi anche con SQLSetDescField e SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="417f5-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="417f5-113">I valori della colonna di parametri con valori di tabella presentano le stesse opzioni di conversione dei dati dei parametri e delle colonne dei risultati.</span><span class="sxs-lookup"><span data-stu-id="417f5-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="417f5-114">Un parametro con valori di tabella può essere solo un parametro di input in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="417f5-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="417f5-115">Se viene effettuato un tentativo di impostare SQL_DESC_PARAMETER_TYPE su un valore diverso da SQL_PARAM_INPUT tramite SQLBindParameter o SQLSetDescField, viene restituito SQL_ERROR e viene aggiunto un record di diagnostica all'istruzione con SQLSTATE = HY105 e il messaggio "tipo di parametro non valido".</span><span class="sxs-lookup"><span data-stu-id="417f5-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="417f5-116">Le colonne di parametri con valori di tabella non possono utilizzare SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*perché i valori predefiniti per riga non sono supportati con i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="417f5-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="417f5-117">È invece possibile impostare l'attributo della colonna SQL_CA_SS_COL_HAS_DEFAULT_VALUE su 1.</span><span class="sxs-lookup"><span data-stu-id="417f5-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="417f5-118">Ciò significa che per tutte le righe della colonna saranno disponibili valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="417f5-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="417f5-119">Se *StrLen_or_IndPtr* è impostato su SQL_DEFAULT_PARAM, SQLExecute o SQLExecDirect restituirà SQL_ERROR e verrà aggiunto un record di diagnostica all'istruzione con SQLSTATE = HY090 e il messaggio "lunghezza di stringa o di buffer non valida".</span><span class="sxs-lookup"><span data-stu-id="417f5-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="417f5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="417f5-120">See Also</span></span>  
 [<span data-ttu-id="417f5-121">Parametri con valori di tabella &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="417f5-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
