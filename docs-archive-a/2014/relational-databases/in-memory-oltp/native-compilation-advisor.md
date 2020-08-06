---
title: Assistente compilazione nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725744"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="643a0-102">Assistente compilazione nativa</span><span class="sxs-lookup"><span data-stu-id="643a0-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="643a0-103">Lo strumento dei report sulle prestazioni delle transazioni (vedere [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) indica quali stored procedure interpretate nel database trarranno vantaggio se trasferite per utilizzare la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="643a0-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="643a0-104">Una volta identificata la stored procedure da trasferire per l'utilizzo nella compilazione nativa, è possibile utilizzare l'Assistente compilazione nativa per facilitare la migrazione della stored procedure interpretata alla compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="643a0-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="643a0-105">Per altre informazioni sulle stored procedure compilate in modo nativo, vedere [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="643a0-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="643a0-106">Connettersi innanzitutto all'istanza contenente la stored procedure interpretata.</span><span class="sxs-lookup"><span data-stu-id="643a0-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="643a0-107">È possibile connettersi all'istanza di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]o [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="643a0-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="643a0-108">Tuttavia, se si desidera effettuare la migrazione con il supporto dell'Assistente compilazione nativa, è necessario connettersi a un'istanza di [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] in cui la funzionalità OLTP in memoria sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="643a0-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="643a0-109">Per ulteriori informazioni sui requisiti di OLTP in memoria, vedere [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="643a0-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="643a0-110">Per informazioni sulle metodologie di migrazione, vedere [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx) (OLTP in memoria: considerazioni sulla migrazione e sui modelli di carico di lavoro comuni).</span><span class="sxs-lookup"><span data-stu-id="643a0-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="643a0-111">Procedura dettagliata per l'utilizzo dell'Assistente compilazione nativa</span><span class="sxs-lookup"><span data-stu-id="643a0-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="643a0-112">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla stored procedure che si desidera convertire, quindi selezionare **Assistente compilazione nativa**.</span><span class="sxs-lookup"><span data-stu-id="643a0-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="643a0-113">Verrà visualizzata la pagina introduttiva di **Assistente compilazione nativa stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="643a0-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="643a0-114">Fare clic su **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="643a0-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="643a0-115">Convalida stored procedure</span><span class="sxs-lookup"><span data-stu-id="643a0-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="643a0-116">In questa pagina verrà indicato se la stored procedure utilizza dei costrutti che non sono compatibili con la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="643a0-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="643a0-117">Fare clic su **Avanti** per vedere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="643a0-117">You can click **Next** to see details.</span></span> <span data-ttu-id="643a0-118">Se sono presenti costrutti che non sono compatibili con la compilazione nativa, fare clic su **Avanti** per vedere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="643a0-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="643a0-119">Risultati di convalida stored procedure</span><span class="sxs-lookup"><span data-stu-id="643a0-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="643a0-120">I dettagli su eventuali costrutti non compatibili con la compilazione nativa saranno visualizzati nella pagina **Risultati di convalida stored procedure** .</span><span class="sxs-lookup"><span data-stu-id="643a0-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="643a0-121">È possibile generare un report (facendo clic su **Genera report**), uscire da **Assistente compilazione nativa**e aggiornare il codice in modo che risulti compatibile con la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="643a0-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="643a0-122">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="643a0-122">Code Sample</span></span>  
 <span data-ttu-id="643a0-123">Nell'esempio seguente viene mostrata una stored procedure interpretata e la stored procedure equivalente per la compilazione nativa.</span><span class="sxs-lookup"><span data-stu-id="643a0-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="643a0-124">Nell'esempio viene supposto l'utilizzo di una directory denominata c:\data.</span><span class="sxs-lookup"><span data-stu-id="643a0-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="643a0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="643a0-125">See Also</span></span>  
 [<span data-ttu-id="643a0-126">Migrazione a OLTP in memoria</span><span class="sxs-lookup"><span data-stu-id="643a0-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
