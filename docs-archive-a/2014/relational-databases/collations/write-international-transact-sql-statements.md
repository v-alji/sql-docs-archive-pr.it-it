---
title: Scrittura di istruzioni Transact-SQL internazionali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637898"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="d3e6f-102">Scrittura di istruzioni Transact-SQL internazionali</span><span class="sxs-lookup"><span data-stu-id="d3e6f-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="d3e6f-103">Le linee guida seguenti consentono di aumentare il grado di portabilità tra lingue diverse, nonché il supporto di più lingue, per i database e le applicazioni di database che utilizzano istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3e6f-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="d3e6f-104">Sostituire tutte le occorrenze dei tipi di dati `char`, `varchar` e `text` con `nchar`, `nvarchar` e `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="d3e6f-105">In questo modo non si verificano problemi a livello di conversione della tabella codici.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="d3e6f-106">Per altre informazioni, vedere [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="d3e6f-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="d3e6f-107">Quando si eseguono confronti e operazioni con mesi o giorni della settimana, utilizzare le parti numeriche della data anziché le stringhe di nomi.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="d3e6f-108">I nomi dei mesi e dei giorni della settimana restituiti variano a seconda dell'impostazione della lingua.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="d3e6f-109">Ad esempio, DATENAME (MONTH,GETDATE()) restituisce May quando la lingua è impostata sull'inglese (Stati Uniti) Mai se è impostato il tedesco e mai se è impostato il francese.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="d3e6f-110">Specificare pertanto una funzione quale DATEPART che utilizza il numero anziché il nome del mese.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="d3e6f-111">Utilizzare i nomi DATEPART quando si compilano i set di risultati da visualizzare all'utente, in quanto le stringhe di nomi sono più significative delle parti numeriche.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="d3e6f-112">Non creare tuttavia il codice di logica che dipende dai nomi visualizzati di una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="d3e6f-113">Quando si specificano le date nei confronti o nell'input di istruzioni INSERT e UPDATE, utilizzare costanti che vengono interpretate nello stesso modo indipendentemente dall'impostazione della lingua:</span><span class="sxs-lookup"><span data-stu-id="d3e6f-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="d3e6f-114">Le applicazioni ADO, OLE DB e ODBC devono utilizzare le clausole di escape seguenti relative a timestamp, data e ora:</span><span class="sxs-lookup"><span data-stu-id="d3e6f-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="d3e6f-115">**{ts '** aaaa **-** _mm_ **-** _DDHH_**:**_mm_**:**_ss_[**.** _fff_] **'}** ad esempio: **{ts '** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="d3e6f-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="d3e6f-116">**{ d'** _aaaa_ **-** _mm_ **-** _gg_ **'}** ad esempio: **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="d3e6f-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="d3e6f-117">**{t'** _HH_ **:** _mm_ **:** _SS_ **'}** ad esempio: **{t'** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="d3e6f-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="d3e6f-118">Nelle applicazioni che utilizzano altre API, oppure script, stored procedure e trigger di [!INCLUDE[tsql](../../includes/tsql-md.md)] , è necessario utilizzare le stringhe numeriche non separate,</span><span class="sxs-lookup"><span data-stu-id="d3e6f-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="d3e6f-119">Ad esempio, *aaaammgg* come 19980924.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="d3e6f-120">Per le applicazioni che utilizzano altre API, o [!INCLUDE[tsql](../../includes/tsql-md.md)] script, stored procedure e trigger, è necessario utilizzare l'istruzione CONVERT con un parametro di stile esplicito per tutte le conversioni tra i tipi di dati `time` , `date` , `smalldate` , `datetime` , **datetime2**e e i tipi di dati `datetimeoffset` stringa di caratteri.</span><span class="sxs-lookup"><span data-stu-id="d3e6f-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="d3e6f-121">L'istruzione seguente viene interpretata nello stesso modo indipendentemente dalle impostazioni di connessione della lingua o del formato della data:</span><span class="sxs-lookup"><span data-stu-id="d3e6f-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="d3e6f-122">Per altre informazioni, vedere [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d3e6f-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
