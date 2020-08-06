---
title: Opzione di configurazione del server cross db ownership chaining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cross-database ownership chaining
- cross db ownership chaining option
- chaining ownership
ms.assetid: 7b2d49f2-b91c-4aee-a52b-6cc49bed03af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cfb768065cc0aa2aaa7aed0f996b18e46f1da7ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629608"
---
# <a name="cross-db-ownership-chaining-server-configuration-option"></a><span data-ttu-id="7bb81-102">Opzione di configurazione del server cross db ownership chaining</span><span class="sxs-lookup"><span data-stu-id="7bb81-102">cross db ownership chaining Server Configuration Option</span></span>
  <span data-ttu-id="7bb81-103">L'opzione **cross db ownership chaining** consente di configurare il concatenamento della proprietà tra database per un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bb81-103">Use the **cross db ownership chaining** option to configure cross-database ownership chaining for an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7bb81-104">Questa opzione del server consente di controllare il concatenamento della proprietà tra database a livello del database oppure di attivare il concatenamento della proprietà per tutti i database:</span><span class="sxs-lookup"><span data-stu-id="7bb81-104">This server option allows you to control cross-database ownership chaining at the database level or to allow cross-database ownership chaining for all databases:</span></span>  
  
-   <span data-ttu-id="7bb81-105">Quando l'opzione **cross db ownership chaining** è impostata su 0 per l'istanza, il concatenamento della proprietà tra database è disabilitato per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="7bb81-105">When **cross db ownership chaining** is off (0) for the instance, cross-database ownership chaining is disabled for all databases.</span></span>  
  
-   <span data-ttu-id="7bb81-106">Quando invece l'opzione **cross db ownership chaining** è impostata su 1 per l'istanza, il concatenamento della proprietà tra database è attivato per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="7bb81-106">When **cross db ownership chaining** is on (1) for the instance, cross-database ownership chaining is on for all databases.</span></span>  
  
-   <span data-ttu-id="7bb81-107">È possibile impostare il concatenamento della proprietà tra database per singoli database utilizzando la clausola SET dell'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="7bb81-107">You can set cross-database ownership chaining for individual databases using the SET clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="7bb81-108">Se si intende creare un nuovo database, è possibile utilizzare l'istruzione CREATE DATABASE per impostare l'opzione di concatenamento della proprietà tra database per il nuovo database.</span><span class="sxs-lookup"><span data-stu-id="7bb81-108">If you are creating a new database, you can set the cross-database ownership chaining option for the new database using the CREATE DATABASE statement.</span></span>  
  
     <span data-ttu-id="7bb81-109">È consigliabile non impostare l'opzione **cross db ownership chaining** su 1, a meno che tutti i database ospitati dall'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non debbano essere inclusi nel concatenamento della proprietà tra database e si sia consapevoli delle implicazioni di questa impostazione in termini di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7bb81-109">Setting **cross db ownership chaining** to 1 is not recommended unless all of the databases hosted by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must participate in cross-database ownership chaining and you are aware of the security implications of this setting.</span></span>  
  
## <a name="controlling-cross-database-ownership-chaining"></a><span data-ttu-id="7bb81-110">Controllo del concatenamento della proprietà tra database</span><span class="sxs-lookup"><span data-stu-id="7bb81-110">Controlling Cross-Database Ownership Chaining</span></span>  
 <span data-ttu-id="7bb81-111">Prima di attivare o disattivare il concatenamento della proprietà tra database, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7bb81-111">Before turning cross-database ownership chaining on or off, consider the following:</span></span>  
  
-   <span data-ttu-id="7bb81-112">È necessario essere membri del ruolo predefinito del server **sysadmin** per attivare o disattivare il concatenamento della proprietà tra database.</span><span class="sxs-lookup"><span data-stu-id="7bb81-112">You must be a member of the **sysadmin** fixed server role to turn cross-database ownership chaining on or off.</span></span>  
  
-   <span data-ttu-id="7bb81-113">Prima di attivare o disattivare il concatenamento della proprietà tra database su un server di produzione, eseguire il test completo di tutte le applicazioni, incluse quelle di terze parti, per assicurare che le modifiche non influiscano sulla funzionalità delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7bb81-113">Before turning off cross-database ownership chaining on a production server, fully test all applications, including third-party applications, to ensure that the changes do not affect application functionality.</span></span>  
  
-   <span data-ttu-id="7bb81-114">Specificare RECONFIGURE con **sp_configure** per modificare l'opzione **cross db ownership chaining**mentre il server è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7bb81-114">You can change the **cross db ownership chaining** option while the server is running if you specify RECONFIGURE with **sp_configure**.</span></span>  
  
-   <span data-ttu-id="7bb81-115">Se sono presenti database per i quali è necessario attivare il concatenamento della proprietà tra database, è consigliabile disattivare l'opzione **cross db ownership chaining** per l'istanza usando **sp_configure**. Usare quindi l'istruzione ALTER DATABASE per attivare il concatenamento della proprietà tra database per i singoli database.</span><span class="sxs-lookup"><span data-stu-id="7bb81-115">If you have databases that require cross-database ownership chaining, the recommended practice is to turn off the **cross db ownership chaining** option for the instance using **sp_configure**; then turn on cross-database ownership chaining for individual databases that require it using the ALTER DATABASE statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb81-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bb81-116">See Also</span></span>  
 <span data-ttu-id="7bb81-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7bb81-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="7bb81-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7bb81-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="7bb81-119">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7bb81-119">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7bb81-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7bb81-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="7bb81-121">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7bb81-121">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
