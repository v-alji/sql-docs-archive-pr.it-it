---
title: Creazione di un endpoint del mirroring del database per Gruppi di disponibilità AlwaysOn (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727112"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="6901b-102">Creare un endpoint del mirroring del database per i gruppi di disponibilità AlwaysOn (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="6901b-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="6901b-103">In questo argomento viene illustrato come creare un endpoint del mirroring del database che verrà utilizzato da [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6901b-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="6901b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6901b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6901b-105">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="6901b-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6901b-106">**Per creare un endpoint del mirroring del database tramite:**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="6901b-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6901b-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6901b-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6901b-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6901b-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6901b-109">L'algoritmo RC4 è deprecato.</span><span class="sxs-lookup"><span data-stu-id="6901b-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6901b-110">È consigliabile utilizzare AES.</span><span class="sxs-lookup"><span data-stu-id="6901b-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6901b-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6901b-111">Permissions</span></span>  
 <span data-ttu-id="6901b-112">È richiesta l'autorizzazione CREATE ENDPOINT o l'appartenenza al ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="6901b-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="6901b-113">Per altre informazioni, vedere [GRANT - autorizzazioni per endpoint &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6901b-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="6901b-114">Uso di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6901b-114">Using PowerShell</span></span>  
 <span data-ttu-id="6901b-115">**Per creare un endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="6901b-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="6901b-116">Spostarsi sulla directory (`cd`) dell'istanza del server per la quale creare l'endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="6901b-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="6901b-117">Utilizzare il cmdlet `New-SqlHadrEndpoint` per creare l'endpoint, quindi utilizzare `Set-SqlHadrEndpoint` per avviare l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="6901b-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="6901b-118">Esempio (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="6901b-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="6901b-119">I comandi di PowerShell seguenti creano un endpoint del mirroring del database in un'istanza di SQL Server (istanza del*computer* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="6901b-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="6901b-120">L'endpoint utilizza la porta 5022.</span><span class="sxs-lookup"><span data-stu-id="6901b-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6901b-121">Questo esempio funziona solo su un'istanza del server che attualmente non dispone di un endpoint del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="6901b-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6901b-122">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="6901b-122">Related Tasks</span></span>  
 <span data-ttu-id="6901b-123">**Per configurare un endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="6901b-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="6901b-124">Creare un endpoint del mirroring del database per l'autenticazione Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="6901b-125">Utilizzare certificati per un endpoint del mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="6901b-126">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in uscita &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="6901b-127">Impostazione dell'endpoint del mirroring del database per l'utilizzo di certificati per le connessioni in ingresso &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="6901b-128">Specificare un indirizzo di rete del server &#40;Mirroring del database&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="6901b-129">Specifica dell'URL dell'endpoint quando si aggiunge o si modifica una replica di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="6901b-130">**Per visualizzare informazioni sull'endpoint del mirroring del database**</span><span class="sxs-lookup"><span data-stu-id="6901b-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="6901b-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="6901b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6901b-132">See Also</span></span>  
 <span data-ttu-id="6901b-133">[Creare un gruppo di disponibilità &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="6901b-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="6901b-134">Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6901b-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
