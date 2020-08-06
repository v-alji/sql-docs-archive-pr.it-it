---
title: Proprietà - Configurazione SQL Server Native Client (scheda Flag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636963"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="d678c-102">Proprietà - Configurazione SQL Server Native Client (scheda Flag)</span><span class="sxs-lookup"><span data-stu-id="d678c-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  <span data-ttu-id="d678c-103">I client [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in questo computer comunicano con i server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite i protocolli disponibili nel file della libreria di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d678c-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="d678c-104">Questa scheda consente di configurare il computer client in modo che richieda una connessione crittografata mediante SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="d678c-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="d678c-105">Se non è possibile ottenere una connessione crittografata, la connessione non viene stabilita.</span><span class="sxs-lookup"><span data-stu-id="d678c-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="d678c-106">Il processo di accesso viene sempre crittografato.</span><span class="sxs-lookup"><span data-stu-id="d678c-106">The login process is always encrypted.</span></span> <span data-ttu-id="d678c-107">Le opzioni riportate di seguito si applicano solo a dati crittografati.</span><span class="sxs-lookup"><span data-stu-id="d678c-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="d678c-108">Per altre informazioni sulla crittografia della comunicazione da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e per istruzioni sulla configurazione del client affinché consideri attendibile l'autorità radice del certificato del server, vedere "Crittografia delle connessioni a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" e "Procedura: Attivazione di connessioni crittografate al [!INCLUDE[ssDE](../../includes/ssde-md.md)] (Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)])" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d678c-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d678c-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d678c-109">Options</span></span>  
 <span data-ttu-id="d678c-110">**ForceEncryption**</span><span class="sxs-lookup"><span data-stu-id="d678c-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="d678c-111">Richiede una connessione mediante SSL.</span><span class="sxs-lookup"><span data-stu-id="d678c-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="d678c-112">**TrustServerCertificate**</span><span class="sxs-lookup"><span data-stu-id="d678c-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="d678c-113">Se è impostato su **No**, il processo client tenta di convalidare il certificato server.</span><span class="sxs-lookup"><span data-stu-id="d678c-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="d678c-114">Sia il client che il server devono disporre di un certificato emesso da un'autorità di certificazione pubblica.</span><span class="sxs-lookup"><span data-stu-id="d678c-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="d678c-115">Se il certificato non è presente nel computer client o se non viene convalidato, la connessione viene terminata.</span><span class="sxs-lookup"><span data-stu-id="d678c-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="d678c-116">Se è impostato su **Sì**, il client non convalida il certificato server e pertanto consente di usare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="d678c-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="d678c-117">**Certificato server attendibile** è disponibile solo se **Forza crittografia protocollo** è impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d678c-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
