---
title: Servizio Change Data Capture per Oracle di Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629567"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="3abc5-102">Servizio Change Data Capture per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="3abc5-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="3abc5-103">Il servizio CDC per Oracle è un servizio Windows tramite cui vengono analizzati i log delle transazioni Oracle e acquisite le modifiche apportate alle tabelle Oracle di interesse nelle tabelle delle modifiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3abc5-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="3abc5-104">Le tabelle delle modifiche SQL in cui vengono archiviate le modifiche acquisite da Oracle sono dello stesso tipo delle tabelle delle modifiche usate nella funzionalità Change Data Capture nativa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3abc5-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="3abc5-105">In questo modo l'utilizzo delle modifiche è facile quanto l'utilizzo delle modifiche apportate ai database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3abc5-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="3abc5-106">Installazione</span><span class="sxs-lookup"><span data-stu-id="3abc5-106">Installation</span></span>  
 <span data-ttu-id="3abc5-107">È possibile installare il servizio CDC per Oracle in qualsiasi computer Windows supportato con accesso al o ai database Oracle di origine che vengono acquisiti e all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione in cui si trova il database CDC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3abc5-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="3abc5-108">Per il servizio CDC non è necessaria un'installazione locale del database Oracle o del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma solo dei relativi client supportati.</span><span class="sxs-lookup"><span data-stu-id="3abc5-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="3abc5-109">Per altre informazioni sul percorso di installazione dei componenti di database richiesti, vedere **Prerequisiti del database** in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3abc5-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="3abc5-110">Con l'installazione del servizio CDC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per Oracle l'interfaccia utente della configurazione del servizio e il programma del servizio vengono posizionati nel percorso selezionato.</span><span class="sxs-lookup"><span data-stu-id="3abc5-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="3abc5-111">Il servizio CDC per Oracle viene configurato separatamente tramite Oracle CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="3abc5-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="3abc5-112">Per altre informazioni sulla configurazione del servizio Oracle CDC, vedere [Guida del servizio Change Data Capture per Oracle di Attunity](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="3abc5-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="3abc5-113">Per installare il servizio CDC per Oracle, eseguire manualmente **AttunityOracleCdcService.msi** dal supporto di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3abc5-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="3abc5-114">I pacchetti di installazione per x86 e x64 si trovano in \*\*.\Tools\AttunityCDCOracle \\ \*\* sul supporto di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3abc5-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="3abc5-115">È possibile installare il servizio CDC per Oracle in qualsiasi computer Windows supportato in cui sia installato il client nativo di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ; non è necessario che sia installato nello stesso computer in cui si trova l'istanza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3abc5-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="3abc5-116">Ambienti Windows supportati</span><span class="sxs-lookup"><span data-stu-id="3abc5-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="3abc5-117">È possibile eseguire il servizio Change Data Capture per Oracle di Attunity negli ambienti Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="3abc5-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="3abc5-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="3abc5-118">Windows 8</span></span>  
  
-   <span data-ttu-id="3abc5-119">Windows 7 a 32 bit (x86) e a 64 bit (x64)</span><span class="sxs-lookup"><span data-stu-id="3abc5-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="3abc5-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3abc5-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="3abc5-121">Windows Server 2008 R2 con Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="3abc5-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="3abc5-122">Windows Server 2008 a 32 bit (x86) e a 64 bit (x64) con Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="3abc5-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="3abc5-123">Prerequisiti del database</span><span class="sxs-lookup"><span data-stu-id="3abc5-123">Database Prerequisites</span></span>  
 <span data-ttu-id="3abc5-124">Per usare il servizio CDC per Oracle, è necessario installare il software Oracle [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="3abc5-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="3abc5-125">Si tratta di un prerequisito che è necessario ottenere da Oracle e installare prima dell'installazione del servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="3abc5-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="3abc5-126">Inoltre, è necessario installare il client ODBC di SQL Server usando il programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3abc5-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="3abc5-127">Il servizio CDC per Oracle supporta le versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3abc5-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="3abc5-128">Database Oracle di origine</span><span class="sxs-lookup"><span data-stu-id="3abc5-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="3abc5-129">Oracle Database 11x, qualsiasi versione</span><span class="sxs-lookup"><span data-stu-id="3abc5-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="3abc5-130">Oracle Database 10x, qualsiasi versione</span><span class="sxs-lookup"><span data-stu-id="3abc5-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="3abc5-131">Database di SQL Server di destinazione</span><span class="sxs-lookup"><span data-stu-id="3abc5-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="3abc5-132">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3abc5-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="3abc5-133">Esecuzione del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="3abc5-133">Running the Installation Program</span></span>  
 <span data-ttu-id="3abc5-134">Per installare il servizio CDC per Oracle, aprire l'Installazione guidata per la piattaforma Windows in uso (32/64 bit) e attenersi alle indicazioni visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="3abc5-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="3abc5-135">Disinstallazione del servizio Change Data Capture per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="3abc5-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="3abc5-136">Per disinstallare il servizio CDC per Oracle, scegliere Pannello di controllo, Programmi e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3abc5-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="3abc5-137">Con la disinstallazione del servizio CDC, non vengono eliminati i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creati.</span><span class="sxs-lookup"><span data-stu-id="3abc5-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="3abc5-138">Per la rimozione completa dello strumento, è necessario rimuovere il database MSXDBCDC e i database CDC specifici creati nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di destinazione usata.</span><span class="sxs-lookup"><span data-stu-id="3abc5-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="3abc5-139">Se si disinstalla il software del servizio CDC da un computer e lo si installa in un altro computer, è sufficiente fornire le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3abc5-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="3abc5-140">Account di servizio</span><span class="sxs-lookup"><span data-stu-id="3abc5-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3abc5-141">- Stringa di connessione e credenziali</span><span class="sxs-lookup"><span data-stu-id="3abc5-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="3abc5-142">Master password</span><span class="sxs-lookup"><span data-stu-id="3abc5-142">The master password</span></span>  
  
 <span data-ttu-id="3abc5-143">Tutte le altre definizioni vengono archiviate in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e sono disponibile dall'installazione precedente in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="3abc5-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="3abc5-144">Contenuto della documentazione</span><span class="sxs-lookup"><span data-stu-id="3abc5-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="3abc5-145">Architettura di sistema del servizio Change Data Capture per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="3abc5-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="3abc5-146">Servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="3abc5-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="3abc5-147">Guida del servizio Change Data Capture per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="3abc5-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="3abc5-148">Guida procedurale del servizio Change Data Capture per Oracle di Attunity</span><span class="sxs-lookup"><span data-stu-id="3abc5-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="3abc5-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abc5-149">See Also</span></span>  
 [<span data-ttu-id="3abc5-150">Utilizzo del servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="3abc5-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  
