---
title: Eseguire Windows PowerShell da SQL Server Management Studio| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627856"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="f60a7-102">Esecuzione di Windows PowerShell da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f60a7-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="f60a7-103">È possibile avviare sessioni di Windows PowerShell da **Esplora oggetti** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f60a7-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="f60a7-104">avvia Windows PowerShell, carica il `sqlps` modulo e imposta il contesto del percorso sul nodo associato nell'albero **Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="f60a7-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f60a7-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f60a7-105">Before You Begin</span></span>  
 <span data-ttu-id="f60a7-106">Quando si specifica l'esecuzione di PowerShell per un oggetto in **Esplora oggetti**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Avvia una sessione di Windows PowerShell in cui [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sono stati caricati e registrati gli snap-in di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f60a7-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="f60a7-107">Il percorso della sessione è preimpostato sulla posizione dell'oggetto su cui si è fatto clic con il pulsante destro del mouse in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="f60a7-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="f60a7-108">Ad esempio, facendo clic con il pulsante destro del mouse sull'oggetto del database [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] in Esplora oggetti e selezionando **Avvia PowerShell**, il percorso di PowerShell viene impostato come segue:</span><span class="sxs-lookup"><span data-stu-id="f60a7-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="f60a7-109">Per eseguire PowerShell da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f60a7-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="f60a7-110">Aprire **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="f60a7-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="f60a7-111">Passare al nodo corrispondente all'oggetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="f60a7-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="f60a7-112">Fare clic con il pulsante destro del mouse sull'oggetto e selezionare **Avvia PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f60a7-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="f60a7-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f60a7-113">Permissions</span></span>  
 <span data-ttu-id="f60a7-114">In caso di apertura da [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell non viene eseguito con privilegi di amministratore che possono impedire alcune attività quali chiamate a WMI.</span><span class="sxs-lookup"><span data-stu-id="f60a7-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60a7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f60a7-115">See Also</span></span>  
 [<span data-ttu-id="f60a7-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f60a7-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
