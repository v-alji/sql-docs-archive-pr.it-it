---
title: Informazioni server Web | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627177"
---
# <a name="web-server-information"></a><span data-ttu-id="4a9cf-102">Informazioni server Web</span><span class="sxs-lookup"><span data-stu-id="4a9cf-102">Web Server Information</span></span>
  <span data-ttu-id="4a9cf-103">Le informazioni sul server Web sono necessarie per l'utilizzo dell'opzione relativa alla sincronizzazione Web per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="4a9cf-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="4a9cf-104">Per informazioni sulla configurazione della sincronizzazione Web, vedere [Configurare la sincronizzazione Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4a9cf-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4a9cf-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4a9cf-105">Options</span></span>  
 <span data-ttu-id="4a9cf-106">**Indirizzo server Web**</span><span class="sxs-lookup"><span data-stu-id="4a9cf-106">**Web server address**</span></span>  
 <span data-ttu-id="4a9cf-107">Se si è specificato l'indirizzo di un server Web nella pagina **Snapshot FTP e Internet** della finestra di dialogo **Proprietà pubblicazione**, tale indirizzo viene visualizzato in questa casella di testo per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4a9cf-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="4a9cf-108">È possibile accettare l'impostazione predefinita oppure immettere l'indirizzo di un server Web completo per il server [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) che esegue la sincronizzazione della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="4a9cf-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="4a9cf-109">**Indicare la modalità di connessione di ogni Sottoscrittore al server Web**</span><span class="sxs-lookup"><span data-stu-id="4a9cf-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="4a9cf-110">Consente di specificare il tipo di autenticazione utilizzato per la connessione al server Web.</span><span class="sxs-lookup"><span data-stu-id="4a9cf-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="4a9cf-111">È consigliabile utilizzare l'autenticazione di base per le connessioni al server IIS realizzate in combinazione con SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="4a9cf-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="4a9cf-112">Se si seleziona l'autenticazione di base, immettere l'account e la password che verranno utilizzati per la connessione dal Sottoscrittore al server IIS.</span><span class="sxs-lookup"><span data-stu-id="4a9cf-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9cf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a9cf-113">See Also</span></span>  
 <span data-ttu-id="4a9cf-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="4a9cf-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="4a9cf-115">[Visualizzare e modificare le proprietà delle sottoscrizioni pull](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4a9cf-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="4a9cf-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="4a9cf-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="4a9cf-117">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="4a9cf-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="4a9cf-118">Sincronizzazione Web per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="4a9cf-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
