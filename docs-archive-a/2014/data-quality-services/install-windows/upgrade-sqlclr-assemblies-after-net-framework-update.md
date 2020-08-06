---
title: Aggiornare gli assembly SQLCLR dopo l'aggiornamento di .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629622"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="076c0-102">Aggiornare gli assembly SQLCLR dopo l'aggiornamento di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="076c0-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="076c0-103">(DQS) è una raccolta di routine SQLCR (SQL Common Language Runtime) che fanno riferimento agli assembly Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="076c0-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="076c0-104">Quando si installano aggiornamenti di .NET Framework nel computer che possono interessare un assembly .NET Framework di riferimento di questo tipo, tale operazione comporta una modifica nell'ID della versione del modulo (MVID, Module Version ID) dell'assembly nel Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="076c0-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="076c0-105">Questa modifica determina una mancata corrispondenza tra i MVID dell'assembly a cui si fa riferimento nella GAC e l'assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="076c0-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="076c0-106">Se per l'aggiornamento di .NET Framework viene richiesto il riavvio del computer di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , gli assembly SQLCLR interessati vengono aggiornati automaticamente per correggere il problema di mancata corrispondenza di MVID al riavvio di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="076c0-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="076c0-107">Per gli aggiornamenti di .NET Framework per cui non è richiesto il riavvio del computer di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , si verifica tuttavia un errore a causa della mancata corrispondenza nei MVID degli assembly quando si tenta di connettersi a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] tramite [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="076c0-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="076c0-108">Per correggere questo problema, è necessario aggiornare gli assembly SQLCLR interessati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="076c0-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="076c0-109">È possibile eseguire questa operazione eseguendo il file DQSInstaller.exe con il parametro della riga di comando **upgradedlls** per ignorare la ricreazione di database di DQS e aggiornare solo gli assembly interessati.</span><span class="sxs-lookup"><span data-stu-id="076c0-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="076c0-110">In questo modo viene garantita l'integrità della Knowledge Base, dei progetti Data Quality e di qualsiasi altro dato di DQS.</span><span class="sxs-lookup"><span data-stu-id="076c0-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="076c0-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="076c0-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="076c0-112">È necessario aver eseguito l'accesso come membro del gruppo di amministratori nel computer di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="076c0-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="076c0-113">È necessario che l'account utente di Windows sia membro del ruolo predefinito del server sysadmin nell'istanza di SQL Server in cui è installato [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="076c0-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="076c0-114">Per aggiornare gli assembly SQLCLR</span><span class="sxs-lookup"><span data-stu-id="076c0-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="076c0-115">Avviare il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="076c0-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="076c0-116">Al prompt dei comandi impostare la directory sul percorso in cui è disponibile il file DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="076c0-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="076c0-117">Se è stata installata l'istanza predefinita di SQL Server, il file DQSinstaller.exe sarà disponibile in C:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="076c0-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="076c0-118">Al prompt dei comandi digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="076c0-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="076c0-119">I passaggi rimanenti sono uguali ai passaggi 2-6 della sezione [Eseguire DQSInstaller.exe dalla schermata Start, dal menu Start o da Esplora risorse](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) in [Eseguire DQSInstaller.exe per completare l'installazione del server DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="076c0-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076c0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="076c0-120">See Also</span></span>  
 <span data-ttu-id="076c0-121">[Installare Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="076c0-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="076c0-122">Aggiornare lo schema dei database DQS dopo l'installazione dell'aggiornamento di SQL Server</span><span class="sxs-lookup"><span data-stu-id="076c0-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  
