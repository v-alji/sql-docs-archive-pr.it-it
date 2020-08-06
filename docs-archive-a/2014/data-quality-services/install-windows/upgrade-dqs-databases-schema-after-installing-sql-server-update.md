---
title: Aggiornare lo schema dei database DQS dopo l'installazione dell'aggiornamento di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629624"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="fa03e-102">Aggiornare lo schema dei database DQS dopo l'installazione dell'aggiornamento di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa03e-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="fa03e-103">Dopo aver installato un aggiornamento di SQL Server (patch, hotfix o aggiornamento cumulativo) in un'istanza di DQS configurata precedentemente, potrebbe essere necessario aggiornare lo schema dei database DQS eseguendo il file DQSInstaller.exe con il parametro della riga di comando **upgrade** .</span><span class="sxs-lookup"><span data-stu-id="fa03e-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="fa03e-104">In caso contrario, potrebbe essere visualizzato l'errore seguente durante il tentativo di connessione al server Data Quality utilizzando il client Data Quality:</span><span class="sxs-lookup"><span data-stu-id="fa03e-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="fa03e-105">L'aggiornamento dello schema dei database DQS non influisce sui dati esistenti nei database DQS (Knowledge Base, progetti Data Quality e risultati esportati nel database DQS_STAGING_DATA).</span><span class="sxs-lookup"><span data-stu-id="fa03e-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="fa03e-106">Tuttavia, è necessario eseguire il backup dei database DQS prima di aggiornare il relativo schema per evitare eventuali perdite di dati accidentali durante l'aggiornamento dello schema.</span><span class="sxs-lookup"><span data-stu-id="fa03e-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="fa03e-107">Per altre informazioni sul ripristino dei database DQS, vedere [Backup e ripristino di database DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fa03e-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa03e-108">Per la maggior parte degli aggiornamenti di SQL Server è richiesto un aggiornamento allo schema dei database DQS.</span><span class="sxs-lookup"><span data-stu-id="fa03e-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="fa03e-109">Per informazioni sugli aggiornamenti di SQL Server per i quali è richiesto un aggiornamento allo schema dei database DQS, vedere il grafico nel passaggio 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Aggiornare DQS: installazione di aggiornamenti cumulativi o di patch di hotfix in Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="fa03e-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fa03e-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="fa03e-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="fa03e-111">È necessario aver eseguito l'accesso come membro del gruppo di amministratori nel computer di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa03e-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="fa03e-112">È necessario che l'account utente di Windows sia membro del ruolo predefinito del server sysadmin nell'istanza di SQL Server in cui è installato [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa03e-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="fa03e-113">Per aggiornare lo schema dei database DQS</span><span class="sxs-lookup"><span data-stu-id="fa03e-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="fa03e-114">(Opzione consigliata) Eseguire il backup dei database DQS prima di procedere con l'aggiornamento dello schema.</span><span class="sxs-lookup"><span data-stu-id="fa03e-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="fa03e-115">Per altre informazioni sul ripristino dei database DQS, vedere [Backup e ripristino di database DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="fa03e-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="fa03e-116">Avviare il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="fa03e-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="fa03e-117">Al prompt dei comandi impostare la directory sul percorso in cui è disponibile il file DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="fa03e-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="fa03e-118">Se è stata installata l'istanza predefinita di SQL Server, il file DQSinstaller.exe sarà disponibile in C:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span><span class="sxs-lookup"><span data-stu-id="fa03e-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="fa03e-119">Al prompt dei comandi digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="fa03e-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="fa03e-120">Tramite il programma di installazione viene richiesta all'utente la conferma dell'esecuzione del backup dei database DQS prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="fa03e-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="fa03e-121">Se il backup dei database DQS è già stato eseguito, digitare `Y` o `Yes` e premere INVIO per continuare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fa03e-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="fa03e-122">Se l'aggiornamento dello schema dei database DQS viene terminato correttamente, viene visualizzato un messaggio di completamento.</span><span class="sxs-lookup"><span data-stu-id="fa03e-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fa03e-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="fa03e-123">Next Steps</span></span>  
 <span data-ttu-id="fa03e-124">Accedere al server Data Quality aggiornato da un'applicazione client Data Quality.</span><span class="sxs-lookup"><span data-stu-id="fa03e-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="fa03e-125">Per altre informazioni sull'aggiornamento dello schema dei database DQS in seguito all'installazione degli aggiornamenti di SQL Server e dei relativi passaggi di risoluzione dei problemi, vedere [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Aggiornare DQS: installazione di aggiornamenti cumulativi o di patch di hotfix in Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="fa03e-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa03e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa03e-126">See Also</span></span>  
 <span data-ttu-id="fa03e-127">[Installare Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="fa03e-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="fa03e-128">Aggiornare gli assembly SQLCLR dopo l'aggiornamento di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa03e-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  
