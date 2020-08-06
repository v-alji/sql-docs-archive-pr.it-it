---
title: Funzionalità modificate (database indipendente) | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725839"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="4cc6f-102">Funzionalità modificate (database indipendente)</span><span class="sxs-lookup"><span data-stu-id="4cc6f-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="4cc6f-103">Le funzionalità seguenti sono state modificate per consentirne il supporto in un database parzialmente indipendente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="4cc6f-104">Le funzionalità vengono generalmente modificate per evitare che superino il limite del database.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="4cc6f-105">Per altre informazioni, vedere [Database indipendenti](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4cc6f-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="4cc6f-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="4cc6f-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="4cc6f-107">Livello dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="4cc6f-107">Application Level</span></span>  
 <span data-ttu-id="4cc6f-108">In caso di utilizzo dell'istruzione ALTER DATABASE dall'interno di un database indipendente, la sintassi differisce da quella utilizzata per un database non indipendente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="4cc6f-109">Questa differenza include restrizioni di elementi dell'istruzione che si estendono oltre il database fino all'istanza.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="4cc6f-110">Per altre informazioni, vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cc6f-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="4cc6f-111">Livello di istanza</span><span class="sxs-lookup"><span data-stu-id="4cc6f-111">Instance Level</span></span>  
 <span data-ttu-id="4cc6f-112">Quanto l'istruzione ALTER DATABASE viene utilizzata all'esterno di un database indipendente, la relativa sintassi differisce da quella utilizzata per un database non indipendente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="4cc6f-113">Queste modifiche impediscono di varcare il limite del database.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="4cc6f-114">Per altre informazioni, vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cc6f-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="4cc6f-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="4cc6f-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="4cc6f-116">La sintassi di CREATE DATABASE per un database indipendente differisce da quella per un database non indipendente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="4cc6f-117">Per informazioni sui nuovi requisiti della sintassi, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4cc6f-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="4cc6f-118">Tabelle temporanee</span><span class="sxs-lookup"><span data-stu-id="4cc6f-118">Temporary Tables</span></span>  
 <span data-ttu-id="4cc6f-119">All'interno di un database indipendente sono consentite tabelle temporanee locali, ma il relativo comportamento differisce da quelle presenti nei database non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="4cc6f-120">Nei database non indipendenti i dati delle tabelle temporanee vengono confrontati nelle regole di confronto di **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="4cc6f-121">In un database indipendente i dati delle tabelle temporanee vengono confrontati nelle regole di confronto del database indipendente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="4cc6f-122">Tutti i metadati associati alle tabelle temporanee (ad esempio nomi di tabella e di colonna, indici e così via) saranno inclusi nelle regole di confronto del catalogo.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="4cc6f-123">È possibile che vincoli denominati non vengano utilizzati nelle tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="4cc6f-124">Le tabelle temporanee potrebbero non fare riferimento a tipi definiti dall'utente, raccolte di XML Schema o funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="4cc6f-125">Regole di confronto</span><span class="sxs-lookup"><span data-stu-id="4cc6f-125">Collation</span></span>  
 <span data-ttu-id="4cc6f-126">Nel modello di database non indipendente sono presenti tre tipi distinti di regole di confronto: del database, dell'istanza e di tempdb.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="4cc6f-127">Nei database indipendenti vengono utilizzate solo due regole di confronto, ovvero regole di confronto del database e nuove regole di confronto del catalogo.</span><span class="sxs-lookup"><span data-stu-id="4cc6f-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="4cc6f-128">Per altre informazioni sulle regole di confronto dei database indipendenti, vedere [Regole di confronto dei database indipendenti](contained-database-collations.md) .</span><span class="sxs-lookup"><span data-stu-id="4cc6f-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="4cc6f-129">User Options</span><span class="sxs-lookup"><span data-stu-id="4cc6f-129">User Options</span></span>  
 <span data-ttu-id="4cc6f-130">In caso di abilitazione di database indipendenti, è necessario impostare l'opzione [Opzioni User](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) su 0 per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc6f-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc6f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cc6f-131">See Also</span></span>  
 <span data-ttu-id="4cc6f-132">[Regole di confronto dei database indipendenti](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="4cc6f-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="4cc6f-133">Database indipendenti</span><span class="sxs-lookup"><span data-stu-id="4cc6f-133">Contained Databases</span></span>](contained-databases.md)  
  
  
