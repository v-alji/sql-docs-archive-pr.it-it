---
title: Server di pubblicazione Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624056"
---
# <a name="oracle-publisher"></a><span data-ttu-id="1bee6-102">Server di pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="1bee6-102">Oracle Publisher</span></span>
  <span data-ttu-id="1bee6-103">A partire da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di pubblicare i dati di un database Oracle tramite la replica transazionale o snapshot.</span><span class="sxs-lookup"><span data-stu-id="1bee6-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="1bee6-104">Per altre informazioni, vedere [Panoramica della pubblicazione Oracle](non-sql/oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1bee6-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="1bee6-105">Il server di pubblicazione Oracle deve utilizzare un server di distribuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] remoto nel quale deve essere eseguita la procedura guidata dopo che il software di rete Oracle necessario è stato installato e testato.</span><span class="sxs-lookup"><span data-stu-id="1bee6-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="1bee6-106">Per altre informazioni, vedere [Configurare un server di pubblicazione Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="1bee6-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1bee6-107">Se un altro amministratore ha configurato il database Oracle come database di pubblicazione, dopo aver fatto clic su **Avanti** verrà richiesto di digitare la password per l'accesso alla replica utilizzata per connettersi al database Oracle.</span><span class="sxs-lookup"><span data-stu-id="1bee6-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> <span data-ttu-id="1bee6-108">In[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verrà quindi definito il mapping tra l'account di accesso utilizzato e la connessione del server collegato al database Oracle.</span><span class="sxs-lookup"><span data-stu-id="1bee6-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="1bee6-109">Non sarà più necessario digitare la password per le connessioni successive al database Oracle.</span><span class="sxs-lookup"><span data-stu-id="1bee6-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1bee6-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1bee6-110">Options</span></span>  
 <span data-ttu-id="1bee6-111">**Server di pubblicazione Oracle**</span><span class="sxs-lookup"><span data-stu-id="1bee6-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="1bee6-112">Consente di selezionare un server di pubblicazione Oracle nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1bee6-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="1bee6-113">Nell'elenco sono inclusi i server di pubblicazione Oracle precedentemente configurati per l'utilizzo del server su cui viene eseguita la procedura guidata come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1bee6-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="1bee6-114">Se l'elenco è vuoto oppure il server di pubblicazione Oracle desiderato non è presente, fare clic su **Aggiungi server di pubblicazione Oracle**.</span><span class="sxs-lookup"><span data-stu-id="1bee6-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="1bee6-115">**Aggiungi server di pubblicazione Oracle**</span><span class="sxs-lookup"><span data-stu-id="1bee6-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="1bee6-116">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="1bee6-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="1bee6-117">In questa finestra di dialogo fare clic su **Aggiungi**e quindi su **Aggiungi server di pubblicazione Oracle**.</span><span class="sxs-lookup"><span data-stu-id="1bee6-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="1bee6-118">Nella finestra di dialogo **Connetti al server** specificare il nome del server Oracle, nonché l'account di accesso e la password per lo schema utente di amministrazione della replica.</span><span class="sxs-lookup"><span data-stu-id="1bee6-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="1bee6-119">Per altre informazioni, vedere [Connetti al server &#40;Oracle&#41;, Account di accesso](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="1bee6-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bee6-120">Se il server su cui viene eseguita la procedura guidata non è stato ancora configurato come server di distribuzione, viene richiesto di eseguire la configurazione adesso.</span><span class="sxs-lookup"><span data-stu-id="1bee6-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bee6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bee6-121">See Also</span></span>  
 [<span data-ttu-id="1bee6-122">Creare una pubblicazione da un database Oracle</span><span class="sxs-lookup"><span data-stu-id="1bee6-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
