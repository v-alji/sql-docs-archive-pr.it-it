---
title: Codici restituiti e informazioni sugli errori di automazione OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- return codes [SQL Server]
- OLE Automation [SQL Server], return codes
- OLE Automation [SQL Server], errors
ms.assetid: 9696fb05-e9e8-4836-b359-d4de0be0eeb2
author: stevestein
ms.author: sstein
ms.openlocfilehash: aecdbaedca42b7456dbdbda0407760959e546f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638371"
---
# <a name="ole-automation-return-codes-and-error-information"></a><span data-ttu-id="e7656-102">Codici restituiti e informazioni sugli errori di automazione OLE</span><span class="sxs-lookup"><span data-stu-id="e7656-102">OLE Automation Return Codes and Error Information</span></span>
  <span data-ttu-id="e7656-103">Le stored procedure del sistema di automazione OLE restituiscono un codice `int` che corrisponde al valore HRESULT restituito dall'operazione di automazione OLE sottostante.</span><span class="sxs-lookup"><span data-stu-id="e7656-103">The OLE Automation system stored procedures return an `int` return code that is the HRESULT returned by the underlying OLE Automation operation.</span></span> <span data-ttu-id="e7656-104">Se HRESULT è 0, l'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e7656-104">An HRESULT of 0 indicates success.</span></span> <span data-ttu-id="e7656-105">Un valore HRESULT diverso da zero è un codice di errore OLE nel formato esadecimale 0x800*nnnnn*, ma quando viene restituito come `int` valore in un stored procedure codice restituito, HRESULT presenta il formato 214*nnnnnnn*.</span><span class="sxs-lookup"><span data-stu-id="e7656-105">A nonzero HRESULT is an OLE error code of the hexadecimal form 0x800*nnnnn*, but when returned as an `int` value in a stored procedure return code, HRESULT has the form 214*nnnnnnn*.</span></span>  
  
 <span data-ttu-id="e7656-106">Ad esempio, passando un nome di oggetto non valido (SQLDMO. Xyzzy) per sp_OACreate fa in modo che la routine restituisca un valore `int` HRESULT 2147221005, ovvero 0x800401F3 in formato esadecimale.</span><span class="sxs-lookup"><span data-stu-id="e7656-106">For example, passing an invalid object name (SQLDMO.Xyzzy) to sp_OACreate causes the procedure to return an `int` HRESULT of 2147221005, which is 0x800401f3 in hexadecimal.</span></span>  
  
 <span data-ttu-id="e7656-107">È possibile utilizzare `CONVERT(binary(4), @hresult)` per convertire un valore HRESULT di tipo `int` in un valore `binary`.</span><span class="sxs-lookup"><span data-stu-id="e7656-107">You can use `CONVERT(binary(4), @hresult)` to convert an `int` HRESULT to a `binary` value.</span></span> <span data-ttu-id="e7656-108">Se tuttavia si utilizza `CONVERT(char(10), CONVERT(binary(4), @hresult))` viene generata una stringa illeggibile, in quanto ogni byte di HRESULT viene convertito in un singolo carattere ASCII.</span><span class="sxs-lookup"><span data-stu-id="e7656-108">However, using `CONVERT(char(10), CONVERT(binary(4), @hresult))` results in an unreadable string, because each byte of the HRESULT is converted to a single ASCII character.</span></span> <span data-ttu-id="e7656-109">È possibile usare il HexToChar di esempio seguente stored procedure per convertire un `int` valore HRESULT in un `char` valore che contiene una stringa esadecimale leggibile.</span><span class="sxs-lookup"><span data-stu-id="e7656-109">You can use the following sample HexToChar stored procedure to convert an `int` HRESULT to a `char` value that contains a readable hexadecimal string.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF EXISTS(SELECT name FROM sys.objects  
          WHERE name = N'dbo.sp_HexToChar')  
    DROP PROCEDURE HexToChar;  
GO  
CREATE PROCEDURE dbo.sp_HexToChar  
    @BinValue varbinary(255),  
    @HexCharValue nvarchar(255) OUTPUT  
AS  
    DECLARE @CharValue nvarchar(255);  
    DECLARE @Position int;  
    DECLARE @Length int;  
    DECLARE @HexString nchar(16);  
    SELECT @CharValue = N'0x';  
    SELECT @Position = 1;  
    SELECT @Length = DATALENGTH(@BinValue);  
    SELECT @HexString = N'0123456789ABCDEF';  
    WHILE (@Position <= @Length)  
    BEGIN  
        DECLARE @TempInt int;  
        DECLARE @FirstInt int;  
        DECLARE @SecondInt int;  
        SELECT @TempInt = CONVERT(int, SUBSTRING(@BinValue,@Position,1));  
        SELECT @FirstInt = FLOOR(@TempInt/16);  
        SELECT @SecondInt = @TempInt - (@FirstInt*16);  
        SELECT @CharValue = @CharValue +  
            SUBSTRING(@HexString, @FirstInt+1, 1) +  
            SUBSTRING(@HexString, @SecondInt+1, 1);  
        SELECT @Position = @Position + 1;  
    END  
    SELECT @HexCharValue = @CharValue;  
GO  
DECLARE @BinVariable varbinary(35);  
DECLARE @CharValue nvarchar(35);  
  
SET @BinVariable = 123456;  
  
EXECUTE dbo.sp_HexToChar  
    @binvalue = @BinVariable,  
    @HexCharValue = @CharValue OUTPUT;  
  
SELECT @BinVariable AS BinaryValue,  
    @CharValue AS CharacterRep;  
GO  
```  
  
 <span data-ttu-id="e7656-110">La stored procedure **sp_displayoaerrorinfo** dell'esempio seguente consente di visualizzare le informazioni sugli errori di automazione OLE quando una delle procedure di automazione OLE restituisce un codice di restituzione HRESULT diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="e7656-110">You can use the following sample stored procedure, **sp_displayoaerrorinfo** to display OLE Automation error information when one of the OLE Automation procedures returns a nonzero HRESULT return code.</span></span> <span data-ttu-id="e7656-111">Questo esempio stored procedure USA `HexToChar` .</span><span class="sxs-lookup"><span data-stu-id="e7656-111">This sample stored procedure uses `HexToChar`.</span></span>  
  
```  
CREATE PROCEDURE dbo.sp_DisplayOAErrorInfo  
    @Object int,  
    @HResult int  
AS  
    DECLARE @Output nvarchar(255);  
    DECLARE @HRHex nchar(10);  
    DECLARE @HR int;  
    DECLARE @Source nvarchar(255);  
    DECLARE @Description nvarchar(255);  
    PRINT N'OLE Automation Error Information';  
    EXEC HexToChar @HResult, @HRHex OUT;  
    SELECT @Output = N'  HRESULT: ' + @HRHex;  
    PRINT @Output;  
    EXEC @HR = sp_OAGetErrorInfo  
        @Object,  
        @Source OUT,  
        @Description OUT;  
    IF @HR = 0  
    BEGIN  
        SELECT @Output = N'  Source: ' + @Source;  
        PRINT @Output;  
        SELECT @Output = N'  Description: '  
               + @Description;  
        PRINT @Output;  
    END  
    ELSE  
    BEGIN  
       PRINT N' sp_OAGetErrorInfo failed.';  
       RETURN;  
    END  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="e7656-112">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="e7656-112">Related Content</span></span>  
 [<span data-ttu-id="e7656-113">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7656-113">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
  
