---
title: Proprietà Sottoscrittore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724484"
---
# <a name="subscriber-properties"></a><span data-ttu-id="1f65d-102">Proprietà Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="1f65d-102">Subscriber Properties</span></span>
  <span data-ttu-id="1f65d-103">La finestra di dialogo **Proprietà Sottoscrittore** contiene informazioni relative ai Sottoscrittori che eseguono versioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f65d-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f65d-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1f65d-104">Options</span></span>  
 <span data-ttu-id="1f65d-105">**Connessione dell'agente al Sottoscrittore**</span><span class="sxs-lookup"><span data-stu-id="1f65d-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="1f65d-106">Contesto nel quale l'agente di distribuzione e l'agente di merge eseguono la connessione dal server di distribuzione al Sottoscrittore. Questa opzione riguarda solo le versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f65d-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="1f65d-107">Selezionare **Rappresenta l'account del processo dell'agente** per eseguire connessioni al Sottoscrittore utilizzando il contesto dell'account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nel server di distribuzione oppure specificare **Autenticazione di SQL Server**e quindi immettere un valore per **Nome account di accesso** e **Password**.</span><span class="sxs-lookup"><span data-stu-id="1f65d-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="1f65d-108">consiglia di selezionare **Rappresenta l'account del processo dell'agente**.</span><span class="sxs-lookup"><span data-stu-id="1f65d-108">recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="1f65d-109">Per [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive le informazioni sulla connessione vengono specificate per ogni sottoscrizione nella Creazione guidata nuova sottoscrizione e possono essere modificate nella finestra di dialogo **Proprietà sottoscrizione** .</span><span class="sxs-lookup"><span data-stu-id="1f65d-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="1f65d-110">**Pianificazioni agenti predefinite**</span><span class="sxs-lookup"><span data-stu-id="1f65d-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="1f65d-111">Pianificazione predefinita utilizzata nella Creazione guidata nuova sottoscrizione per i Sottoscrittori che eseguono versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f65d-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="1f65d-112">**Varie**</span><span class="sxs-lookup"><span data-stu-id="1f65d-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="1f65d-113">Include informazioni sul Sottoscrittore e sul tipo di Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1f65d-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f65d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f65d-114">See Also</span></span>  
 [<span data-ttu-id="1f65d-115">Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="1f65d-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="1f65d-116">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="1f65d-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
