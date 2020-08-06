---
title: Gestione connessione SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625517"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="8f62c-102">Gestione connessione SAP BW</span><span class="sxs-lookup"><span data-stu-id="8f62c-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="8f62c-103">La gestione connessione SAP BW è il componente per la gestione delle connessioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="8f62c-104">La gestione connessione SAP BW offre la connettività a un sistema SAP Netweaver BW versione 7 di cui hanno bisogno i componenti di origine e destinazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="8f62c-105">L'origine e la destinazione SAP BW che fanno parte del pacchetto di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW sono gli unici componenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che usano la gestione connessione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f62c-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8f62c-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="8f62c-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="8f62c-108">Quando si aggiunge una gestione connessione SAP BW a un pacchetto, la proprietà `ConnectionManagerType` della gestione connessione è impostata su `SAPBI`.</span><span class="sxs-lookup"><span data-stu-id="8f62c-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="8f62c-109">Configurazione della gestione connessione SAP BW</span><span class="sxs-lookup"><span data-stu-id="8f62c-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="8f62c-110">Per configurare la gestione connessione SAP BW, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8f62c-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="8f62c-111">Specificare client, nome utente, password e lingua della connessione.</span><span class="sxs-lookup"><span data-stu-id="8f62c-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="8f62c-112">Scegliere se stabilire la connessione a un server applicazioni singolo o a un gruppo di server con carico bilanciato.</span><span class="sxs-lookup"><span data-stu-id="8f62c-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="8f62c-113">Specificare il numero di sistema e host per un server applicazioni oppure specificare server messaggi, gruppo e SID per un gruppo di server con carico bilanciato.</span><span class="sxs-lookup"><span data-stu-id="8f62c-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="8f62c-114">Abilitare la registrazione personalizzata delle chiamate di funzione RFC per i componenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="8f62c-115">Tale registrazione è separata dalla registrazione facoltativa che è possibile abilitare nei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . Per abilitare la registrazione delle chiamate di funzione RFC, specificare una directory in cui archiviare i file di log creati prima e dopo ogni chiamata di funzione RFC.</span><span class="sxs-lookup"><span data-stu-id="8f62c-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="8f62c-116">Questa funzionalità di registrazione crea molti file di log in formato XML.</span><span class="sxs-lookup"><span data-stu-id="8f62c-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="8f62c-117">Poiché questi file di log contengono anche tutte le righe di dati trasferiti, è possibile che occupino una grande quantità di spazio su disco. Se non si seleziona una directory di log, la registrazione non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="8f62c-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8f62c-118">Se i dati trasferiti contengono informazioni riservate, anche i file di log conterranno tali informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="8f62c-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="8f62c-119">Utilizzare i valori immessi per verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8f62c-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="8f62c-120">Se non si conoscono tutti i valori richiesti per configurare la gestione connessione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="8f62c-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="8f62c-121">Per una procedura dettagliata che illustra come configurare e utilizzare la gestione connessione, l'origine e la destinazione SAP BW, vedere il white paper [Utilizzo dei servizi di integrazione SQL Server 2008 con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="8f62c-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="8f62c-122">Nel white paper viene anche indicato come configurare gli oggetti necessari in SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8f62c-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="8f62c-123">Utilizzo di Progettazione SSIS per configurare l'origine</span><span class="sxs-lookup"><span data-stu-id="8f62c-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="8f62c-124">Per ulteriori informazioni sulle proprietà della gestione connessione SAP BW che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="8f62c-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8f62c-125">Editor gestione connessione SAP BW</span><span class="sxs-lookup"><span data-stu-id="8f62c-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f62c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f62c-126">See Also</span></span>  
 [<span data-ttu-id="8f62c-127">Componenti di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="8f62c-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
