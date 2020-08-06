---
title: Ridurre il carico di ottimizzazione del server di produzione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- overhead [Database Engine Tuning Advisor]
- tuning overhead [SQL Server]
- reducing production server tuning load
- Database Engine Tuning Advisor [SQL Server], test servers
- test servers [Database Engine Tuning Advisor]
- production servers [SQL Server]
- offload tuning overhead [SQL Server]
ms.assetid: bb95ecaf-444a-4771-a625-e0a91c8f0709
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 53a61b17793a50d6b819f7c1684afdc4de4377f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634992"
---
# <a name="reduce-the-production-server-tuning-load"></a><span data-ttu-id="556c8-102">Riduzione del carico di ottimizzazione del server di produzione</span><span class="sxs-lookup"><span data-stu-id="556c8-102">Reduce the Production Server Tuning Load</span></span>
  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="556c8-103">Ottimizzazione guidata si basa su Query Optimizer per analizzare un carico di lavoro e fornire indicazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="556c8-103">Tuning Advisor relies on the query optimizer to analyze a workload and to make tuning recommendations.</span></span> <span data-ttu-id="556c8-104">L'esecuzione di questa analisi sul server di produzione aumenta il carico del server e può ridurre le prestazioni del server durante la sessione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="556c8-104">Performing this analysis on the production server adds to the server load and can hurt server performance during the tuning session.</span></span> <span data-ttu-id="556c8-105">È possibile diminuire l'impatto sul carico del server durante una sessione di ottimizzazione utilizzando un server di prova oltre al server di produzione.</span><span class="sxs-lookup"><span data-stu-id="556c8-105">You can reduce the impact to the server load during a tuning session by using a test server in addition to the production server.</span></span>

## <a name="how-database-engine-tuning-advisor-uses-a-test-server"></a><span data-ttu-id="556c8-106">Modalità di utilizzo di un server di prova da parte di Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="556c8-106">How Database Engine Tuning Advisor Uses a Test Server</span></span>
 <span data-ttu-id="556c8-107">L'utilizzo tradizionale di un server di prova consiste nel copiare tutti i dati dal server di produzione sul server di prova, ottimizzare quest'ultimo e quindi implementare l'indicazione sul server di produzione.</span><span class="sxs-lookup"><span data-stu-id="556c8-107">The traditional way to use a test server is to copy all of the data from your production server to your test server, tune the test server, and then implement the recommendation on your production server.</span></span> <span data-ttu-id="556c8-108">Questo processo elimina l'effetto sulle prestazioni del server di produzione, ma non rappresenta comunque la soluzione ideale.</span><span class="sxs-lookup"><span data-stu-id="556c8-108">This process eliminates the performance impact on your production server, but nevertheless is not the optimal solution.</span></span> <span data-ttu-id="556c8-109">Ad esempio, la copia di grandi quantità di dati dal server di produzione sul server di prova può richiedere notevoli quantità di tempo e risorse.</span><span class="sxs-lookup"><span data-stu-id="556c8-109">For example, copying large amounts of data from the production to the test server can consume substantial amounts of time and resources.</span></span> <span data-ttu-id="556c8-110">Inoltre, l'hardware del server di prova raramente è potente quanto quello utilizzato per i server di produzione.</span><span class="sxs-lookup"><span data-stu-id="556c8-110">In addition, test server hardware is seldom as powerful as the hardware that is deployed for production servers.</span></span> <span data-ttu-id="556c8-111">Il processo di ottimizzazione si basa su Query Optimizer e le indicazioni da esso generate dipendono in parte dall'hardware sottostante.</span><span class="sxs-lookup"><span data-stu-id="556c8-111">The tuning process relies on the query optimizer, and the recommendations it generates are based in part on the underlying hardware.</span></span> <span data-ttu-id="556c8-112">Se l'hardware del server di prova e di produzione non sono identici, la qualità delle indicazioni di Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] ne risente.</span><span class="sxs-lookup"><span data-stu-id="556c8-112">If the test and production server hardware are not identical, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor recommendation quality is diminished.</span></span>

 <span data-ttu-id="556c8-113">Per evitare questi problemi, Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] esegue l'ottimizzazione di un database in un server di produzione ripartendo la maggioranza del carico di ottimizzazione in un server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-113">To avoid these problems, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor tunes a database on a production server by offloading most of the tuning load onto a test server.</span></span> <span data-ttu-id="556c8-114">Questo avviene utilizzando le informazioni di configurazione hardware del server di produzione e senza copiare effettivamente i dati dal server di produzione sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-114">It does this by using the production server hardware configuration information and without actually copying the data from the production server to the test server.</span></span> [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="556c8-115">Ottimizzazione guidata non copia i dati effettivi dal server di produzione sul server di prova,</span><span class="sxs-lookup"><span data-stu-id="556c8-115">Tuning Advisor does not copy actual data from the production server to the test server.</span></span> <span data-ttu-id="556c8-116">ma solo i metadati e le statistiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="556c8-116">It only copies the metadata and necessary statistics.</span></span>

 <span data-ttu-id="556c8-117">Nella procedura seguente viene illustrato il processo per l'ottimizzazione di un database di produzione su un server di prova:</span><span class="sxs-lookup"><span data-stu-id="556c8-117">The following steps outline the process for tuning a production database on a test server:</span></span>

1.  <span data-ttu-id="556c8-118">Verificare che l'utente che desidera utilizzare il server di prova sia presente su entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="556c8-118">Make sure that the user who wants to use the test server exists on both servers.</span></span>

     <span data-ttu-id="556c8-119">Prima di iniziare, verificare che l'utente che desidera utilizzare il server di prova per l'ottimizzazione del database sul server di produzione sia presente su entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="556c8-119">Before you start, make sure that the user who wants to use the test server to tune a database on the production server exists on both servers.</span></span> <span data-ttu-id="556c8-120">Questo richiede la creazione dell'utente e del relativo account di accesso sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-120">This requires that you create the user and his or her login on the test server.</span></span> <span data-ttu-id="556c8-121">Per i membri del ruolo predefinito del server **sysadmin** su entrambi i computer, questo passaggio non è necessario.</span><span class="sxs-lookup"><span data-stu-id="556c8-121">If you are a member of the **sysadmin** fixed server role on both computers, this step is not necessary.</span></span>

2.  <span data-ttu-id="556c8-122">Ottimizzazione del carico di lavoro sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-122">Tune the workload on the test server.</span></span>

     <span data-ttu-id="556c8-123">Per ottimizzare un carico di lavoro su un server di prova, è necessario usare un file di input XML con l'utilità della riga di comando **dta** .</span><span class="sxs-lookup"><span data-stu-id="556c8-123">To tune a workload on a test server, you must use an XML input file with the **dta** command-line utility.</span></span> <span data-ttu-id="556c8-124">Nel file di input XML specificare il nome del server di prova con l'elemento secondario **TestServer** oltre ai valori per gli altri elementi secondari dell'elemento padre **TuningOptions** .</span><span class="sxs-lookup"><span data-stu-id="556c8-124">In the XML input file, specify the name of your test server with the **TestServer** subelement in addition to specifying the values for the other subelements under the **TuningOptions** parent element.</span></span>

     <span data-ttu-id="556c8-125">Durante il processo di ottimizzazione, Ottimizzazione guidata motore di database crea uno scheletro di database sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-125">During the tuning process, Database Engine Tuning Advisor creates a shell database on the test server.</span></span> <span data-ttu-id="556c8-126">Per creare questo scheletro di database e ottimizzarlo, Ottimizzazione guidata motore di database esegue chiamate al server di produzione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="556c8-126">To create this shell database and tune it, Database Engine Tuning Advisor makes calls to the production server for the following:</span></span>

    1.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="556c8-127">Ottimizzazione guidata importa i metadati dal database di produzione sullo scheletro di database del server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-127">Tuning Advisor imports metadata from the production database to the test server shell database.</span></span> <span data-ttu-id="556c8-128">Questi metadati includono tabelle vuote, indici, viste, stored procedure, trigger e così via.</span><span class="sxs-lookup"><span data-stu-id="556c8-128">This metadata includes empty tables, indexes, views, stored procedures, triggers, and so on.</span></span> <span data-ttu-id="556c8-129">Questo rende possibile l'esecuzione delle query del carico di lavoro sullo scheletro di database del server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-129">This makes it possible for the workload queries to execute against the test server shell database.</span></span>

    2.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="556c8-130">Ottimizzazione guidata importa le statistiche dal server di produzione in modo che Query Optimizer possa ottimizzare in modo accurato le query sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-130">Tuning Advisor imports statistics from the production server so the query optimizer can accurately optimize queries on the test server.</span></span>

    3.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="556c8-131">Ottimizzazione guidata importa i parametri hardware specificando il numero di processori e la memoria disponibile dal server di produzione per offrire a Query Optimizer le informazioni necessarie per generare un piano di query.</span><span class="sxs-lookup"><span data-stu-id="556c8-131">Tuning Advisor imports hardware parameters specifying the number of processors and available memory from the production server to provide the query optimizer with the information it needs to generate a query plan.</span></span>

3.  <span data-ttu-id="556c8-132">Dopo aver ottimizzato lo scheletro di database del server di prova, Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] genera un'indicazione di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="556c8-132">After [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor finishes tuning the test server shell database, it generates a tuning recommendation.</span></span>

4.  <span data-ttu-id="556c8-133">Applicare l'indicazione derivata dall'ottimizzazione del server di prova al server di produzione.</span><span class="sxs-lookup"><span data-stu-id="556c8-133">Apply the recommendation received from tuning the test server to the production server.</span></span>

 <span data-ttu-id="556c8-134">Nella seguente figura viene illustrato lo scenario relativo al server di prova e al server di produzione:</span><span class="sxs-lookup"><span data-stu-id="556c8-134">The following illustration shows the test server and production server scenario:</span></span>

 <span data-ttu-id="556c8-135">![Utilizzo del server di prova con Ottimizzazione guidata motore di database](../../database-engine/media/testsvr.gif "Utilizzo del server di prova con Ottimizzazione guidata motore di database")</span><span class="sxs-lookup"><span data-stu-id="556c8-135">![Database Engine Tuning Advisor test server usage](../../database-engine/media/testsvr.gif "Database Engine Tuning Advisor test server usage")</span></span>

> [!NOTE]
>  <span data-ttu-id="556c8-136">La funzionalità di ottimizzazione del server di prova non è supportata nell'interfaccia utente grafica (GUI) di Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="556c8-136">The test server tuning feature is not supported in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor graphical user interface (GUI).</span></span>

## <a name="example"></a><span data-ttu-id="556c8-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="556c8-137">Example</span></span>
 <span data-ttu-id="556c8-138">Innanzitutto verificare che l'utente che desidera eseguire l'ottimizzazione sia presente sul server di prova e di produzione.</span><span class="sxs-lookup"><span data-stu-id="556c8-138">First, make sure that the user who wants to perform the tuning exists on both the test and production servers.</span></span>

 <span data-ttu-id="556c8-139">Dopo aver copiato le informazioni utente sul server di prova, è possibile definire la sessione di ottimizzazione del server di prova nel file di input XML di Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="556c8-139">After the user information is copied over to your test server, you can define your test server tuning session in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor XML input file.</span></span> <span data-ttu-id="556c8-140">Nell'esempio di file di input XML seguente viene illustrato come specificare un server di prova per ottimizzare un database tramite Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="556c8-140">The following example XML input file illustrates how to specify a test server to tune a database with [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor.</span></span>

 <span data-ttu-id="556c8-141">Nell'esempio, il database `MyDatabaseName` viene ottimizzato su `MyServerName`.</span><span class="sxs-lookup"><span data-stu-id="556c8-141">In this example, the `MyDatabaseName` database is being tuned on `MyServerName`.</span></span> <span data-ttu-id="556c8-142">Lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] , `MyWorkloadScript.sql`, viene utilizzato come carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="556c8-142">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script, `MyWorkloadScript.sql`, is used as the workload.</span></span> <span data-ttu-id="556c8-143">Esso include gli eventi eseguiti su `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="556c8-143">This workload contains events that execute against `MyDatabaseName`.</span></span> <span data-ttu-id="556c8-144">La maggioranza delle chiamate di Query Optimizer al database, che si verificano nell'ambito del processo di ottimizzazione, vengono gestite dallo scheletro di database che risiede su `MyTestServerName`.</span><span class="sxs-lookup"><span data-stu-id="556c8-144">Most of the query optimizer calls to this database, which occur as part of the tuning process, are handled by the shell database that resides on `MyTestServerName`.</span></span> <span data-ttu-id="556c8-145">Lo scheletro di database è costituito da metadati e statistiche.</span><span class="sxs-lookup"><span data-stu-id="556c8-145">The shell database is composed of metadata and statistics.</span></span> <span data-ttu-id="556c8-146">Questo processo determina la ripartizione del carico dell'overhead di ottimizzazione sul server di prova.</span><span class="sxs-lookup"><span data-stu-id="556c8-146">This process results in the tuning overhead being offloaded to the test server.</span></span> <span data-ttu-id="556c8-147">Quando Ottimizzazione guidata [!INCLUDE[ssDE](../../../includes/ssde-md.md)] genera la propria indicazione di ottimizzazione utilizzando questo file di input XML, dovrebbe considerare solo gli indici (`<FeatureSet>IDX</FeatureSet>`), nessun partizionamento e non dovrebbe essere necessario mantenere alcuna delle strutture di progettazione fisica esistenti in `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="556c8-147">When [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor generates its tuning recommendation using this XML input file, it should consider indexes only (`<FeatureSet>IDX</FeatureSet>`), no partitioning, and need not keep any of the existing physical design structures in `MyDatabaseName`.</span></span>

```
<?xml version="1.0" encoding="utf-16" ?>
<DTAXML xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">
  <DTAInput>
    <Server>
      <Name>MyServerName</Name>
      <Database>
        <Name>MyDatabaseName</Name>
      </Database>
    </Server>
    <Workload>
      <File>MyWorkloadScript.sql</File>
    </Workload>
    <TuningOptions>
      <TestServer>MyTestServerName</TestServer>
      <FeatureSet>IDX</FeatureSet>
      <Partitioning>NONE</Partitioning>
      <KeepExisting>NONE</KeepExisting>
    </TuningOptions>
  </DTAInput>
</DTAXML>
```

## <a name="see-also"></a><span data-ttu-id="556c8-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="556c8-148">See Also</span></span>
 <span data-ttu-id="556c8-149">[Considerazioni sull'uso di riferimenti ai file di input XML di server di Test](considerations-for-using-test-servers.md) [&#40;Ottimizzazione guidata motore di database&#41;](database-engine-tuning-advisor.md)</span><span class="sxs-lookup"><span data-stu-id="556c8-149">[Considerations for Using Test Servers](considerations-for-using-test-servers.md) [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](database-engine-tuning-advisor.md)</span></span>


