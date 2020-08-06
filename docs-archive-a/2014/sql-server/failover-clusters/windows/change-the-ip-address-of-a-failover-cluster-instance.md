---
title: Modificare l'indirizzo IP di un'istanza del cluster di failover | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628279"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="3d0ea-102">Modifica dell'indirizzo IP di un'istanza del cluster di failover</span><span class="sxs-lookup"><span data-stu-id="3d0ea-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="3d0ea-103">In questo argomento viene descritto come modificare la risorsa indirizzo IP nell'istanza del cluster di failover (FCI) di AlwaysOn tramite lo snap-in Gestione cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="3d0ea-104">Lo snap-in Gestione cluster di failover è l'applicazione di gestione cluster per il servizio Windows Server Failover Clustering (WSFC).</span><span class="sxs-lookup"><span data-stu-id="3d0ea-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="3d0ea-105">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="3d0ea-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d0ea-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3d0ea-106">Before You Begin</span></span>  
 <span data-ttu-id="3d0ea-107">Prima di iniziare, esaminare il seguente argomento della documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : [Operazioni preliminari all'installazione del clustering di failover](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="3d0ea-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3d0ea-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3d0ea-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d0ea-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3d0ea-109">Permissions</span></span>  
 <span data-ttu-id="3d0ea-110">Per eseguire la manutenzione o l'aggiornamento di un'istanza FCI, è necessario essere un amministratore locale che dispone dell'account per accedere come servizio su tutti i nodi dell'istanza FCI.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="3d0ea-111">Utilizzo dello snap-in Gestione cluster di failover</span><span class="sxs-lookup"><span data-stu-id="3d0ea-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="3d0ea-112">**Per modificare la risorsa indirizzo IP per un'istanza FCI**</span><span class="sxs-lookup"><span data-stu-id="3d0ea-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="3d0ea-113">Aprire lo snap-in Gestione cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="3d0ea-114">Espandere il nodo **Servizi e applicazioni** nel riquadro sinistro e fare clic sull'istanza FCI.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="3d0ea-115">Nel riquadro a destra, nella categoria **Nome server** , fare clic con il pulsante destro del mouse sul'istanza di SQL Server e scegliere **Proprietà** per aprire la finestra di dialogo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3d0ea-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="3d0ea-116">Nella scheda **Generale** , modificare la risorsa indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="3d0ea-117">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="3d0ea-118">Nel riquadro destro fare clic con il pulsante destro del mouse su SQL IP Address1(nome dell'istanza del cluster di failover) e scegliere **Offline**.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="3d0ea-119">Lo stato di SQL IP Address1(nome dell'istanza del cluster di failover), di SQL Network Name(nome dell'istanza del cluster di failover) e di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] passerà da Online a Sospensione offline e quindi a Offline.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="3d0ea-120">Nel riquadro destro fare clic con il pulsante destro del mouse su [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]e scegliere **Online**.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="3d0ea-121">Lo stato di SQL IP Address1(nome dell'istanza del cluster di failover), di SQL Network Name(nome dell'istanza del cluster di failover) e di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] passerà da Offline a Sospensione online e quindi a Online.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="3d0ea-122">Chiudere lo snap-in Gestione cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="3d0ea-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
