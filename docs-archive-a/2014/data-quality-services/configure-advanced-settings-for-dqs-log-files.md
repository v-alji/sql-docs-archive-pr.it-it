---
title: Configurare le impostazioni avanzate per i file di log DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712416"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="1cb29-102">Configurare le impostazioni avanzate per i file di log DQS</span><span class="sxs-lookup"><span data-stu-id="1cb29-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="1cb29-103">In questo argomento viene descritto come configurare le impostazioni avanzate per i file di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , ad esempio come impostare il limite delle dimensioni dei file mobili per i file di log, il modello del timestamp degli eventi e così via.</span><span class="sxs-lookup"><span data-stu-id="1cb29-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cb29-104">Queste attività non possono essere eseguite mediante il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]e sono destinate solo agli utenti avanzati.</span><span class="sxs-lookup"><span data-stu-id="1cb29-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1cb29-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1cb29-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1cb29-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1cb29-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1cb29-107">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1cb29-107">Permissions</span></span>  
  
-   <span data-ttu-id="1cb29-108">Per modificare le impostazioni di configurazione nella tabella A_CONFIGURATION del database DQS_MAIN, è necessario che l'account utente di Windows sia membro del ruolo predefinito del server sysadmin nell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cb29-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="1cb29-109">Per configurare le impostazioni di registrazione del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , è necessario avere eseguito l'accesso come membro del gruppo Administrators al computer in cui si modifica il file DQLog.Client.xml.</span><span class="sxs-lookup"><span data-stu-id="1cb29-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a><span data-ttu-id="1cb29-110">Configurare le impostazioni del log del server Data Quality</span><span class="sxs-lookup"><span data-stu-id="1cb29-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="1cb29-111">Le impostazioni di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] sono presenti in formato XML nella colonna **VALUE** della riga **ServerLogging** nella tabella A_CONFIGURATION del database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="1cb29-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="1cb29-112">Per visualizzare le informazioni di configurazione, è possibile eseguire la query SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="1cb29-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="1cb29-113">È necessario aggiornare le informazioni appropriate nella colonna **VALUE** della riga **ServerLogging** per modificare le impostazioni di configurazione per la registrazione del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cb29-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="1cb29-114">In questo esempio verranno aggiornate le impostazioni di log del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] per impostare il limite delle dimensioni dei file mobili su 25000 KB (il valore predefinito è 20000 KB).</span><span class="sxs-lookup"><span data-stu-id="1cb29-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="1cb29-115">Avviare Microsoft SQL Server Management Studio e connettersi all'istanza di SQL Server appropriata.</span><span class="sxs-lookup"><span data-stu-id="1cb29-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="1cb29-116">In Esplora oggetti fare clic con il pulsante destro del mouse sul server, quindi fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1cb29-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1cb29-117">Nella finestra dell'editor di query copiare le istruzioni SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cb29-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="1cb29-118">Premere F5 per eseguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1cb29-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="1cb29-119">Esaminare il riquadro **Risultati** per verificare che le istruzioni siano state eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="1cb29-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="1cb29-120">Per applicare le modifiche apportate alla configurazione della registrazione del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , è necessario eseguire le istruzioni Transact-SQL seguenti.</span><span class="sxs-lookup"><span data-stu-id="1cb29-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="1cb29-121">Aprire una nuova finestra dell'editor di query e incollare le istruzioni Transact-SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="1cb29-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="1cb29-122">Premere F5 per eseguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="1cb29-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="1cb29-123">Esaminare il riquadro **Risultati** per verificare che le istruzioni siano state eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="1cb29-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cb29-124">La configurazione delle impostazioni di registrazione del [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] viene generata dinamicamente e viene archiviata nel file DQS_MAIN.Log, disponibile in genere in C:\Programmi\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log se è stata installata l'istanza predefinita di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1cb29-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="1cb29-125">Tuttavia, le modifiche effettuate direttamente in questo file non vengono conservate e vengono sovrascritte dalle impostazioni di configurazione nella tabella A_CONFIGURATION del database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="1cb29-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="1cb29-126">Configurare le impostazioni del log Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="1cb29-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="1cb29-127">Il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] file di configurazione delle impostazioni di log, DQLog.Client.xml, è disponibile in genere in C:\Programmi\Microsoft SQL Server\120\Tools\Binn\DQ\config. Il contenuto del file XML è simile al file XML modificato in precedenza per le [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] impostazioni di configurazione del log.</span><span class="sxs-lookup"><span data-stu-id="1cb29-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="1cb29-128">Per configurare le impostazioni di log del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1cb29-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="1cb29-129">Eseguire un qualsiasi strumento di modifica dei file XML o Blocco note come amministratore.</span><span class="sxs-lookup"><span data-stu-id="1cb29-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="1cb29-130">Aprire il file DQLog.Client.xml nello strumento o in Blocco note.</span><span class="sxs-lookup"><span data-stu-id="1cb29-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="1cb29-131">Apportare le modifiche necessarie e salvare il file per applicare le nuove modifiche di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1cb29-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb29-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cb29-132">See Also</span></span>  
 [<span data-ttu-id="1cb29-133">Configurare livelli di gravità per i file di log DQS</span><span class="sxs-lookup"><span data-stu-id="1cb29-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
