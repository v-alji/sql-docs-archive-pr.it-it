---
title: Avviare Monitoraggio replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725507"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="68bd5-102">Avvio di Monitoraggio replica</span><span class="sxs-lookup"><span data-stu-id="68bd5-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="68bd5-103">È possibile avviare Monitoraggio replica da [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] in qualsiasi istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]oppure dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="68bd5-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="68bd5-104">Dopo l'avvio di Monitoraggio replica, aggiungere uno o più server di pubblicazione da monitorare.</span><span class="sxs-lookup"><span data-stu-id="68bd5-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="68bd5-105">Per altre informazioni, vedere [Aggiungere e rimuovere server di pubblicazione da Monitoraggio replica](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="68bd5-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="68bd5-106">Per avviare Monitoraggio replica da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68bd5-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="68bd5-107">Connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]e quindi espandere il nodo del server.</span><span class="sxs-lookup"><span data-stu-id="68bd5-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="68bd5-108">Fare clic con il pulsante destro del mouse sulla cartella **Replica** o una delle relative sottocartelle e quindi scegliere **Avvia Monitoraggio replica**.</span><span class="sxs-lookup"><span data-stu-id="68bd5-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="68bd5-109">Per avviare Monitoraggio replica dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="68bd5-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="68bd5-110">Al prompt dei comandi passare alla directory di installazione degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="68bd5-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="68bd5-111">Il percorso predefinito è [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span><span class="sxs-lookup"><span data-stu-id="68bd5-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="68bd5-112">Eseguire sqlmonitor.exe.</span><span class="sxs-lookup"><span data-stu-id="68bd5-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68bd5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68bd5-113">See Also</span></span>  
 [<span data-ttu-id="68bd5-114">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="68bd5-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
