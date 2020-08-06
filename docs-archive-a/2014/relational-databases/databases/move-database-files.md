---
title: Spostare file del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- disaster recovery [SQL Server], moving database files
- files [SQL Server], moving
- data files [SQL Server], moving
- file moving [SQL Server]
- moving full-text catalogs
- moving databases
- full-text catalogs [SQL Server], moving
- moving database files
- scheduled disk maintenance [SQL Server]
- moving files
- relocating database files
- planned database relocations [SQL Server]
- databases [SQL Server], moving
ms.assetid: 89f01b10-5fae-4ed8-b0fb-a4b9f540fd28
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5491f3c4dfd47cac4047d0409c78001be80d6f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721475"
---
# <a name="move-database-files"></a><span data-ttu-id="2a32b-102">Spostare file del database</span><span class="sxs-lookup"><span data-stu-id="2a32b-102">Move Database Files</span></span>
  <span data-ttu-id="2a32b-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]è possibile spostare i file di database di sistema e definiti dall'utente specificando la nuova posizione dei file nella clausola FILENAME dell'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="2a32b-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can move system and user databases by specifying the new file location in the FILENAME clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="2a32b-104">In questo modo è possibile spostare file di dati, di log e del catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="2a32b-104">Data, log, and full-text catalog files can be moved in this way.</span></span> <span data-ttu-id="2a32b-105">Questo può risultare utile nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a32b-105">This may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="2a32b-106">Recupero da errore.</span><span class="sxs-lookup"><span data-stu-id="2a32b-106">Failure recovery.</span></span> <span data-ttu-id="2a32b-107">Ad esempio, il database è in modalità sospetta oppure viene chiuso, a causa di un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="2a32b-107">For example, the database is in suspect mode or has shut down, because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="2a32b-108">Rilocazione pianificata.</span><span class="sxs-lookup"><span data-stu-id="2a32b-108">Planned relocation.</span></span>  
  
-   <span data-ttu-id="2a32b-109">Rilocazione per una manutenzione pianificata del disco.</span><span class="sxs-lookup"><span data-stu-id="2a32b-109">Relocation for scheduled disk maintenance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a32b-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2a32b-110">In This Section</span></span>  
  
|<span data-ttu-id="2a32b-111">Argomento</span><span class="sxs-lookup"><span data-stu-id="2a32b-111">Topic</span></span>|<span data-ttu-id="2a32b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a32b-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2a32b-113">Spostare database utente</span><span class="sxs-lookup"><span data-stu-id="2a32b-113">Move User Databases</span></span>](move-user-databases.md)|<span data-ttu-id="2a32b-114">Descrive le procedure necessarie per spostare i file di database definiti dall'utente e i file dei cataloghi in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="2a32b-114">Describes the procedures for moving user database files and full-text catalog files to a new location.</span></span>|  
|[<span data-ttu-id="2a32b-115">Spostare i database di sistema</span><span class="sxs-lookup"><span data-stu-id="2a32b-115">Move System Databases</span></span>](system-databases.md)|<span data-ttu-id="2a32b-116">Descrive le procedure necessarie per spostare i file di database di sistema in una nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="2a32b-116">Describes the procedures for moving system database files to a new location.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a32b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a32b-117">See Also</span></span>  
 <span data-ttu-id="2a32b-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a32b-118">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="2a32b-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a32b-119">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="2a32b-120">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2a32b-120">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
