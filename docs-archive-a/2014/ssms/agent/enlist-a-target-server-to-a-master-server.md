---
title: Integrare un server di destinazione in un server master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623723"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="3a638-102">Integrare un server di destinazione in un server master</span><span class="sxs-lookup"><span data-stu-id="3a638-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="3a638-103">In questo argomento viene illustrata la procedura per l'aggiunta di server di destinazione a una configurazione di amministrazione multiserver.</span><span class="sxs-lookup"><span data-stu-id="3a638-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="3a638-104">Eseguire questa procedura dal server master.</span><span class="sxs-lookup"><span data-stu-id="3a638-104">Run this procedure from the master server.</span></span> <span data-ttu-id="3a638-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]o SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="3a638-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="3a638-106">Per informazioni sugli effetti dell'uso dell'account di Windows per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent su un ambiente multiserver, vedere [Creazione di un ambiente multiserver](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3a638-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="3a638-107">Per impostazione predefinita, per le connessioni tra server master e server di destinazione sono attive la crittografia SSL (Secure Sockets Layer) completa e la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="3a638-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="3a638-108">Per altre informazioni, vedere [Impostazione delle opzioni di crittografia nei server di destinazione](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3a638-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="3a638-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3a638-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3a638-110">**Per integrare un server di destinazione tramite:**</span><span class="sxs-lookup"><span data-stu-id="3a638-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="3a638-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a638-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3a638-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a638-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="3a638-113">SMO</span><span class="sxs-lookup"><span data-stu-id="3a638-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3a638-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a638-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="3a638-115">Per integrare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="3a638-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="3a638-116">In **Esplora oggetti**espandere un server configurato come server master.</span><span class="sxs-lookup"><span data-stu-id="3a638-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="3a638-117">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Aggiungi server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="3a638-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="3a638-118">In Configurazione guidata server di destinazione, eseguire i passaggi necessari per completare la procedura.</span><span class="sxs-lookup"><span data-stu-id="3a638-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3a638-119">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3a638-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="3a638-120">Per integrare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="3a638-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="3a638-121">Utilizzare la stored procedure `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="3a638-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="3a638-122">Per ulteriori informazioni, vedere [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="3a638-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="3a638-123">Utilizzo di SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="3a638-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a638-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a638-124">See Also</span></span>  
 [<span data-ttu-id="3a638-125">Amministrazione automatizzata in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3a638-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
