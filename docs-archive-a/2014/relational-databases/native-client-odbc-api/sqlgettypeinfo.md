---
title: SQLGetTypeInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637289"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="27a7b-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="27a7b-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="27a7b-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client segnala la colonna aggiuntiva USERTYPE nel set di risultati di `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="27a7b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="27a7b-104">USERTYPE riporta la definizione del tipo di dati DB-Library e risulta utile agli sviluppatori che trasferiscono applicazioni DB-Library esistenti a ODBC.</span><span class="sxs-lookup"><span data-stu-id="27a7b-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="27a7b-105">tratta l'identità come attributo, mentre ODBC la tratta come tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="27a7b-105">treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="27a7b-106">Per risolvere questa mancata corrispondenza, `SQLGetTypeInfo` restituisce i tipi di dati: **intidentity**, **smallintidentity**, **TinyIntIdentity**, **decimalidentity**e **NumericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="27a7b-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="27a7b-107">La `SQLGetTypeInfo` colonna del set di risultati AUTO_UNIQUE_VALUE restituisce il valore true per questi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="27a7b-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="27a7b-108">Per **varchar**, **nvarchar** e **varbinary**, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client continua a segnalare rispettivamente 8000, 4000 e 8000 per il valore COLUMN_SIZE, anche se è effettivamente illimitato.</span><span class="sxs-lookup"><span data-stu-id="27a7b-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="27a7b-109">Ciò consente di assicurare la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="27a7b-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="27a7b-110">Per il tipo di dati **XML** , il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client segnala SQL_SS_LENGTH_UNLIMITED per COLUMN_SIZE per indicare dimensioni illimitate.</span><span class="sxs-lookup"><span data-stu-id="27a7b-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="27a7b-111">SQLGetTypeInfo e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="27a7b-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="27a7b-112">Il tipo di tabella per i parametri con valori di tabella è effettivamente un metatipo, ovvero un tipo usato per definire altri tipi.</span><span class="sxs-lookup"><span data-stu-id="27a7b-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="27a7b-113">Non è pertanto necessario che venga esposta tramite SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="27a7b-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="27a7b-114">Per recuperare i metadati per i tipi di tabella utilizzati con i parametri con valori di tabella, le applicazioni devono utilizzare SQLTables anziché SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="27a7b-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="27a7b-115">Per ulteriori informazioni sul recupero di metadati per i parametri con valori di tabella, vedere [attributi dell'istruzione che influiscono sui parametri con valori di tabella](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="27a7b-116">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="27a7b-117">Supporto di SQLGetTypeInfo per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="27a7b-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="27a7b-118">Per i valori restituiti per i tipi data/ora, vedere [metadati del catalogo](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="27a7b-119">Per informazioni più generali, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="27a7b-120">Supporto SQLGetTypeInfo per i tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="27a7b-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="27a7b-121">`SQLGetTypeInfo` supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="27a7b-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="27a7b-122">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="27a7b-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a7b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27a7b-123">See Also</span></span>  
 <span data-ttu-id="27a7b-124">[SQLGetTypeInfo (funzione)](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="27a7b-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="27a7b-125">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="27a7b-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
