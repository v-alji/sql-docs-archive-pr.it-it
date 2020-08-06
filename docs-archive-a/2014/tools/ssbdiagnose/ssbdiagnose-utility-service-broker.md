---
title: Utilità ssbdiagnose (Service Broker) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720609"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="c2e24-102">Utilità ssbdiagnose (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="c2e24-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="c2e24-103">L'utilità **ssbdiagnose** segnala la presenza di problemi in conversazioni di [!INCLUDE[ssSB](../../includes/sssb-md.md)] o nella configurazione di servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2e24-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="c2e24-104">I controlli della configurazione possono essere eseguiti per due servizi oppure per un unico servizio.</span><span class="sxs-lookup"><span data-stu-id="c2e24-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="c2e24-105">I problemi vengono segnalati nella finestra del prompt dei comandi in testo leggibile oppure in un file XML formattato che può essere reindirizzato a un file oppure a un altro programma.</span><span class="sxs-lookup"><span data-stu-id="c2e24-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e24-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2e24-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="c2e24-107">Opzioni da riga di comando</span><span class="sxs-lookup"><span data-stu-id="c2e24-107">Command Line Options</span></span>  
 <span data-ttu-id="c2e24-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="c2e24-108">**-XML**</span></span>  
 <span data-ttu-id="c2e24-109">Specifica che l'output di **ssbdiagnose** deve essere generato come file XML formattato.</span><span class="sxs-lookup"><span data-stu-id="c2e24-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="c2e24-110">che può essere reindirizzato a un file oppure a un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="c2e24-111">Se l'opzione **-XML** non viene specificata, l'output di **ssbdiagnose** viene formattato come testo leggibile.</span><span class="sxs-lookup"><span data-stu-id="c2e24-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="c2e24-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="c2e24-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="c2e24-113">Specifica il livello dei messaggi da segnalare.</span><span class="sxs-lookup"><span data-stu-id="c2e24-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="c2e24-114">**ERROR**: segnala solo i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="c2e24-115">**WARNING**: segnala i messaggi di errore e di avviso.</span><span class="sxs-lookup"><span data-stu-id="c2e24-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="c2e24-116">**INFO**: segnala i messaggi di errore, di avviso e informativi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="c2e24-117">L'impostazione predefinita è **WARNING**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="c2e24-118">**-IGNORE** *error_id*</span><span class="sxs-lookup"><span data-stu-id="c2e24-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="c2e24-119">Specifica che i messaggi o gli errori con il valore *error_id* specificato non devono essere inclusi nei report.</span><span class="sxs-lookup"><span data-stu-id="c2e24-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="c2e24-120">È possibile specificare **-IGNORE** più volte per eliminare più ID messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2e24-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="c2e24-121">Specifica le informazioni di connessione di base usate da **ssbdiagnose** quando le opzioni di connessione non sono incluse in una clausola specifica.</span><span class="sxs-lookup"><span data-stu-id="c2e24-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="c2e24-122">Le informazioni di connessione indicate in una clausola specifica prevalgono sulle informazioni specificate in **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="c2e24-123">Questa situazione viene gestita separatamente per ciascun parametro.</span><span class="sxs-lookup"><span data-stu-id="c2e24-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="c2e24-124">Ad esempio, se vengono specificati **-S** e **-d** in **baseconnetionoptions**e solo **-d** è specificato in **toconnetionoptions**, **ssbdiagnose** userà -S di **baseconnetionoptions** e -d di **toconnetionoptions**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="c2e24-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="c2e24-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="c2e24-126">Richiede un report degli errori di configurazione tra una coppia di servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] o per un singolo servizio.</span><span class="sxs-lookup"><span data-stu-id="c2e24-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="c2e24-127">**FROM SERVICE** *service_name*</span><span class="sxs-lookup"><span data-stu-id="c2e24-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="c2e24-128">Specifica il servizio che avvia le conversazioni.</span><span class="sxs-lookup"><span data-stu-id="c2e24-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="c2e24-129">Specifica le informazioni necessarie per connettersi al database che contiene il servizio Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2e24-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="c2e24-130">Se **fromconnectionoptions** non viene specificato, **ssbdiagnose** usa le informazioni di connessione di **baseconnectionoptions** per la connessione al database del servizio Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2e24-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="c2e24-131">Se specificato, **fromconnectionoptions** deve includere il database che contiene il servizio Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2e24-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="c2e24-132">Se **fromconnectionoptions** non è specificato, **baseconnectionoptions** deve specificare il database del servizio Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2e24-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="c2e24-133">**TO SERVICE** *service_name*[, *broker_id* ]</span><span class="sxs-lookup"><span data-stu-id="c2e24-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="c2e24-134">Specifica il servizio che rappresenta la destinazione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="c2e24-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="c2e24-135">*service_name*: specifica il nome del servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="c2e24-136">*broker_id*: specifica l'ID di [!INCLUDE[ssSB](../../includes/sssb-md.md)] che identifica il database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="c2e24-137">*broker_id* è un GUID.</span><span class="sxs-lookup"><span data-stu-id="c2e24-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="c2e24-138">Per individuarlo, è possibile eseguire la query seguente sul database di destinazione:</span><span class="sxs-lookup"><span data-stu-id="c2e24-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="c2e24-139">Specifica le informazioni necessarie per connettersi al database che contiene il servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="c2e24-140">Se **toconnectionoptions** non viene specificato, **ssbdiagnose** usa le informazioni di connessione di **baseconnectionoptions** per la connessione al database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="c2e24-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="c2e24-141">**MIRROR**</span></span>  
 <span data-ttu-id="c2e24-142">Specifica che il servizio [!INCLUDE[ssSB](../../includes/sssb-md.md)] associato è ospitato in un database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="c2e24-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="c2e24-143">**ssbdiagnose** verifica che la route per il servizio sia una route con mirroring, in cui MIRROR_ADDRESS è stato specificato in CREATE ROUTE.</span><span class="sxs-lookup"><span data-stu-id="c2e24-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="c2e24-144">Specifica le informazioni necessarie per connettersi al database mirror.</span><span class="sxs-lookup"><span data-stu-id="c2e24-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="c2e24-145">Se **mirrorconnectionoptions** non viene specificato, **ssbdiagnose** usa le informazioni di connessione di **baseconnectionoptions** per la connessione al database mirror.</span><span class="sxs-lookup"><span data-stu-id="c2e24-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="c2e24-146">**ON CONTRACT** *contract_name*</span><span class="sxs-lookup"><span data-stu-id="c2e24-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="c2e24-147">Richiede che **ssbdiagnose** controlli solo le configurazioni che usano il contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="c2e24-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="c2e24-148">Se ON CONTRACT non è specificato, **ssbdiagnose** offre informazioni solo sul contratto denominato DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="c2e24-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="c2e24-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="c2e24-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="c2e24-150">Richiede di verificare che il dialogo sia configurato correttamente per il livello di crittografia specificato:</span><span class="sxs-lookup"><span data-stu-id="c2e24-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="c2e24-151">**ON**: impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c2e24-151">**ON**: Default setting.</span></span> <span data-ttu-id="c2e24-152">Viene configurata la sicurezza completa del dialogo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-152">Full dialog security is configured.</span></span> <span data-ttu-id="c2e24-153">Questo significa che i certificati sono stati distribuiti in entrambi i lati del dialogo, che è presente un'associazione al servizio remoto e che nell'istruzione GRANT SEND per il servizio di destinazione è stato specificato l'utente che avvia il dialogo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="c2e24-154">**OFF**: non viene configurata alcuna sicurezza del dialogo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="c2e24-155">Questo significa che non è stato distribuito alcun certificato, non è stata creata alcuna associazione al servizio remoto e in GRANT SEND per il servizio Initiator è stato specificato il ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="c2e24-156">**ANONYMOUS**: viene configurata la sicurezza anonima del dialogo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="c2e24-157">Questo significa che è stato distribuito solo un certificato, che nell'associazione al servizio remoto è stata specificata la clausola anonima e che in GRANT SEND per il servizio di destinazione è stato specificato il ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="c2e24-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="c2e24-158">**RUNTIME**</span></span>  
 <span data-ttu-id="c2e24-159">Richiede che venga generato un report di problemi che provocano errori di run-time per una conversazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2e24-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="c2e24-160">Se non viene specificata l'opzione **-NEW** o **-ID** , **ssbdiagnose** esegue il monitoraggio di tutte le conversazioni in tutti i database specificati nelle opzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="c2e24-161">Se viene specificata l'opzione **-NEW** o **-ID** , **ssbdiagnose** compila un elenco degli ID specificati nei parametri.</span><span class="sxs-lookup"><span data-stu-id="c2e24-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="c2e24-162">Durante l'esecuzione, **ssbdiagnose** registra tutti gli eventi di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] che indicano errori di run-time,</span><span class="sxs-lookup"><span data-stu-id="c2e24-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="c2e24-163">ovvero gli eventi che si verificano per gli ID specificati più quelli a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="c2e24-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="c2e24-164">Se vengono rilevati errori di run-time, **ssbdiagnose** esegue un report di configurazione sulla configurazione associata.</span><span class="sxs-lookup"><span data-stu-id="c2e24-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="c2e24-165">Per impostazione predefinita, nel report di output non vengono inclusi gli errori di run-time, ma solo i risultati dell'analisi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="c2e24-166">Per includere gli errori di runtime nel report, usare **-SHOWEVENTS** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="c2e24-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="c2e24-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="c2e24-168">Specifica che **ssbdiagnose** deve includere eventi di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] durante la generazione di un report RUNTIME.</span><span class="sxs-lookup"><span data-stu-id="c2e24-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="c2e24-169">Vengono segnalati solo gli eventi considerati come condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="c2e24-170">Per impostazione predefinita, **ssbdiagnose** esegue solo il monitoraggio degli eventi di errore, ma non li inserisce nell'output.</span><span class="sxs-lookup"><span data-stu-id="c2e24-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="c2e24-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="c2e24-171">**-NEW**</span></span>  
 <span data-ttu-id="c2e24-172">Richiede il monitoraggio in fase di esecuzione della prima conversazione iniziata dopo l'avvio di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="c2e24-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="c2e24-173">**-ID**</span></span>  
 <span data-ttu-id="c2e24-174">Richiede il monitoraggio in fase di esecuzione degli elementi di conversazione specificati.</span><span class="sxs-lookup"><span data-stu-id="c2e24-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="c2e24-175">È possibile specificare l'opzione **-ID** più volte.</span><span class="sxs-lookup"><span data-stu-id="c2e24-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="c2e24-176">Se si specifica un handle di conversazione, vengono segnalati solo gli eventi correlati all'endpoint di conversazione associato.</span><span class="sxs-lookup"><span data-stu-id="c2e24-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="c2e24-177">Se si specifica un ID di conversazione, vengono segnalati tutti gli eventi relativi a tale conversazione e agli endpoint dell'Initiator e di destinazione della conversazione stessa,</span><span class="sxs-lookup"><span data-stu-id="c2e24-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="c2e24-178">mentre se si specifica un ID di un gruppo di conversazioni, vengono segnalati tutti gli eventi relativi a tutti gli endpoint e a tutte le conversazioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="c2e24-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="c2e24-179">*conversation_handle*</span></span>  
 <span data-ttu-id="c2e24-180">Identificatore univoco di un endpoint di conversazione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="c2e24-181">Per un endpoint di una conversazione gli handle di conversazione sono univoci , mentre per gli endpoint dell'Initiator e di destinazione gli handle di conversazione sono diversi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="c2e24-182">Gli handle di conversazione vengono restituiti alle applicazioni dal *@dialog_handle* parametro dell'istruzione **BEGIN DIALOG** e dalla `conversation_handle` colonna nel set di risultati di un'istruzione **Receive** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="c2e24-183">Gli handle di conversazione vengono segnalati nella `conversation_handle` colonna delle viste del catalogo **sys. transmission_queue** e **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="c2e24-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="c2e24-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="c2e24-185">Identificatore univoco di un gruppo di conversazioni.</span><span class="sxs-lookup"><span data-stu-id="c2e24-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="c2e24-186">Gli ID del gruppo di conversazioni vengono restituiti alle applicazioni dal *@conversation_group_id* parametro dell'istruzione **Get Conversation Group** e dalla `conversation_group_id` colonna nel set di risultati di un'istruzione **Receive** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="c2e24-187">Gli ID del gruppo di conversazioni vengono indicati nelle `conversation_group_id` colonne delle viste del catalogo **sys. conversation_groups** e **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="c2e24-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="c2e24-188">*conversation_id*</span></span>  
 <span data-ttu-id="c2e24-189">Identificatore univoco di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="c2e24-190">Gli ID di conversazione sono gli stessi per sia gli endpoint dell'Initiator che per quelli di destinazione di una conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="c2e24-191">Gli ID di conversazione vengono segnalati nella `conversation_id` colonna della vista del catalogo **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="c2e24-192">**-TIMEOUT** *timeout_interval*</span><span class="sxs-lookup"><span data-stu-id="c2e24-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="c2e24-193">Specifica il numero di secondi per l'esecuzione un report **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="c2e24-194">Se l'opzione **-TIMEOUT** non viene specificata, il report di runtime viene eseguito per un periodo di tempo illimitato.</span><span class="sxs-lookup"><span data-stu-id="c2e24-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="c2e24-195">**- TIMEOUT** viene usata solo nei report **RUNTIME** e non nei report **CONFIGURATION** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="c2e24-196">Usare CTRL + C per uscire da **ssbdiagnose** se **-TIMEOUT** non è stata specificata oppure per terminare un report di runtime prima che scada l'intervallo di time **-** out.</span><span class="sxs-lookup"><span data-stu-id="c2e24-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="c2e24-197">Il valore*timeout_interval* deve essere un numero compreso tra 1 e 2,147,483,647.</span><span class="sxs-lookup"><span data-stu-id="c2e24-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="c2e24-198">Specifica le informazioni di connessione per i database che contengono i servizi associati agli elementi di conversazione monitorati.</span><span class="sxs-lookup"><span data-stu-id="c2e24-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="c2e24-199">Se tutti i servizi si trovano nello stesso database, è necessario specificare solo una clausola **CONNECT TO** ,</span><span class="sxs-lookup"><span data-stu-id="c2e24-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="c2e24-200">mentre se i servizi si trovano in database separati è necessario specificare una clausola **CONNECT TO** per ogni database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="c2e24-201">Se **runtimeconnectionoptions** non viene specificato, **ssbdiagnose** usa le informazioni di connessione di **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="c2e24-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="c2e24-202">**-E**</span></span>  
 <span data-ttu-id="c2e24-203">Apre una connessione con autenticazione di Windows a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando l'account di Windows corrente come ID di accesso.</span><span class="sxs-lookup"><span data-stu-id="c2e24-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="c2e24-204">Le credenziali di accesso devono corrispondere a un membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="c2e24-205">L'opzione -E consente di ignorare le impostazioni relative all'utente e alla password delle variabili di ambiente SQLCMDUSER e SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="c2e24-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="c2e24-206">Se non viene specificata né **-E** né **-U** , **ssbdiagnose** usa il valore della variabile di ambiente SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="c2e24-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="c2e24-207">Se SQLCMDUSER non è impostata, **ssbdiagnose** usa l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2e24-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="c2e24-208">Se si usa l'opzione **-E** in combinazione con l'opzione **-U** o con l'opzione **-P** , viene generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="c2e24-209">**-U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="c2e24-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="c2e24-210">Apre una connessione con autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite l'ID di accesso specificato.</span><span class="sxs-lookup"><span data-stu-id="c2e24-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="c2e24-211">Le credenziali di accesso devono corrispondere a un membro del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="c2e24-212">Se non viene specificata né **-E** né **-U** , **ssbdiagnose** usa il valore della variabile di ambiente SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="c2e24-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="c2e24-213">Se SQLCMDUSER non è impostata, **ssbdiagnose** tenta di effettuare la connessione usando la modalità di autenticazione di Windows basata sull'account di Windows dell'utente che esegue **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="c2e24-214">Se si usa l'opzione **-U** in combinazione con l'opzione **-E** , viene generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="c2e24-215">Se l'opzione **-U** è seguita da più di un argomento, viene generato un messaggio di errore e il programma viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="c2e24-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="c2e24-216">**-P** *password*</span><span class="sxs-lookup"><span data-stu-id="c2e24-216">**-P** *password*</span></span>  
 <span data-ttu-id="c2e24-217">Specifica la password per l'ID di accesso **-U** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="c2e24-218">Alle password viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c2e24-218">Passwords are case sensitive.</span></span> <span data-ttu-id="c2e24-219">Se si usa l'opzione **-U** senza usare **-P** , **ssbdiagnose** usa il valore della variabile di ambiente SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="c2e24-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="c2e24-220">Se SQLCMDPASSWORD non è impostata, **ssbdiagnose** richiede l'immissione di una password.</span><span class="sxs-lookup"><span data-stu-id="c2e24-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c2e24-221">Quando si digita un comando SET SQLCMDPASSWORD, la password sarà visibile a chiunque sia in grado di vedere il monitor.</span><span class="sxs-lookup"><span data-stu-id="c2e24-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="c2e24-222">Se l'opzione **-P** viene specificata senza che sia indicata una password, **ssbdiagnose** usa la password predefinita (NULL).</span><span class="sxs-lookup"><span data-stu-id="c2e24-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="c2e24-223">Per altre informazioni, vedere [Password complesse](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="c2e24-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="c2e24-224">La richiesta della password viene visualizzata mediante la stampa nella console, come indicato di seguito: `Password:`</span><span class="sxs-lookup"><span data-stu-id="c2e24-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="c2e24-225">L'input dell'utente è nascosto.</span><span class="sxs-lookup"><span data-stu-id="c2e24-225">User input is hidden.</span></span> <span data-ttu-id="c2e24-226">L'input non viene pertanto visualizzato e il cursore rimane in posizione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="c2e24-227">Se si usa l'opzione **-P** in combinazione con l'opzione **-E** , viene generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="c2e24-228">Se l'opzione **-P** è seguita da più di un argomento, viene generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="c2e24-229">**-S** *server_name*[\\*instance_name*]</span><span class="sxs-lookup"><span data-stu-id="c2e24-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="c2e24-230">Specifica l'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] che contiene i servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] da analizzare.</span><span class="sxs-lookup"><span data-stu-id="c2e24-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="c2e24-231">Specificare *server_name* per connettersi all'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="c2e24-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="c2e24-232">Specificare *server_name ***\\*** instance_name* per connettersi a un'istanza denominata del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in tale server.</span><span class="sxs-lookup"><span data-stu-id="c2e24-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="c2e24-233">Se **-S** non viene specificata, **ssbdiagnose** usa il valore della variabile di ambiente SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="c2e24-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="c2e24-234">Se SQLCMDSERVER non è impostata, **ssbdiagnose** si connette all'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)] sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="c2e24-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="c2e24-235">**-d** *database_name*</span><span class="sxs-lookup"><span data-stu-id="c2e24-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="c2e24-236">Specifica il database che contiene i servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] da analizzare.</span><span class="sxs-lookup"><span data-stu-id="c2e24-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="c2e24-237">Se il database non esiste, viene generato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="c2e24-238">Se l'opzione **-d** non è specificata, per impostazione predefinita viene usato il database specificato nella proprietà default-database dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="c2e24-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="c2e24-239">**-l** *login_timeout*</span><span class="sxs-lookup"><span data-stu-id="c2e24-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="c2e24-240">Specifica il numero di secondi prima del timeout di un tentativo di connessione. Se l'opzione **-l** non è specificata, **ssbdiagnose** usa il valore impostato per la variabile di ambiente SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="c2e24-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="c2e24-241">Se SQLCMDLOGINTIMEOUT non è impostata, il timeout predefinito è di trenta secondi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="c2e24-242">Il valore del timeout deve essere un numero compreso tra 0 e 65.534.</span><span class="sxs-lookup"><span data-stu-id="c2e24-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="c2e24-243">Se il valore specificato non è numerico o non è compreso nell'intervallo, **ssbdiagnose** genera un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c2e24-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="c2e24-244">Il valore 0 specifica un timeout infinito.</span><span class="sxs-lookup"><span data-stu-id="c2e24-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="c2e24-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="c2e24-245">**-?**</span></span>  
 <span data-ttu-id="c2e24-246">Visualizza la guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c2e24-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2e24-247">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c2e24-247">Remarks</span></span>  
 <span data-ttu-id="c2e24-248">Usare **ssbdiagnose** per eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="c2e24-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="c2e24-249">Verificare che non siano presenti errori di configurazione in un'applicazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] appena configurata.</span><span class="sxs-lookup"><span data-stu-id="c2e24-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="c2e24-250">Verificare che non siano presenti errori di configurazione in seguito alla modifica della configurazione di un'applicazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] esistente.</span><span class="sxs-lookup"><span data-stu-id="c2e24-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="c2e24-251">Verificare che non siano presenti errori di configurazione in seguito allo scollegamento di un database di [!INCLUDE[ssSB](../../includes/sssb-md.md)] e al successivo collegamento a una nuova istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="c2e24-252">Ricercare eventuali errori di configurazione quando i messaggi non vengono trasmessi correttamente tra servizi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="c2e24-253">Ottenere un report di qualsiasi errore che si verifica in un set di elementi di conversazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2e24-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="c2e24-254">Report di configurazione</span><span class="sxs-lookup"><span data-stu-id="c2e24-254">Configuration Reporting</span></span>  
 <span data-ttu-id="c2e24-255">Per analizzare correttamente la configurazione usata da una conversazione, eseguire un report di configurazione di **ssbdiagnose** che usa le stesse opzioni della conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="c2e24-256">Se per **ssbdiagnose** si specifica un livello di opzioni inferiore rispetto a quello usato dalla conversazione, **ssbdiagnose** potrebbe non segnalare le condizioni necessarie alla conversazione,</span><span class="sxs-lookup"><span data-stu-id="c2e24-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="c2e24-257">mentre se si specifica un livello di opzioni superiore **ssbdiagnose**potrebbe segnalare elementi non richiesti dalla conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="c2e24-258">Una conversazione tra due servizi nello stesso database, ad esempio, può essere eseguita utilizzando l'opzione ENCPRYPTION OFF.</span><span class="sxs-lookup"><span data-stu-id="c2e24-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="c2e24-259">Se si esegue **ssbdiagnose** per convalidare la configurazione tra i due servizi, ma si usa l'impostazione ENCRYPTION ON predefinita, **ssbdiagnose** segnala che nel database manca una chiave master,</span><span class="sxs-lookup"><span data-stu-id="c2e24-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="c2e24-260">che non è richiesta per la conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="c2e24-261">Il report di configurazione di **ssbdiagnose** analizza solo un servizio oppure una singola coppia di servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="c2e24-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="c2e24-262">Per eseguire report su più coppie di servizi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] , compilare un file di comando con estensione cmd che chiama l'utilità **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="c2e24-263">Report in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c2e24-263">Runtime Reporting</span></span>  
 <span data-ttu-id="c2e24-264">Quando viene specificata l'opzione -RUNTIME, **ssbdiagnose** cerca in tutti i database specificati in **runtimeconnectionoptions** e **baseconnectionoption** s per generare un elenco degli ID di [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2e24-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="c2e24-265">L'elenco completo di ID dipende dagli elementi specificati per le opzioni -NEW e -ID:</span><span class="sxs-lookup"><span data-stu-id="c2e24-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="c2e24-266">Se non viene specificata né **-NEW** né **-ID** , nell'elenco vengono incluse tutte le conversazioni per tutti i database specificati nelle opzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="c2e24-267">Se l'opzione **-NEW** è specificata, **ssbdiagnose** include gli elementi per la prima conversazione avviata dopo l'esecuzione di **ssbdiagnose** ,</span><span class="sxs-lookup"><span data-stu-id="c2e24-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="c2e24-268">tra cui l'ID e gli handle di conversazione relativi sia agli endpoint di conversazione dell'Initiator e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="c2e24-269">Se l'opzione **-ID** è specificata con un handle di conversazione, nell'elenco viene inserito solo tale handle.</span><span class="sxs-lookup"><span data-stu-id="c2e24-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="c2e24-270">Se l'opzione **-ID** è specificata con un ID conversazione, all'elenco vengono aggiunti l'ID conversazione e gli handle per entrambi gli endpoint di conversazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="c2e24-271">Se l'opzione **-ID** è specificata con un ID gruppo di conversazioni, all'elenco vengono aggiunti tutti gli ID conversazione e gli handle di conversazione di tale gruppo.</span><span class="sxs-lookup"><span data-stu-id="c2e24-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="c2e24-272">Nell'elenco non sono inclusi elementi da database non coperti dalle opzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="c2e24-273">Se ad esempio si usa l'opzione **-ID** per specificare un ID conversazione, ma si specifica solo una clausola **runtimeconnectionoptions** per il database del servizio Initiator e non il database di destinazione,</span><span class="sxs-lookup"><span data-stu-id="c2e24-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="c2e24-274">**ssbdiagnose** non includerà l'handle di conversazione di destinazione nell'elenco degli ID, ma solo l'ID conversazione e l'handle di conversazione del servizio Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2e24-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="c2e24-275">**ssbdiagnose** esegue il monitoraggio degli eventi di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] dei database coperti da **runtimeconnectionoptions** e **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="c2e24-276">Cerca gli eventi di [!INCLUDE[ssSB](../../includes/sssb-md.md)] che indicano la presenza di un errore in base a uno o più ID di [!INCLUDE[ssSB](../../includes/sssb-md.md)] nell'elenco di runtime.</span><span class="sxs-lookup"><span data-stu-id="c2e24-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="c2e24-277">**ssbdiagnose** cerca anche gli eventi di errore di [!INCLUDE[ssSB](../../includes/sssb-md.md)] a livello di sistema non specificamente associati alcun gruppo di conversazioni.</span><span class="sxs-lookup"><span data-stu-id="c2e24-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="c2e24-278">Se **ssbdiagnose** rileva errori di conversazione, l'utilità tenterà di segnalare la causa radice degli eventi eseguendo anche un report di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="c2e24-279">**ssbdiagnose** usa i metadati presenti nei database per tentare di determinare le istanze, gli ID [!INCLUDE[ssSB](../../includes/sssb-md.md)] , i database, i servizi e i contratti usati dalla conversazione</span><span class="sxs-lookup"><span data-stu-id="c2e24-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="c2e24-280">ed esegue quindi un report di configurazione utilizzando tutte le informazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="c2e24-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="c2e24-281">Per impostazione predefinita, **ssbdiagnose** non segnala eventi di errore,</span><span class="sxs-lookup"><span data-stu-id="c2e24-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="c2e24-282">ma solo i problemi sottostanti rilevati durante il controllo della configurazione.</span><span class="sxs-lookup"><span data-stu-id="c2e24-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="c2e24-283">In questo modo la quantità di informazioni segnalate viene ridotta ed è possibile concentrarsi sui problemi di configurazione sottostanti.</span><span class="sxs-lookup"><span data-stu-id="c2e24-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="c2e24-284">Per visualizzare gli eventi di errore rilevati da **ssbdiagnose** , è possibile specificare **-SHOWEVENTS**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="c2e24-285">Problemi segnalati di ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="c2e24-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="c2e24-286">**ssbdiagnose** segnala tre classi di problemi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="c2e24-287">Nel file di output XML ogni classe di problemi viene segnalata come un tipo separato dell'elemento Issue.</span><span class="sxs-lookup"><span data-stu-id="c2e24-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="c2e24-288">Di seguito sono riportati i tre tipi di problemi segnalati da **ssbdiagnose** :</span><span class="sxs-lookup"><span data-stu-id="c2e24-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="c2e24-289">**Diagnosi**</span><span class="sxs-lookup"><span data-stu-id="c2e24-289">**Diagnosis**</span></span>  
 <span data-ttu-id="c2e24-290">Segnala un problema di configurazione,</span><span class="sxs-lookup"><span data-stu-id="c2e24-290">Reports a configuration issue.</span></span> <span data-ttu-id="c2e24-291">ovvero problemi rilevati durante l'esecuzione di un report **CONFIGURATION** o durante la fase di configurazione di un report **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="c2e24-292">**ssbdiagnose** segnala ogni problema di configurazione solo una volta.</span><span class="sxs-lookup"><span data-stu-id="c2e24-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="c2e24-293">**Event**</span><span class="sxs-lookup"><span data-stu-id="c2e24-293">**Event**</span></span>  
 <span data-ttu-id="c2e24-294">Segnala un evento di [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] che indica che si è verificato un problema in una conversazione monitorata durante un report **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="c2e24-295">**ssbdiagnose** segnala gli eventi ogni volta che vengono generati.</span><span class="sxs-lookup"><span data-stu-id="c2e24-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="c2e24-296">Se il problema viene rilevato in più conversazioni, gli eventi possono essere segnalati più volte.</span><span class="sxs-lookup"><span data-stu-id="c2e24-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="c2e24-297">**Problema**</span><span class="sxs-lookup"><span data-stu-id="c2e24-297">**Problem**</span></span>  
 <span data-ttu-id="c2e24-298">Segnala un problema che impedisce a **ssbdiagnose** di completare un'analisi di configurazione o di monitorare le conversazioni.</span><span class="sxs-lookup"><span data-stu-id="c2e24-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="c2e24-299">Variabili di ambiente sqlcmd</span><span class="sxs-lookup"><span data-stu-id="c2e24-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="c2e24-300">L'utilità **ssbdiagnose** supporta le variabili di ambiente SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD e SQLCMDLOGINTIMOUT usate anche dall'utilità **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="c2e24-301">Per impostare le variabili di ambiente, è possibile usare il comando SET del prompt dei comandi o il comando **setvar** negli script [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguiti tramite **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="c2e24-302">Per altre informazioni sull'uso di **setvar** in **sqlcmd**, vedere [Utilizzo di sqlcmd con variabili di scripting](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c2e24-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="c2e24-303">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c2e24-303">Permissions</span></span>  
 <span data-ttu-id="c2e24-304">In ogni clausola **connectionoptions** l'account di accesso specificato mediante **-E** o **-U** deve essere un membro del ruolo predefinito del server **sysadmin** nell'istanza specificata in **-S**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c2e24-305">Esempi</span><span class="sxs-lookup"><span data-stu-id="c2e24-305">Examples</span></span>  
 <span data-ttu-id="c2e24-306">Questa sezione include esempi d'uso di **ssbdiagnose** a un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="c2e24-307">R.</span><span class="sxs-lookup"><span data-stu-id="c2e24-307">A.</span></span> <span data-ttu-id="c2e24-308">Controllo della configurazione di due servizi nello stesso database</span><span class="sxs-lookup"><span data-stu-id="c2e24-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="c2e24-309">Nell'esempio seguente viene illustrato come richiedere un report di configurazione quando si verificano le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="c2e24-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="c2e24-310">Il servizio Initiator e quello di destinazione si trovano nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="c2e24-311">Il database si trova nell'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="c2e24-312">L'istanza si trova nello stesso computer in cui viene eseguita **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="c2e24-313">L'utilità **ssbdiagnose** segnala la configurazione che usa il contratto DEFAULT poiché l'opzione ON CONTRACT non è specificata.</span><span class="sxs-lookup"><span data-stu-id="c2e24-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="c2e24-314">B.</span><span class="sxs-lookup"><span data-stu-id="c2e24-314">B.</span></span> <span data-ttu-id="c2e24-315">Controllo della configurazione di due servizi in computer separati che utilizzano un unico account di accesso</span><span class="sxs-lookup"><span data-stu-id="c2e24-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="c2e24-316">Nell'esempio seguente viene illustrato come richiedere un report di configurazione quando il servizio Initiator e quello di destinazione si trovano in computer separati, ma l'accesso ai servizi può essere eseguito utilizzando lo stesso account con autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2e24-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="c2e24-317">C.</span><span class="sxs-lookup"><span data-stu-id="c2e24-317">C.</span></span> <span data-ttu-id="c2e24-318">Controllo della configurazione di due servizi in computer separati che utilizzano account di accesso diversi</span><span class="sxs-lookup"><span data-stu-id="c2e24-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="c2e24-319">Nell'esempio seguente viene illustrato come richiedere un report di configurazione quando il servizio Initiator e quello di destinazione si trovano in computer separati ed è necessario utilizzare due account di accesso con autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diversi per ogni istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="c2e24-320">D.</span><span class="sxs-lookup"><span data-stu-id="c2e24-320">D.</span></span> <span data-ttu-id="c2e24-321">Controllo delle configurazioni del servizio con mirroring in computer separati con crittografia anonima</span><span class="sxs-lookup"><span data-stu-id="c2e24-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="c2e24-322">Nell'esempio seguente viene illustrato come richiedere un report di configurazione quando il servizio Initiator e quello di destinazione si trovano in computer separati e viene eseguito il mirroring del servizio Initiator a un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="c2e24-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="c2e24-323">Il report verifica inoltre che i servizi siano configurati in modo da utilizzare la crittografia anonima.</span><span class="sxs-lookup"><span data-stu-id="c2e24-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="c2e24-324">E.</span><span class="sxs-lookup"><span data-stu-id="c2e24-324">E.</span></span> <span data-ttu-id="c2e24-325">Controllo della configurazione di due contratti</span><span class="sxs-lookup"><span data-stu-id="c2e24-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="c2e24-326">Nell'esempio seguente viene illustrato come compilare un file di comando per richiedere un report di configurazione quando si verificano le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="c2e24-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="c2e24-327">Il servizio Initiator e quello di destinazione si trovano nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="c2e24-328">Il database si trova nell'istanza predefinita del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="c2e24-329">L'istanza si trova nello stesso computer in cui viene eseguita **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="c2e24-330">Ogni volta che **ssbdiagnose** viene eseguita, segnala la configurazione per un contratto diverso tra gli stessi servizi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="c2e24-331">F.</span><span class="sxs-lookup"><span data-stu-id="c2e24-331">F.</span></span> <span data-ttu-id="c2e24-332">Monitoraggio dello stato di una conversazione specifica nel computer locale con un timeout</span><span class="sxs-lookup"><span data-stu-id="c2e24-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="c2e24-333">L'esempio seguente illustra come monitorare una conversazione specifica per cui il servizio Initiator e quello di destinazione si trovano nello stesso database nell'istanza predefinita dello stesso computer in cui è in esecuzione **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="c2e24-334">L'intervallo di timeout è impostato su 20 secondi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="c2e24-335">G.</span><span class="sxs-lookup"><span data-stu-id="c2e24-335">G.</span></span> <span data-ttu-id="c2e24-336">Monitoraggio dello stato di una conversazione eseguita tra due computer</span><span class="sxs-lookup"><span data-stu-id="c2e24-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="c2e24-337">Nell'esempio seguente viene illustrato come monitorare una conversazione specifica per cui il servizio Initiator e quello di destinazione si trovano in database diversi.</span><span class="sxs-lookup"><span data-stu-id="c2e24-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="c2e24-338">H.</span><span class="sxs-lookup"><span data-stu-id="c2e24-338">H.</span></span> <span data-ttu-id="c2e24-339">Monitoraggio dello stato di una conversazione in due database nella stessa istanza</span><span class="sxs-lookup"><span data-stu-id="c2e24-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="c2e24-340">Nell'esempio seguente viene illustrato come monitorare una conversazione specifica per cui il servizio Initiator e quello di destinazione si trovano in database diversi della stessa istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c2e24-341">L'esempio usa **baseconnectionoptions** per specificare le informazioni sull'istanza e sull'account di accesso e le due clausole CONNECT TO per specificare i database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="c2e24-342">L'opzione -SHOWEVENTS viene specificata in modo che tutti gli eventi in fase di esecuzione vengano inclusi nel report restituito.</span><span class="sxs-lookup"><span data-stu-id="c2e24-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="c2e24-343">I.</span><span class="sxs-lookup"><span data-stu-id="c2e24-343">I.</span></span> <span data-ttu-id="c2e24-344">Monitoraggio dello stato di due conversazioni tra due database</span><span class="sxs-lookup"><span data-stu-id="c2e24-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="c2e24-345">Nell'esempio seguente viene illustrato come monitorare due conversazioni per cui il servizio Initiator e quello di destinazione si trovano in database diversi della stessa istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c2e24-346">L'esempio usa **baseconnectionoptions** per specificare le informazioni sull'istanza e sull'account di accesso e le due clausole CONNECT TO per specificare i database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="c2e24-347">J.</span><span class="sxs-lookup"><span data-stu-id="c2e24-347">J.</span></span> <span data-ttu-id="c2e24-348">Monitoraggio dello stato di tutte le conversazioni tra due database</span><span class="sxs-lookup"><span data-stu-id="c2e24-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="c2e24-349">Nell'esempio seguente viene illustrato come monitorare tutta la conversazione tra due database nella stessa istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2e24-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c2e24-350">L'esempio usa **baseconnectionoptions** per specificare le informazioni sull'istanza e sull'account di accesso e le due clausole CONNECT TO per specificare i database.</span><span class="sxs-lookup"><span data-stu-id="c2e24-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="c2e24-351">K.</span><span class="sxs-lookup"><span data-stu-id="c2e24-351">K.</span></span> <span data-ttu-id="c2e24-352">Ignorare errori specifici</span><span class="sxs-lookup"><span data-stu-id="c2e24-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="c2e24-353">Nell'esempio seguente viene illustrato come ignorare errori noti (303 e 304) in un'attivazione configurata attualmente in un sistema di prova.</span><span class="sxs-lookup"><span data-stu-id="c2e24-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="c2e24-354">L.</span><span class="sxs-lookup"><span data-stu-id="c2e24-354">L.</span></span> <span data-ttu-id="c2e24-355">Reindirizzamento dell'output XML di ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="c2e24-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="c2e24-356">L'esempio seguente illustra come richiedere che **ssbdiagnose** generi come output un file con estensione xml reindirizzato a un altro file.</span><span class="sxs-lookup"><span data-stu-id="c2e24-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="c2e24-357">Il file TestDiag.xml può quindi essere aperto da un'applicazione per analizzare o segnalare i file con estensione xml di **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="c2e24-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="c2e24-358">In alternativa, è possibile visualizzarlo mediante un editor XML generico, ad esempio XML Notepad.</span><span class="sxs-lookup"><span data-stu-id="c2e24-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="c2e24-359">M.</span><span class="sxs-lookup"><span data-stu-id="c2e24-359">M.</span></span> <span data-ttu-id="c2e24-360">Utilizzo di una variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="c2e24-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="c2e24-361">L'esempio seguente imposta prima la variabile di ambiente SQLCMDSERVER per specificare il nome del server, quindi esegue **ssbdiagnose** senza specificare **-S**.</span><span class="sxs-lookup"><span data-stu-id="c2e24-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2e24-362">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2e24-362">See Also</span></span>  
 <span data-ttu-id="c2e24-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="c2e24-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="c2e24-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="c2e24-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c2e24-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="c2e24-378">sys.conversation_groups &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c2e24-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
