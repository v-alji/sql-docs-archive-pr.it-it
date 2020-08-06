---
title: Installare la replica di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ba941fda1d463e7bb4a26bd2fbb45d2a82ca27b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713440"
---
# <a name="install-sql-server-replication"></a><span data-ttu-id="a2c7f-102">Installare la replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2c7f-102">Install SQL Server Replication</span></span>
  <span data-ttu-id="a2c7f-103">I componenti della replica possono essere installati mediante l'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a2c7f-103">Replication components can be installed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or at a command prompt.</span></span> <span data-ttu-id="a2c7f-104">L'installazione della replica può essere eseguita durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]oppure durante la modifica di un'istanza esistente.</span><span class="sxs-lookup"><span data-stu-id="a2c7f-104">Install replication when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or when you modify an existing instance.</span></span>  
  
 <span data-ttu-id="a2c7f-105">Dopo aver installato i componenti della replica, è necessario configurare il server per poter utilizzare la replica.</span><span class="sxs-lookup"><span data-stu-id="a2c7f-105">After replication components are installed, you must configure the server before you can use replication.</span></span> <span data-ttu-id="a2c7f-106">Per altre informazioni, vedere [Configura distribuzione](../../relational-databases/replication/configure-distribution.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a2c7f-106">For more information, see [Configure Distribution](../../relational-databases/replication/configure-distribution.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a2c7f-107">Se si installano componenti di replica quando si modifica un'istanza esistente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent al termine dell'installazione,</span><span class="sxs-lookup"><span data-stu-id="a2c7f-107">If you install replication components when you modify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent after the installation is completed.</span></span> <span data-ttu-id="a2c7f-108">per fare in modo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent riconosca i sottosistemi dell'agente di replica e sia in grado di chiamare gli agenti di replica dai passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="a2c7f-108">This action helps ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recognizes the replication agent subsystems and can call replication agents from job steps.</span></span>  
  
## <a name="installing-replication-by-using-setup"></a><span data-ttu-id="a2c7f-109">Installazione della replica mediante l'utilizzo del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="a2c7f-109">Installing Replication by Using Setup</span></span>  
 <span data-ttu-id="a2c7f-110">**Per installare la replica durante l'installazione di una nuova istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a2c7f-110">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="a2c7f-111">Per installare i componenti della replica, inclusi gli oggetti RMO (Replication Management Objects), selezionare **Replica di SQL Server** nella pagina **Selezione funzionalità** dell'Installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="a2c7f-111">To install replication components, including Replication Management Objects (RMO), select **SQL Server Replication** on the **Feature Selection** page of the Installation Wizard.</span></span>  
  
## <a name="installing-replication-from-the-command-prompt"></a><span data-ttu-id="a2c7f-112">Installazione della replica dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="a2c7f-112">Installing Replication from the Command Prompt</span></span>  
 <span data-ttu-id="a2c7f-113">**Per installare la replica durante l'installazione di una nuova istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a2c7f-113">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="a2c7f-114">Vedere [Install SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="a2c7f-114">See [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c7f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2c7f-115">See Also</span></span>  
 <span data-ttu-id="a2c7f-116">[Installare SQL Server 2014](install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a2c7f-116">[Install SQL Server 2014](install-sql-server.md) </span></span>  
 <span data-ttu-id="a2c7f-117">[Installare SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="a2c7f-117">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 [<span data-ttu-id="a2c7f-118">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a2c7f-118">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
