---
title: Considerazioni per l'esecuzione di set di raccolta di utilità e non di utilità nella stessa istanza di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629817"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="169a1-102">Considerazioni per l'esecuzione di set di raccolta dell'utilità e non appartenenti all'utilità nella stessa istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="169a1-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="169a1-103">L'esecuzione side-by-side del set di raccolta di Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e dei set di raccolta non appartenenti a Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è supportata.</span><span class="sxs-lookup"><span data-stu-id="169a1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="169a1-104">Ciò significa che un'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere monitorata da altri set di raccolta anche se l'istanza è membro di un'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="169a1-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="169a1-105">È tuttavia necessario disabilitare la funzionalità della raccolta dati non appartenente all'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mentre l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene registrata nell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="169a1-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="169a1-106">Dopo la registrazione dell'istanza con il punto di controllo dell'utilità, è possibile riavviare i set di raccolta non appartenenti dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="169a1-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="169a1-107">Tuttavia, tutti i set di raccolta sull'istanza gestita caricheranno i propri dati nel data warehouse di gestione dell'utilità (UMDW); il nome del file UMDW è sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="169a1-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="169a1-108">Per eseguire side-by-side i set di raccolta dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e i set di raccolta non appartenenti all'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="169a1-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="169a1-109">L'esecuzione side-by-side dei set di raccolta è supportata.</span><span class="sxs-lookup"><span data-stu-id="169a1-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="169a1-110">È necessario disabilitare gli agenti di raccolta dati esistenti mentre si registrano le istanze nell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="169a1-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="169a1-111">Per soddisfare i requisiti della convalida, è necessario eseguire le stored procedure seguenti sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima di creare un punto di controllo dell'utilità e su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima di registrarla nell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="169a1-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="169a1-112">Se non si eseguono queste stored procedure prima di avviare la procedura guidata Crea punto di controllo dell'utilità o Aggiungi istanza gestita, l'operazione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="169a1-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="169a1-113">È necessario utilizzare il data warehouse di gestione (sysutility_mdw) dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per tutti i set di raccolta su un'istanza gestita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="169a1-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169a1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="169a1-114">See Also</span></span>  
 <span data-ttu-id="169a1-115">[Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="169a1-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="169a1-116">Configurare il data warehouse del punto di controllo dell'utilità &#40;Utilità SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="169a1-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
