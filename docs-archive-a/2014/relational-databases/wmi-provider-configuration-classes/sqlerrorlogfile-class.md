---
title: Classe SqlErrorLogFile | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712899"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="d6c24-102">Classe SqlErrorLogFile</span><span class="sxs-lookup"><span data-stu-id="d6c24-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="d6c24-103">Fornisce proprietà per la visualizzazione delle informazioni relative a un file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6c24-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6c24-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="d6c24-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d6c24-105">Properties</span></span>  
 <span data-ttu-id="d6c24-106">La classe SQLErrorLogFile definisce le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="d6c24-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6c24-107">ArchiveNumber</span><span class="sxs-lookup"><span data-stu-id="d6c24-107">ArchiveNumber</span></span>|<span data-ttu-id="d6c24-108">Tipo di dati: `uint32`</span><span class="sxs-lookup"><span data-stu-id="d6c24-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="d6c24-109">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d6c24-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d6c24-110">Numero dell'archivio per il file di log.</span><span class="sxs-lookup"><span data-stu-id="d6c24-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="d6c24-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="d6c24-111">InstanceName</span></span>|<span data-ttu-id="d6c24-112">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="d6c24-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d6c24-113">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d6c24-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="d6c24-114">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="d6c24-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="d6c24-115">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si trova il file di log.</span><span class="sxs-lookup"><span data-stu-id="d6c24-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="d6c24-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="d6c24-116">LastModified</span></span>|<span data-ttu-id="d6c24-117">Tipo di dati: `datetime`</span><span class="sxs-lookup"><span data-stu-id="d6c24-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="d6c24-118">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d6c24-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d6c24-119">Data dell'ultima modifica apportata al file di log.</span><span class="sxs-lookup"><span data-stu-id="d6c24-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="d6c24-120">LogFileSize</span><span class="sxs-lookup"><span data-stu-id="d6c24-120">LogFileSize</span></span>|<span data-ttu-id="d6c24-121">Tipo di dati: `uint32`</span><span class="sxs-lookup"><span data-stu-id="d6c24-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="d6c24-122">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d6c24-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d6c24-123">Dimensione del file di log, in byte.</span><span class="sxs-lookup"><span data-stu-id="d6c24-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="d6c24-124">Nome</span><span class="sxs-lookup"><span data-stu-id="d6c24-124">Name</span></span>|<span data-ttu-id="d6c24-125">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="d6c24-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d6c24-126">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="d6c24-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="d6c24-127">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="d6c24-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="d6c24-128">Nome del file di log.</span><span class="sxs-lookup"><span data-stu-id="d6c24-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6c24-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d6c24-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6c24-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d6c24-130">MOF</span></span>|<span data-ttu-id="d6c24-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="d6c24-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="d6c24-132">DLL</span><span class="sxs-lookup"><span data-stu-id="d6c24-132">DLL</span></span>|<span data-ttu-id="d6c24-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="d6c24-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="d6c24-134">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d6c24-134">Namespace</span></span>|<span data-ttu-id="d6c24-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="d6c24-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d6c24-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6c24-136">Example</span></span>  
 <span data-ttu-id="d6c24-137">Nell'esempio seguente viene illustrato come recuperare informazioni su tutti i file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6c24-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d6c24-138">Per eseguire l'esempio, sostituire \<*Instance_Name*> con il nome dell'istanza, ad esempio,' Instance1'.</span><span class="sxs-lookup"><span data-stu-id="d6c24-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="d6c24-139">Commenti</span><span class="sxs-lookup"><span data-stu-id="d6c24-139">Comments</span></span>  
 <span data-ttu-id="d6c24-140">Quando *NomeIstanza* non viene fornito nell'istruzione WQL, la query restituirà informazioni per l'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="d6c24-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="d6c24-141">L'istruzione WQL seguente restituisce, ad esempio, informazioni su tutti i file di log dall'istanza predefinita (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d6c24-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="d6c24-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d6c24-142">Security</span></span>  
 <span data-ttu-id="d6c24-143">Per connettersi a un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file di log tramite WMI, è necessario disporre delle autorizzazioni seguenti per i computer locali e remoti:</span><span class="sxs-lookup"><span data-stu-id="d6c24-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="d6c24-144">Accesso in lettura allo spazio dei nomi WMI **allo root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="d6c24-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="d6c24-145">Per impostazione predefinita, chiunque dispone di accesso in lettura tramite l'autorizzazione Abilita account.</span><span class="sxs-lookup"><span data-stu-id="d6c24-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6c24-146">Per informazioni su come verificare le autorizzazioni WMI, vedere la sezione relativa alla sicurezza nell'argomento [visualizzare i file di log offline](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="d6c24-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="d6c24-147">Autorizzazione di lettura per la cartella che contiene i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="d6c24-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="d6c24-148">Per impostazione predefinita, i log degli errori si trovano nel percorso seguente \<*Drive> , dove \* rappresenta l'unità in cui è stato installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> è il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d6c24-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="d6c24-149">\*\* \<Drive> : \Programmi\microsoft SQL Server\MSSQL11\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="d6c24-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="d6c24-150">Se si sta eseguendo la connessione attraverso un firewall, assicurarsi che sia impostata un'eccezione nel firewall per WMI nei computer di destinazione remoti.</span><span class="sxs-lookup"><span data-stu-id="d6c24-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="d6c24-151">Per ulteriori informazioni, vedere [connessione a WMI in modalità remota a partire da Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="d6c24-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c24-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6c24-152">See Also</span></span>  
 <span data-ttu-id="d6c24-153">[Classe SqlErrorLogEvent](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="d6c24-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="d6c24-154">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="d6c24-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
