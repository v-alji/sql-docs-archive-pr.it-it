---
title: Dettagli di implementazione dell'API ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQL Server Native Client ODBC driver, SQL Server-specific behaviors
- ODBC, SQL Server-specific behaviors
- functions [ODBC]
ms.assetid: dca92489-f179-4b1f-997c-adcc46aa17a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 1af47924090e7cb1df8ed7907ba0f793b9df2420
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724608"
---
# <a name="odbc-api-implementation-details"></a><span data-ttu-id="29b64-102">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="29b64-102">ODBC API Implementation Details</span></span>
  <span data-ttu-id="29b64-103">In questa sezione vengono illustrate le funzioni ODBC che presentano comportamenti specifici di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se utilizzate con il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="29b64-103">This section documents the ODBC functions that exhibit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific behaviors when used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="29b64-104">In questa sede non vengono trattate tutte le funzioni ODBC.</span><span class="sxs-lookup"><span data-stu-id="29b64-104">Not all ODBC functions are documented here.</span></span> <span data-ttu-id="29b64-105">Nei singoli argomenti vengono descritti solo problemi specifici di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per una funzione ODBC.</span><span class="sxs-lookup"><span data-stu-id="29b64-105">The individual topics only discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific issues for an ODBC function.</span></span> <span data-ttu-id="29b64-106">Tali argomenti non costituiscono un riferimento esaustivo per le funzioni ODBC.</span><span class="sxs-lookup"><span data-stu-id="29b64-106">They are not a complete reference for the ODBC functions.</span></span>  
  
 <span data-ttu-id="29b64-107">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client è conforme alla specifica ODBC 3.51 e, se si utilizza Windows 7 SDK, alla specifica ODBC 3.8.</span><span class="sxs-lookup"><span data-stu-id="29b64-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the ODBC 3.51 specification and, if you are using the Windows 7 SDK, with the ODBC 3.8 specification.</span></span> <span data-ttu-id="29b64-108">Per un riferimento ODBC completo, vedere la documentazione online [di ODBC Programmer ' s Reference](https://go.microsoft.com/fwlink/?LinkId=45250) .</span><span class="sxs-lookup"><span data-stu-id="29b64-108">For a comprehensive ODBC reference, view the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29b64-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="29b64-109">In This Section</span></span>  
  
-   [<span data-ttu-id="29b64-110">SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="29b64-110">SQLBindCol</span></span>](sqlbindcol.md)  
  
-   [<span data-ttu-id="29b64-111">SQLBindParameter</span><span class="sxs-lookup"><span data-stu-id="29b64-111">SQLBindParameter</span></span>](sqlbindparameter.md)  
  
-   [<span data-ttu-id="29b64-112">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="29b64-112">SQLBrowseConnect</span></span>](sqlbrowseconnect.md)  
  
-   [<span data-ttu-id="29b64-113">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="29b64-113">SQLCancel</span></span>](sqlcancel.md)  
  
-   [<span data-ttu-id="29b64-114">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="29b64-114">SQLCloseCursor</span></span>](sqlclosecursor.md)  
  
-   [<span data-ttu-id="29b64-115">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="29b64-115">SQLColAttribute</span></span>](sqlcolattribute.md)  
  
-   [<span data-ttu-id="29b64-116">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="29b64-116">SQLColumnPrivileges</span></span>](sqlcolumnprivileges.md)  
  
-   [<span data-ttu-id="29b64-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="29b64-117">SQLColumns</span></span>](sqlcolumns.md)  
  
-   [<span data-ttu-id="29b64-118">SQLConfigDataSource</span><span class="sxs-lookup"><span data-stu-id="29b64-118">SQLConfigDataSource</span></span>](sqlconfigdatasource.md)  
  
-   [<span data-ttu-id="29b64-119">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="29b64-119">SQLConnect</span></span>](sqlconnect.md)  
  
-   [<span data-ttu-id="29b64-120">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="29b64-120">SQLDescribeCol</span></span>](sqldescribecol.md)  
  
-   [<span data-ttu-id="29b64-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="29b64-121">SQLDescribeParam</span></span>](sqldescribeparam.md)  
  
-   [<span data-ttu-id="29b64-122">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="29b64-122">SQLDriverConnect</span></span>](sqldriverconnect.md)  
  
-   [<span data-ttu-id="29b64-123">SQLDrivers</span><span class="sxs-lookup"><span data-stu-id="29b64-123">SQLDrivers</span></span>](sqldrivers.md)  
  
-   [<span data-ttu-id="29b64-124">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="29b64-124">SQLEndTran</span></span>](sqlendtran.md)  
  
-   [<span data-ttu-id="29b64-125">SQLExecDirect</span><span class="sxs-lookup"><span data-stu-id="29b64-125">SQLExecDirect</span></span>](sqlexecdirect.md)  
  
-   [<span data-ttu-id="29b64-126">SQLExecute</span><span class="sxs-lookup"><span data-stu-id="29b64-126">SQLExecute</span></span>](sqlexecute.md)  
  
-   [<span data-ttu-id="29b64-127">SQLFetch</span><span class="sxs-lookup"><span data-stu-id="29b64-127">SQLFetch</span></span>](sqlfetch.md)  
  
-   [<span data-ttu-id="29b64-128">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="29b64-128">SQLFetchScroll</span></span>](sqlfetchscroll.md)  
  
-   [<span data-ttu-id="29b64-129">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="29b64-129">SQLForeignKeys</span></span>](sqlforeignkeys.md)  
  
-   [<span data-ttu-id="29b64-130">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="29b64-130">SQLFreeHandle</span></span>](sqlfreehandle.md)  
  
-   [<span data-ttu-id="29b64-131">SQLFreeStmt</span><span class="sxs-lookup"><span data-stu-id="29b64-131">SQLFreeStmt</span></span>](sqlfreestmt.md)  
  
-   [<span data-ttu-id="29b64-132">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="29b64-132">SQLGetConnectAttr</span></span>](sqlgetconnectattr.md)  
  
-   [<span data-ttu-id="29b64-133">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="29b64-133">SQLGetCursorName</span></span>](sqlgetcursorname.md)  
  
-   [<span data-ttu-id="29b64-134">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="29b64-134">SQLGetData</span></span>](sqlgetdata.md)  
  
-   [<span data-ttu-id="29b64-135">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="29b64-135">SQLGetDescField</span></span>](sqlgetdescfield.md)  
  
-   [<span data-ttu-id="29b64-136">SQLGetDescRec</span><span class="sxs-lookup"><span data-stu-id="29b64-136">SQLGetDescRec</span></span>](sqlgetdescrec.md)  
  
-   [<span data-ttu-id="29b64-137">SQLGetDiagField</span><span class="sxs-lookup"><span data-stu-id="29b64-137">SQLGetDiagField</span></span>](sqlgetdiagfield.md)  
  
-   [<span data-ttu-id="29b64-138">SQLGetFunctions</span><span class="sxs-lookup"><span data-stu-id="29b64-138">SQLGetFunctions</span></span>](sqlgetfunctions.md)  
  
-   [<span data-ttu-id="29b64-139">SQLGetInfo</span><span class="sxs-lookup"><span data-stu-id="29b64-139">SQLGetInfo</span></span>](sqlgetinfo.md)  
  
-   [<span data-ttu-id="29b64-140">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="29b64-140">SQLGetStmtAttr</span></span>](sqlgetstmtattr.md)  
  
-   [<span data-ttu-id="29b64-141">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="29b64-141">SQLGetTypeInfo</span></span>](sqlgettypeinfo.md)  
  
-   [<span data-ttu-id="29b64-142">SQLMoreResults</span><span class="sxs-lookup"><span data-stu-id="29b64-142">SQLMoreResults</span></span>](sqlmoreresults.md)  
  
-   [<span data-ttu-id="29b64-143">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="29b64-143">SQLNativeSql</span></span>](sqlnativesql.md)  
  
-   [<span data-ttu-id="29b64-144">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="29b64-144">SQLNumParams</span></span>](sqlnumparams.md)  
  
-   [<span data-ttu-id="29b64-145">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="29b64-145">SQLNumResultCols</span></span>](sqlnumresultcols.md)  
  
-   [<span data-ttu-id="29b64-146">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="29b64-146">SQLParamData</span></span>](sqlparamdata.md)  
  
-   [<span data-ttu-id="29b64-147">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="29b64-147">SQLPrimaryKeys</span></span>](sqlprimarykeys.md)  
  
-   [<span data-ttu-id="29b64-148">SQLProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="29b64-148">SQLProcedureColumns</span></span>](sqlprocedurecolumns.md)  
  
-   [<span data-ttu-id="29b64-149">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="29b64-149">SQLProcedures</span></span>](sqlprocedures.md)  
  
-   [<span data-ttu-id="29b64-150">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="29b64-150">SQLPutData</span></span>](sqlputdata.md)  
  
-   [<span data-ttu-id="29b64-151">SQLRowCount</span><span class="sxs-lookup"><span data-stu-id="29b64-151">SQLRowCount</span></span>](sqlrowcount.md)  
  
-   [<span data-ttu-id="29b64-152">SQLSetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="29b64-152">SQLSetConnectAttr</span></span>](sqlsetconnectattr.md)  
  
-   [<span data-ttu-id="29b64-153">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="29b64-153">SQLSetDescField</span></span>](sqlsetdescfield.md)  
  
-   [<span data-ttu-id="29b64-154">SQLSetDescRec</span><span class="sxs-lookup"><span data-stu-id="29b64-154">SQLSetDescRec</span></span>](sqlsetdescrec.md)  
  
-   [<span data-ttu-id="29b64-155">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="29b64-155">SQLSetEnvAttr</span></span>](sqlsetenvattr.md)  
  
-   [<span data-ttu-id="29b64-156">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="29b64-156">SQLSetStmtAttr</span></span>](sqlsetstmtattr.md)  
  
-   [<span data-ttu-id="29b64-157">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="29b64-157">SQLSpecialColumns</span></span>](sqlspecialcolumns.md)  
  
-   [<span data-ttu-id="29b64-158">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="29b64-158">SQLStatistics</span></span>](../statistics/statistics.md)  
  
-   [<span data-ttu-id="29b64-159">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="29b64-159">SQLTablePrivileges</span></span>](sqltableprivileges.md)  
  
-   [<span data-ttu-id="29b64-160">SQLTables</span><span class="sxs-lookup"><span data-stu-id="29b64-160">SQLTables</span></span>](sqltables.md)  
  
## <a name="see-also"></a><span data-ttu-id="29b64-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b64-161">See Also</span></span>  
 <span data-ttu-id="29b64-162">[SQL Server Native Client &#40;riferimento&#41; ODBC](../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md) </span><span class="sxs-lookup"><span data-stu-id="29b64-162">[SQL Server Native Client &#40;ODBC&#41; Reference](../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md) </span></span>  
 [<span data-ttu-id="29b64-163">Compilazione di applicazioni con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="29b64-163">Building Applications with SQL Server Native Client</span></span>](../native-client/applications/building-applications-with-sql-server-native-client.md)  
  
  
