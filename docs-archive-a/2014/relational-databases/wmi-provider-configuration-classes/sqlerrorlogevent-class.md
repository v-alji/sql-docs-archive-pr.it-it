---
title: Classe SqlErrorLogEvent | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627666"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="c740a-102">Classe SqlErrorLogEvent</span><span class="sxs-lookup"><span data-stu-id="c740a-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="c740a-103">Fornisce proprietà per la visualizzazione di eventi in un file di log di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specificato.</span><span class="sxs-lookup"><span data-stu-id="c740a-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c740a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c740a-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="c740a-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c740a-105">Properties</span></span>  
 <span data-ttu-id="c740a-106">La classe SQLErrorLogEvent definisce le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="c740a-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c740a-107">FileName</span><span class="sxs-lookup"><span data-stu-id="c740a-107">FileName</span></span>|<span data-ttu-id="c740a-108">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="c740a-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c740a-109">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c740a-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c740a-110">Nome del file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="c740a-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="c740a-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="c740a-111">InstanceName</span></span>|<span data-ttu-id="c740a-112">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="c740a-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c740a-113">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c740a-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="c740a-114">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="c740a-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="c740a-115">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui si trova il file di log.</span><span class="sxs-lookup"><span data-stu-id="c740a-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="c740a-116">LogDate</span><span class="sxs-lookup"><span data-stu-id="c740a-116">LogDate</span></span>|<span data-ttu-id="c740a-117">Tipo di dati: `datetime`</span><span class="sxs-lookup"><span data-stu-id="c740a-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="c740a-118">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c740a-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="c740a-119">Qualificatori: chiave</span><span class="sxs-lookup"><span data-stu-id="c740a-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="c740a-120">Data e ora della registrazione dell'evento nel file di log.</span><span class="sxs-lookup"><span data-stu-id="c740a-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="c740a-121">Message</span><span class="sxs-lookup"><span data-stu-id="c740a-121">Message</span></span>|<span data-ttu-id="c740a-122">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="c740a-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c740a-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c740a-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c740a-124">Messaggio di evento.</span><span class="sxs-lookup"><span data-stu-id="c740a-124">The event message.</span></span>|  
|<span data-ttu-id="c740a-125">ProcessInfo</span><span class="sxs-lookup"><span data-stu-id="c740a-125">ProcessInfo</span></span>|<span data-ttu-id="c740a-126">Tipo di dati: `string`</span><span class="sxs-lookup"><span data-stu-id="c740a-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="c740a-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="c740a-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="c740a-128">Informazioni sull'ID del processo server di origine (SPID) per l'evento.</span><span class="sxs-lookup"><span data-stu-id="c740a-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c740a-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c740a-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c740a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c740a-130">MOF</span></span>|<span data-ttu-id="c740a-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="c740a-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="c740a-132">DLL</span><span class="sxs-lookup"><span data-stu-id="c740a-132">DLL</span></span>|<span data-ttu-id="c740a-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="c740a-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="c740a-134">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c740a-134">Namespace</span></span>|<span data-ttu-id="c740a-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="c740a-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c740a-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="c740a-136">Example</span></span>  
 <span data-ttu-id="c740a-137">Nell'esempio seguente viene illustrato come recuperare valori per tutti gli eventi registrati in un file di log specificato.</span><span class="sxs-lookup"><span data-stu-id="c740a-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="c740a-138">Per eseguire l'esempio, sostituire \<*Instance_Name*> con il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad esempio ' Instance1', e sostituire ' file_name ' con il nome del file di log degli errori, ad esempio ' log degli errori. 1'.</span><span class="sxs-lookup"><span data-stu-id="c740a-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="c740a-139">Commenti</span><span class="sxs-lookup"><span data-stu-id="c740a-139">Comments</span></span>  
 <span data-ttu-id="c740a-140">Quando *NomeIstanza* o *filename* non vengono specificati nell'istruzione WQL, la query restituirà informazioni per l'istanza predefinita e il file di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log corrente.</span><span class="sxs-lookup"><span data-stu-id="c740a-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="c740a-141">L'istruzione WQL seguente restituisce, ad esempio, tutti gli eventi di log per il file di log corrente (ERRORLOG) nell'istanza predefinita (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="c740a-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="c740a-142">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c740a-142">Security</span></span>  
 <span data-ttu-id="c740a-143">Per connettersi a un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file di log tramite WMI, è necessario disporre delle autorizzazioni seguenti per i computer locali e remoti:</span><span class="sxs-lookup"><span data-stu-id="c740a-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="c740a-144">Accesso in lettura allo spazio dei nomi WMI **allo root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="c740a-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="c740a-145">Per impostazione predefinita, chiunque dispone di accesso in lettura tramite l'autorizzazione Abilita account.</span><span class="sxs-lookup"><span data-stu-id="c740a-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="c740a-146">Autorizzazione di lettura per la cartella che contiene i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="c740a-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="c740a-147">Per impostazione predefinita, i log degli errori si trovano nel percorso seguente \<*Drive> , dove \* rappresenta l'unità in cui è stato installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e \<*InstanceName*> è il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c740a-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="c740a-148">\*\* \<Drive> : \Programmi\microsoft SQL Server\MSSQL12\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="c740a-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="c740a-149">Se si sta eseguendo la connessione attraverso un firewall, assicurarsi che sia impostata un'eccezione nel firewall per WMI nei computer di destinazione remoti.</span><span class="sxs-lookup"><span data-stu-id="c740a-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="c740a-150">Per ulteriori informazioni, vedere [connessione a WMI in modalità remota a partire da Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="c740a-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c740a-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c740a-151">See Also</span></span>  
 <span data-ttu-id="c740a-152">[Classe SqlErrorLogFile](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="c740a-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="c740a-153">Visualizzare file di log offline</span><span class="sxs-lookup"><span data-stu-id="c740a-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
