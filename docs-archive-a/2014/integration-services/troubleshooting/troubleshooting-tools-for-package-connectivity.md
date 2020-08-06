---
title: Strumenti per la risoluzione dei problemi di connettività dei pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715555"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="337e0-102">Risoluzione dei problemi relativi alla connettività dei pacchetti degli strumenti</span><span class="sxs-lookup"><span data-stu-id="337e0-102">Troubleshooting Tools Package Connectivity</span></span>
  <span data-ttu-id="337e0-103">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sono disponibili gli strumenti e le caratteristiche per la risoluzione dei problemi relativi alla connettività tra pacchetti e alle origini dati da cui i pacchetti estraggono e caricano i dati.</span><span class="sxs-lookup"><span data-stu-id="337e0-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="337e0-104">Risoluzione dei problemi relativi a provider di dati esterni</span><span class="sxs-lookup"><span data-stu-id="337e0-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="337e0-105">In molti pacchetti si verificano degli errori durante le interazioni con provider di dati esterni.</span><span class="sxs-lookup"><span data-stu-id="337e0-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="337e0-106">Tuttavia, i messaggi restituiti a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dai provider spesso non contengono informazioni sufficienti per risolvere i problemi dell'interazione.</span><span class="sxs-lookup"><span data-stu-id="337e0-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="337e0-107">A questo scopo, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include nuovi messaggi che è possibile utilizzare per risolvere i problemi relativi all'interazione di un pacchetto con origini dati esterne.</span><span class="sxs-lookup"><span data-stu-id="337e0-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="337e0-108">**Abilitare la registrazione e selezionare l'evento Diagnostic del pacchetto per visualizzare i messaggi per la risoluzione dei problemi**.</span><span class="sxs-lookup"><span data-stu-id="337e0-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="337e0-109">Tramite i componenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] seguenti può venire scritto un messaggio nel log prima e dopo ogni chiamata a un provider di dati esterno:</span><span class="sxs-lookup"><span data-stu-id="337e0-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="337e0-110">Gestione connessione OLE DB, origine OLE DB e destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="337e0-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   <span data-ttu-id="337e0-111">Gestione connessione [!INCLUDE[vstecado](../../includes/vstecado-md.md)] e origine ADO NET</span><span class="sxs-lookup"><span data-stu-id="337e0-111">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="337e0-112">Attività Esegui SQL</span><span class="sxs-lookup"><span data-stu-id="337e0-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="337e0-113">Trasformazione Ricerca, trasformazione Comando OLE DB e trasformazione Dimensione a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="337e0-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="337e0-114">I messaggi del log includono il nome del metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="337e0-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="337e0-115">Questi messaggi del log, ad esempio, potrebbero includere il metodo `Open` di un oggetto `Connection` OLE DB o il metodo `ExecuteNonQuery` di un oggetto `Command`.</span><span class="sxs-lookup"><span data-stu-id="337e0-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="337e0-116">I messaggi presentano il formato seguente, dove '%1!s!'</span><span class="sxs-lookup"><span data-stu-id="337e0-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="337e0-117">è un segnaposto per le informazioni sul metodo:</span><span class="sxs-lookup"><span data-stu-id="337e0-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="337e0-118">Per risolvere i problemi relativi all'interazione con il provider di dati esterno, controllare nel log che per ogni messaggio che precede la richiesta (`ExternalRequest_pre`) sia presente un messaggio che la segue (`ExternalRequest_post`).</span><span class="sxs-lookup"><span data-stu-id="337e0-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="337e0-119">Se tale messaggio successivo non è presente, il provider di dati esterno non ha risposto come previsto.</span><span class="sxs-lookup"><span data-stu-id="337e0-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="337e0-120">Di seguito sono riportate alcune righe di esempio di un log contenente questi messaggi di registrazione:</span><span class="sxs-lookup"><span data-stu-id="337e0-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="337e0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="337e0-121">See Also</span></span>  
 <span data-ttu-id="337e0-122">[Risoluzione dei problemi relativi agli strumenti per lo sviluppo dei pacchetti](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="337e0-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="337e0-123">Strumenti per la risoluzione dei problemi relativi all'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="337e0-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
