---
title: Connetti al server (Oracle), Account di accesso| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624078"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="fc7cc-102">Connetti al server (Oracle), Account di accesso</span><span class="sxs-lookup"><span data-stu-id="fc7cc-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="fc7cc-103">Usare la scheda **Account di accesso** della finestra di dialogo **Connetti al server** per specificare l'account con cui vengono stabilite le connessioni dal server di distribuzione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al server di pubblicazione Oracle.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="fc7cc-104">È necessario utilizzare lo stesso account specificato per lo schema utente di amministrazione della replica durante la configurazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="fc7cc-105">Per altre informazioni, vedere [Configurare un server di pubblicazione Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="fc7cc-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fc7cc-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fc7cc-106">Options</span></span>  
 <span data-ttu-id="fc7cc-107">**Istanza del server**</span><span class="sxs-lookup"><span data-stu-id="fc7cc-107">**Server instance**</span></span>  
 <span data-ttu-id="fc7cc-108">Transparent Network Substrate del server di pubblicazione Oracle specificato durante la configurazione del software client Oracle installato nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="fc7cc-109">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="fc7cc-109">**Authentication**</span></span>  
 <span data-ttu-id="fc7cc-110">Consente di selezionare l' **Autenticazione standard Oracle** (scelta consigliata) oppure l' **Autenticazione di Windows**.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="fc7cc-111">Se si seleziona l' **Autenticazione di Windows**:</span><span class="sxs-lookup"><span data-stu-id="fc7cc-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="fc7cc-112">Il server Oracle deve essere configurato in modo da consentire le connessioni con le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="fc7cc-113">Per ulteriori informazioni, vedere la documentazione di Oracle.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="fc7cc-114">È necessario eseguire l'accesso con lo stesso account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows specificato per lo schema utente di amministrazione della replica.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="fc7cc-115">**Account di accesso** e **Password**</span><span class="sxs-lookup"><span data-stu-id="fc7cc-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="fc7cc-116">Se è stata selezionata l' **Autenticazione standard Oracle** per l'opzione **Autenticazione** , specificare l'account di accesso e la password da utilizzare, che devono corrispondere all'account di accesso e alla password specificati per lo schema utente di amministrazione della replica.</span><span class="sxs-lookup"><span data-stu-id="fc7cc-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7cc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc7cc-117">See Also</span></span>  
 [<span data-ttu-id="fc7cc-118">Glossario dei termini per la pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="fc7cc-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
