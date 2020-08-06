---
title: Credenziali (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: faa2b5be7cf6918b5d5232763a96ed4dbbc89e51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635988"
---
# <a name="credentials-database-engine"></a><span data-ttu-id="cd8fe-102">Credenziali (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="cd8fe-102">Credentials (Database Engine)</span></span>
  <span data-ttu-id="cd8fe-103">Una credenziale è un record contenente le informazioni di autenticazione (credenziali) necessarie per connettersi a una risorsa all'esterno di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd8fe-103">A credential is a record that contains the authentication information (credentials) required to connect to a resource outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cd8fe-104">Queste informazioni vengono utilizzate internamente da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd8fe-104">This information is used internally by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cd8fe-105">La maggior parte delle credenziali contiene un nome utente e una password di Windows.</span><span class="sxs-lookup"><span data-stu-id="cd8fe-105">Most credentials contain a Windows user name and password.</span></span>  
  
 <span data-ttu-id="cd8fe-106">Le informazioni archiviate in una credenziale consentono a un utente che ha eseguito la connessione a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tramite l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di accedere a risorse esterne all'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="cd8fe-106">The information stored in a credential enables a user who has connected to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by way of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to access resources outside the server instance.</span></span> <span data-ttu-id="cd8fe-107">Quando la risorsa esterna è Windows, l'utente viene autenticato come l'utente di Windows specificato nella credenziale.</span><span class="sxs-lookup"><span data-stu-id="cd8fe-107">When the external resource is Windows, the user is authenticated as the Windows user specified in the credential.</span></span> <span data-ttu-id="cd8fe-108">È possibile eseguire il mapping di una singola credenziale a più account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="cd8fe-108">A single credential can be mapped to multiple [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="cd8fe-109">tuttavia, per un account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è possibile eseguire il mapping a una sola credenziale.</span><span class="sxs-lookup"><span data-stu-id="cd8fe-109">However, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can be mapped to only one credential.</span></span>  
  
 <span data-ttu-id="cd8fe-110">Le credenziali del sistema vengono create automaticamente e associate a endpoint specifici.</span><span class="sxs-lookup"><span data-stu-id="cd8fe-110">System credentials are created automatically and are associated with specific endpoints.</span></span> <span data-ttu-id="cd8fe-111">I nomi delle credenziali di sistema iniziano con due segni di cancelletto (##).</span><span class="sxs-lookup"><span data-stu-id="cd8fe-111">Names for system credentials start with two hash signs (##).</span></span>  
  
 <span data-ttu-id="cd8fe-112">Per ulteriori informazioni sulle credenziali, vedere la vista del catalogo [sys. Credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="cd8fe-112">For more information about credentials, see the [sys.credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) catalog view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="cd8fe-113">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="cd8fe-113">Related Content</span></span>  
 <span data-ttu-id="cd8fe-114">[Creazione di una credenziale](../authentication-access/create-a-credential.md) [create Credential &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="cd8fe-114">[Create a Credential](../authentication-access/create-a-credential.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span></span>  
  
 [<span data-ttu-id="cd8fe-115">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cd8fe-115">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
