---
title: Mapping dei dati dei parametri CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725959"
---
# <a name="mapping-clr-parameter-data"></a><span data-ttu-id="05c7a-102">Mapping dei dati dei parametri CLR</span><span class="sxs-lookup"><span data-stu-id="05c7a-102">Mapping CLR Parameter Data</span></span>
  <span data-ttu-id="05c7a-103">Nella tabella seguente sono elencati i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati, gli equivalenti nella Common Language Runtime (CLR) per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nello `System.Data.SqlTypes` spazio dei nomi e i relativi equivalenti CLR nativi nell' [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05c7a-103">The following table lists [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, their equivalents in the common language runtime (CLR) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the `System.Data.SqlTypes` namespace, and their native CLR equivalents in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="05c7a-104">**Tipo di dati di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="05c7a-104">**SQL Server data type**</span></span>|<span data-ttu-id="05c7a-105">Tipo (in System.Data.SqlTypes o Microsoft.SqlServer.Types)</span><span class="sxs-lookup"><span data-stu-id="05c7a-105">Type (in System.Data.SqlTypes or Microsoft.SqlServer.Types)</span></span>|<span data-ttu-id="05c7a-106">**Tipo di dati CLR (.NET Framework)**</span><span class="sxs-lookup"><span data-stu-id="05c7a-106">**CLR data type (.NET Framework)**</span></span>|  
|`bigint`|`SqlInt64`|<span data-ttu-id="05c7a-107">**Int64, Nullable\<Int64>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-107">**Int64, Nullable\<Int64>**</span></span>|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|<span data-ttu-id="05c7a-108">**Booleano, Nullable\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-108">**Boolean, Nullable\<Boolean>**</span></span>|  
|`char`|<span data-ttu-id="05c7a-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-109">None</span></span>|<span data-ttu-id="05c7a-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-110">None</span></span>|  
|`cursor`|<span data-ttu-id="05c7a-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-111">None</span></span>|<span data-ttu-id="05c7a-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-112">None</span></span>|  
|`date`|`SqlDateTime`|<span data-ttu-id="05c7a-113">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-113">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime`|`SqlDateTime`|<span data-ttu-id="05c7a-114">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-114">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime2`|<span data-ttu-id="05c7a-115">Nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-115">None</span></span>|<span data-ttu-id="05c7a-116">**DateTime, Nullable\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-116">**DateTime, Nullable\<DateTime>**</span></span>|  
|`DATETIMEOFFSET`|`None`|<span data-ttu-id="05c7a-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span></span>|  
|`decimal`|`SqlDecimal`|<span data-ttu-id="05c7a-118">**Decimale, Nullable\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-118">**Decimal, Nullable\<Decimal>**</span></span>|  
|`float`|`SqlDouble`|<span data-ttu-id="05c7a-119">**Double, Nullable\<Double>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-119">**Double, Nullable\<Double>**</span></span>|  
|`geography`|`SqlGeography`<br /><br /> <span data-ttu-id="05c7a-120">`SqlGeography`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="05c7a-120">`SqlGeography` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="05c7a-121">Nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-121">None</span></span>|  
|`geometry`|`SqlGeometry`<br /><br /> <span data-ttu-id="05c7a-122">`SqlGeometry`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="05c7a-122">`SqlGeometry` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="05c7a-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-123">None</span></span>|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> <span data-ttu-id="05c7a-124">`SqlHierarchyId`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).</span><span class="sxs-lookup"><span data-stu-id="05c7a-124">`SqlHierarchyId` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="05c7a-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-125">None</span></span>|  
|`image`|<span data-ttu-id="05c7a-126">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-126">None</span></span>|<span data-ttu-id="05c7a-127">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-127">None</span></span>|  
|`int`|`SqlInt32`|<span data-ttu-id="05c7a-128">**Int32, Nullable\<Int32>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-128">**Int32, Nullable\<Int32>**</span></span>|  
|`money`|`SqlMoney`|<span data-ttu-id="05c7a-129">**Decimale, Nullable\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-129">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|<span data-ttu-id="05c7a-130">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-130">None</span></span>|<span data-ttu-id="05c7a-131">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-131">None</span></span>|  
|`numeric`|`SqlDecimal`|<span data-ttu-id="05c7a-132">**Decimale, Nullable\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-132">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> <span data-ttu-id="05c7a-133">`SQLChars` rappresenta la soluzione migliore per il trasferimento dei dati e l'accesso ai dati, mentre `SQLString` è preferibile per l'esecuzione di operazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="05c7a-133">`SQLChars` is a better match for data transfer and access, and `SQLString` is a better match for performing String operations.</span></span>|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|<span data-ttu-id="05c7a-134">**Char, String, Char [], Nullable\<char>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-134">**Char, String, Char[], Nullable\<char>**</span></span>|  
|`real`|<span data-ttu-id="05c7a-135">`SqlSingle` (la gamma di `SqlSingle`, tuttavia, è maggiore di `real`)</span><span class="sxs-lookup"><span data-stu-id="05c7a-135">`SqlSingle` (the range of `SqlSingle`, however, is larger than `real`)</span></span>|<span data-ttu-id="05c7a-136">**Singolo, Nullable\<Single>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-136">**Single, Nullable\<Single>**</span></span>|  
|`rowversion`|<span data-ttu-id="05c7a-137">Nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-137">None</span></span>|`Byte[]`|  
|`smallint`|`SqlInt16`|<span data-ttu-id="05c7a-138">**Int16, Nullable\<Int16>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-138">**Int16, Nullable\<Int16>**</span></span>|  
|`smallmoney`|`SqlMoney`|<span data-ttu-id="05c7a-139">**Decimale, Nullable\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-139">**Decimal, Nullable\<Decimal>**</span></span>|  
|`sql_variant`|<span data-ttu-id="05c7a-140">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-140">None</span></span>|`Object`|  
|`table`|<span data-ttu-id="05c7a-141">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-141">None</span></span>|<span data-ttu-id="05c7a-142">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-142">None</span></span>|  
|`text`|<span data-ttu-id="05c7a-143">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-143">None</span></span>|<span data-ttu-id="05c7a-144">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-144">None</span></span>|  
|`time`|<span data-ttu-id="05c7a-145">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-145">None</span></span>|<span data-ttu-id="05c7a-146">**TimeSpan, Nullable\<TimeSpan>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-146">**TimeSpan, Nullable\<TimeSpan>**</span></span>|  
|`timestamp`|<span data-ttu-id="05c7a-147">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-147">None</span></span>|<span data-ttu-id="05c7a-148">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-148">None</span></span>|  
|`tinyint`|`SqlByte`|<span data-ttu-id="05c7a-149">**Byte, Nullable\<Byte>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-149">**Byte, Nullable\<Byte>**</span></span>|  
|`uniqueidentifier`|`SqlGuid`|<span data-ttu-id="05c7a-150">**GUID, Nullable\<Guid>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-150">**Guid, Nullable\<Guid>**</span></span>|  
|`User-defined type(UDT)`|<span data-ttu-id="05c7a-151">Nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-151">None</span></span>|<span data-ttu-id="05c7a-152">La stessa classe associata al tipo definito dall'utente (UDT) nello stesso assembly o un assembly dipendente.</span><span class="sxs-lookup"><span data-stu-id="05c7a-152">The same class that is bound to the user-defined type in the same assembly or a dependent assembly.</span></span>|  
|<span data-ttu-id="05c7a-153">**varbinary**</span><span class="sxs-lookup"><span data-stu-id="05c7a-153">**varbinary**</span></span>|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|<span data-ttu-id="05c7a-154">**byte, byte [], Nullable\<byte>**</span><span class="sxs-lookup"><span data-stu-id="05c7a-154">**byte, Byte[], Nullable\<byte>**</span></span>|  
|`varchar`|<span data-ttu-id="05c7a-155">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-155">None</span></span>|<span data-ttu-id="05c7a-156">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-156">None</span></span>|  
|`xml`|`SqlXml`|<span data-ttu-id="05c7a-157">nessuno</span><span class="sxs-lookup"><span data-stu-id="05c7a-157">None</span></span>|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a><span data-ttu-id="05c7a-158">Conversione automatica dei tipi di dati con parametri Out</span><span class="sxs-lookup"><span data-stu-id="05c7a-158">Automatic Data Type Conversion with Out Parameters</span></span>  
 <span data-ttu-id="05c7a-159">Un metodo CLR può restituire informazioni al codice o programma chiamante contrassegnando un parametro di input con il modificatore `out` (Microsoft Visual C#) o `<Out()> ByRef` (Microsoft Visual Basic). Se il parametro di input è un tipo di dati CLR nello spazio dei nomi `System.Data.SqlTypes` e il programma chiamante ne specifica il tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalente come parametro di input, una conversione dei tipi avviene automaticamente quando il metodo CLR restituisce il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="05c7a-159">A CLR method can return information to the calling code or program by marking an input parameter with the `out` modifier (Microsoft Visual C#) or `<Out()> ByRef` (Microsoft Visual Basic) If the input parameter is a CLR data type in the `System.Data.SqlTypes` namespace, and the calling program specifies its equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as the input parameter, a type conversion occurs automatically when the CLR method returns the data type.</span></span>  
  
 <span data-ttu-id="05c7a-160">La stored procedure CLR seguente, ad esempio, include un parametro di input dei dati CLR `SqlInt32` contrassegnato da `out` (C#) o `<Out()> ByRef` (Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="05c7a-160">For example, the following CLR stored procedure has an input parameter of `SqlInt32` CLR data type that is marked with `out` (C#) or `<Out()> ByRef` (Visual Basic):</span></span>  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 <span data-ttu-id="05c7a-161">Dopo che l'assembly è stato compilato e creato nel database, la stored procedure viene creata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'istruzione Transact-SQL seguente che specifica un tipo dei dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di `int` come parametro OUTPUT:</span><span class="sxs-lookup"><span data-stu-id="05c7a-161">After the assembly is built and created in the database, the stored procedure is created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the following Transact-SQL, which specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of `int` as an OUTPUT parameter:</span></span>  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 <span data-ttu-id="05c7a-162">Quando la stored procedure CLR viene chiamata, il tipo di dati `SqlInt32` viene convertito automaticamente in un tipo di dati `int` e restituito al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="05c7a-162">When the CLR stored procedure is called, the `SqlInt32` data type is automatically converted to an `int` data type, and returned to the calling program.</span></span>  
  
 <span data-ttu-id="05c7a-163">Non tutti i tipi di dati CLR possono essere convertiti automaticamente nei tipi dei dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalenti tramite un parametro out.</span><span class="sxs-lookup"><span data-stu-id="05c7a-163">Not all CLR data types can be automatically converted to their equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types through an out parameter, however.</span></span> <span data-ttu-id="05c7a-164">Nella seguente tabella vengono descritte queste eccezioni.</span><span class="sxs-lookup"><span data-stu-id="05c7a-164">The following table lists these exceptions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05c7a-165">**Tipo di dati CLR (SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="05c7a-165">**CLR data type (SQL Server)**</span></span>|<span data-ttu-id="05c7a-166">**Tipo di dati di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="05c7a-166">**SQL Server data type**</span></span>|  
|`Decimal`|<span data-ttu-id="05c7a-167">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="05c7a-167">smallmoney</span></span>|  
|`SqlMoney`|<span data-ttu-id="05c7a-168">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="05c7a-168">smallmoney</span></span>|  
|`Decimal`|<span data-ttu-id="05c7a-169">money</span><span class="sxs-lookup"><span data-stu-id="05c7a-169">money</span></span>|  
|`DateTime`|<span data-ttu-id="05c7a-170">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="05c7a-170">smalldatetime</span></span>|  
|`SQLDateTime`|<span data-ttu-id="05c7a-171">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="05c7a-171">smalldatetime</span></span>|  
  
## <a name="change-history"></a><span data-ttu-id="05c7a-172">Cronologia modifiche</span><span class="sxs-lookup"><span data-stu-id="05c7a-172">Change History</span></span>  
  
|<span data-ttu-id="05c7a-173">Contenuto aggiornato</span><span class="sxs-lookup"><span data-stu-id="05c7a-173">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="05c7a-174">Aggiunta dei tipi `SqlGeography`, `SqlGeometry` e `SqlHierarchyId` alla tabella di mapping.</span><span class="sxs-lookup"><span data-stu-id="05c7a-174">Added `SqlGeography`, `SqlGeometry`, and `SqlHierarchyId` types to the mapping table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05c7a-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05c7a-175">See Also</span></span>  
 [<span data-ttu-id="05c7a-176">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="05c7a-176">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
