---
title: Escludere più server di destinazione da un server master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715036"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="9615d-102">Escludere più server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="9615d-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="9615d-103">In questo argomento viene illustrata la procedura per l'esclusione di più server di destinazione da una configurazione di amministrazione multiserver in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9615d-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9615d-104">Eseguire questa procedura dal server master.</span><span class="sxs-lookup"><span data-stu-id="9615d-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9615d-105">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9615d-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="9615d-106">Per escludere più server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="9615d-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="9615d-107">In **Esplora oggetti**espandere un server configurato come server master.</span><span class="sxs-lookup"><span data-stu-id="9615d-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="9615d-108">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Gestione server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="9615d-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="9615d-109">Fare clic su **Invia istruzioni**e quindi selezionare **Escludi** nell'elenco **Tipo istruzione**.</span><span class="sxs-lookup"><span data-stu-id="9615d-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="9615d-110">In **Destinatari**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9615d-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="9615d-111">Fare clic su **Tutti i server di destinazione** per escludere tutti i server di destinazione di questo server master.</span><span class="sxs-lookup"><span data-stu-id="9615d-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="9615d-112">Questa opzione consente di disinstallare completamente l'attuale configurazione di amministrazione multiserver.</span><span class="sxs-lookup"><span data-stu-id="9615d-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="9615d-113">Fare clic su **Solo i server di destinazione seguenti**e quindi sulla casella **Seleziona** corrispondente per escludere solo alcuni server di destinazione di questo server master.</span><span class="sxs-lookup"><span data-stu-id="9615d-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9615d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9615d-114">See Also</span></span>  
 <span data-ttu-id="9615d-115">[Creazione di un ambiente multiserver](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="9615d-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="9615d-116">[Amministrazione automatizzata in un'organizzazione](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="9615d-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="9615d-117">Escludere un server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="9615d-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
