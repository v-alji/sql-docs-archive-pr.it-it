---
title: Verificare l'integrità di un database contenente pagine sospette | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711900"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="99934-102">Verifica del'integrità di un database contenente pagine sospette</span><span class="sxs-lookup"><span data-stu-id="99934-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="99934-103">Questa regola consente di controllare i database utente con stato impostato come sospetto.</span><span class="sxs-lookup"><span data-stu-id="99934-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="99934-104">Quando il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] legge una pagina di database contenente un errore 824, la pagina viene considerata sospetta, l'ID di pagina corrispondente viene registrato nella tabella suspect_pages in msdb e il database contenente la pagina viene impostato come sospetto.</span><span class="sxs-lookup"><span data-stu-id="99934-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="99934-105">L'errore 824 indica che è stato rilevato un errore logico correlato alla consistenza durante un'operazione di lettura.</span><span class="sxs-lookup"><span data-stu-id="99934-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="99934-106">Questo errore indica in genere il danneggiamento dei dati causato da un componente del sottosistema di I/O difettoso.</span><span class="sxs-lookup"><span data-stu-id="99934-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="99934-107">Si tratta di una condizione di errore grave che può compromettere l'integrità del database e che deve essere corretta immediatamente.</span><span class="sxs-lookup"><span data-stu-id="99934-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="99934-108">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="99934-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="99934-109">Esaminare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per individuare informazioni dettagliate sull'errore 824 per il database.</span><span class="sxs-lookup"><span data-stu-id="99934-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="99934-110">Eseguire una verifica di coerenza del database ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="99934-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="99934-111">Implementare le azioni dell'utente definite in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span><span class="sxs-lookup"><span data-stu-id="99934-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="99934-112">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="99934-112">For More Information</span></span>  
 [<span data-ttu-id="99934-113">Gestione della tabella suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99934-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
