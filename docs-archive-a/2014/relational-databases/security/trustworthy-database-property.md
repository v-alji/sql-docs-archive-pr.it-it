---
title: Proprietà di database TRUSTWORTHY | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database property
ms.assetid: 64b2a53d-4416-4a19-acc0-664a61b45348
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23391fe48037d4cd7f69aef7df6649949301a0f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713976"
---
# <a name="trustworthy-database-property"></a><span data-ttu-id="a5dec-102">Proprietà di database TRUSTWORTHY</span><span class="sxs-lookup"><span data-stu-id="a5dec-102">TRUSTWORTHY Database Property</span></span>
  <span data-ttu-id="a5dec-103">La proprietà di database TRUSTWORTHY consente di indicare se l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] considera attendibile il database e il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="a5dec-103">The TRUSTWORTHY database property is used to indicate whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trusts the database and the contents within it.</span></span> <span data-ttu-id="a5dec-104">Per impostazione predefinita, questa impostazione ha valore OFF, ma è possibile impostarla su ON tramite l'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="a5dec-104">By default, this setting is OFF, but can be set to ON by using the ALTER DATABASE statement.</span></span> <span data-ttu-id="a5dec-105">Ad esempio: `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span><span class="sxs-lookup"><span data-stu-id="a5dec-105">For example, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5dec-106">Per impostare questa opzione è necessario essere un membro del ruolo predefinito **sysadmin** del server.</span><span class="sxs-lookup"><span data-stu-id="a5dec-106">To set this option, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="a5dec-107">Questa proprietà può essere utilizzata per limitare i rischi che possono derivare dal collegamento a un database contenente uno degli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5dec-107">This property can be used to reduce certain threats that can exist as a result of attaching a database that contains one of the following objects:</span></span>  
  
-   <span data-ttu-id="a5dec-108">Assembly dannosi con un'impostazione di autorizzazione EXTERNAL_ACCESS o UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="a5dec-108">Malicious assemblies with an EXTERNAL_ACCESS or UNSAFE permission setting.</span></span> <span data-ttu-id="a5dec-109">Per altre informazioni, vedere [Sicurezza per l'integrazione con CLR](../clr-integration/security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="a5dec-109">For more information, see [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span></span>  
  
-   <span data-ttu-id="a5dec-110">Moduli dannosi definiti in modo da essere eseguiti con un account utente con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="a5dec-110">Malicious modules that are defined to execute as high privileged users.</span></span> <span data-ttu-id="a5dec-111">Per altre informazioni, vedere [Clausola EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5dec-111">For more information, see [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="a5dec-112">Entrambe le situazioni richiedono un livello di privilegi specifico e vengono evitate grazie a meccanismi appropriati quando tali componenti vengono utilizzati nel contesto di un database già collegato a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5dec-112">Both of these situations require a specific degree of privileges and are protected against by appropriate mechanisms when they are used in the context of a database that is already attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5dec-113">Se però il database è offline, un utente che ha accesso al file di database è potenzialmente in grado di collegarlo a un'istanza arbitraria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e aggiungervi contenuto dannoso.</span><span class="sxs-lookup"><span data-stu-id="a5dec-113">However, if the database is taken offline, a user that has access to the database file can potentially attach it to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of his or her choice and add malicious content to the database.</span></span> <span data-ttu-id="a5dec-114">Quando i database vengono scollegati e collegati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sui dati e sui file di log vengono impostate determinate autorizzazioni che limitano l'accesso ai file di database.</span><span class="sxs-lookup"><span data-stu-id="a5dec-114">When databases are detached and attached in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certain permissions are set on the data and log files that restrict access to the database files.</span></span>  
  
 <span data-ttu-id="a5dec-115">Poiché un database che viene collegato a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non può essere considerato immediatamente attendibile, non può accedere a risorse esterne al proprio ambito fino a quando non verrà esplicitamente contrassegnato come attendibile.</span><span class="sxs-lookup"><span data-stu-id="a5dec-115">Because a database that is attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be immediately trusted, the database is not allowed to access resources beyond the scope of the database until the database is explicitly marked trustworthy.</span></span> <span data-ttu-id="a5dec-116">Sono inoltre previsti ulteriori requisiti per l'esecuzione dei moduli progettati per accedere a risorse esterne al database e degli assembly con impostazione di autorizzazione EXTERNAL_ACCESS e UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="a5dec-116">Also, modules that are designed to access resources outside the database, and assemblies with either the EXTERNAL_ACCESS and UNSAFE permission setting, have additional requirements in order to run successfully.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="a5dec-117">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a5dec-117">Related Content</span></span>  
 [<span data-ttu-id="a5dec-118">Centro sicurezza per il motore di Database di SQL Server e il Database SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="a5dec-118">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="a5dec-119">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5dec-119">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
