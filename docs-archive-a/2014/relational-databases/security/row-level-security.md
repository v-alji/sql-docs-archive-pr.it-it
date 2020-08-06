---
title: Sicurezza a livello di riga | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- row level security described
- row level security
- access control predicates
- security [SQL Server], predicate based access control
- predicate based security
ms.assetid: 7221fa4e-ca4a-4d5c-9f93-1b8a4af7b9e8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c67f84723e79b66d0454fb509f2fa9ced03dac7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714024"
---
# <a name="row-level-security"></a><span data-ttu-id="04957-102">Sicurezza a livello di riga</span><span class="sxs-lookup"><span data-stu-id="04957-102">Row-Level Security</span></span>
  <span data-ttu-id="04957-103">La sicurezza a livello di riga consente ai clienti di controllare l'accesso alle righe in una tabella di database in base alle caratteristiche dell'utente che esegue una query, ad esempio l'appartenenza a un gruppo o il contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="04957-103">Row-Level Security enables customers to control access to rows in a database table based on the characteristics of the user executing a query (e.g., group membership or execution context).</span></span> <span data-ttu-id="04957-104">La sicurezza a livello di riga è ora disponibile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span><span class="sxs-lookup"><span data-stu-id="04957-104">Row-Level Security is now available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span></span> <span data-ttu-id="04957-105">Per la descrizione attuale di questa funzionalità, vedere [Sicurezza a livello di riga](https://msdn.microsoft.com/library/dn765131.aspx) nella documentazione corrente.</span><span class="sxs-lookup"><span data-stu-id="04957-105">See [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) in the current documentation for the current description of this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04957-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04957-106">See Also</span></span>  
 <span data-ttu-id="04957-107">[CREARE criteri di sicurezza &#40;database SQL di Azure&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-107">[CREATE SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="04957-108">[MODIFICARE i criteri di sicurezza &#40;database SQL di Azure&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-108">[ALTER SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="04957-109">[ELIMINARE i criteri di sicurezza &#40;database SQL di Azure&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-109">[DROP SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="04957-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 <span data-ttu-id="04957-111">[sys. security_policies &#40;database SQL di Azure&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-111">[sys.security_policies &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span></span>  
 <span data-ttu-id="04957-112">[sys. security_predicates &#40;database SQL di Azure&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="04957-112">[sys.security_predicates &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span></span>  
 [<span data-ttu-id="04957-113">Creare funzioni definite dall'utente &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="04957-113">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)  
  
  
