---
title: Supporto per colonne di tipo sparse (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718072"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="05a19-102">Supporto per colonne di tipo sparse (ODBC)</span><span class="sxs-lookup"><span data-stu-id="05a19-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="05a19-103">In questo argomento viene descritto il supporto ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client per le colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="05a19-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="05a19-104">Per un esempio che illustra il supporto ODBC per le colonne di tipo sparse, vedere [chiamare SQLColumns in una tabella con colonne di tipo sparse](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="05a19-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="05a19-105">Per ulteriori informazioni sulle colonne di tipo sparse, vedere [supporto di colonne di tipo sparse in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="05a19-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="05a19-106">Metadati di istruzione</span><span class="sxs-lookup"><span data-stu-id="05a19-106">Statement Metadata</span></span>  
 <span data-ttu-id="05a19-107">Il campo di descrizione del parametro dell'applicazione (APD) e l'attributo dell'istruzione SQL_SOPT_SS_NAME_SCOPE accettano i valori aggiuntivi SQL_SS_NAME_SCOPE_EXTENDED e SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="05a19-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="05a19-108">Questi valori specificano le colonne incluse nel set di risultati restituito da [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="05a19-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="05a19-109">Per ulteriori informazioni su SQL_SOPT_SS_NAME_SCOPE, vedere [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="05a19-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="05a19-110">È possibile utilizzare un nuovo descrittore della riga di implementazione (IRD, Implementation Row Descriptor), un campo SQLSMALLINT di sola lettura denominato SQL_CA_SS_IS_COLUMN_SET, per determinare se una colonna è un valore XML di `column_set`.</span><span class="sxs-lookup"><span data-stu-id="05a19-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="05a19-111">SQL_CA_SS_IS_COLUMN_SET accetta i valori SQL_TRUE e SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="05a19-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="05a19-112">Metadati del catalogo</span><span class="sxs-lookup"><span data-stu-id="05a19-112">Catalog Metadata</span></span>  
 <span data-ttu-id="05a19-113">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Sono state aggiunte due colonne specifiche (SS_IS_SPARSE e SS_IS_COLUMN_SET) al set di risultati per [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="05a19-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="05a19-114">Supporto della funzione ODBC per colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="05a19-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="05a19-115">Sono state aggiornate le funzioni ODBC seguenti per supportare colonne di tipo sparse in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="05a19-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="05a19-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="05a19-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="05a19-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="05a19-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="05a19-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="05a19-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="05a19-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="05a19-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="05a19-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="05a19-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="05a19-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05a19-121">See Also</span></span>  
 [<span data-ttu-id="05a19-122">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="05a19-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
