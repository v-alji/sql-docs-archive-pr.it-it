---
title: Microsoft Connector 1,1 per SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721591"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="e8768-102">Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8768-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="e8768-103">Il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW è costituito da un set di tre componenti che consentono di estrarre o caricare dati in un sistema SAP NETWEAVER BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="e8768-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8768-104">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e8768-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e8768-105">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="e8768-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8768-106">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e8768-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="e8768-107">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="e8768-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="e8768-108">Componenti</span><span class="sxs-lookup"><span data-stu-id="e8768-108">Components</span></span>  
 <span data-ttu-id="e8768-109">Il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8768-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="e8768-110">**Origine SAP BW**: l'origine SAP BW è un componente di origine del flusso di dati che consente di estrarre dati da un sistema SAP NetWeaver BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="e8768-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="e8768-111">**Destinazione SAP BW**-la destinazione SAP BW è un componente di destinazione del flusso di dati che consente di caricare i dati in un sistema SAP NetWeaver BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="e8768-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="e8768-112">**Gestione connessione SAP BW**: la gestione connessione SAP BW connette un'origine SAP BW o una destinazione SAP BW a un sistema SAP NetWeaver BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="e8768-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="e8768-113">Per una procedura dettagliata che illustra come configurare e usare la gestione connessione, l'origine e la destinazione SAP BW, vedere il white paper [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897)(Utilizzo dei servizi di integrazione SQL Server con SAP BI 7.0).</span><span class="sxs-lookup"><span data-stu-id="e8768-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="e8768-114">Nel white paper viene anche indicato come configurare gli oggetti necessari in SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8768-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="e8768-115">Documentazione</span><span class="sxs-lookup"><span data-stu-id="e8768-115">Documentation</span></span>  
 <span data-ttu-id="e8768-116">Questo file della Guida per il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW contiene gli argomenti e le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8768-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="e8768-117">Installazione di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8768-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="e8768-118">Descrive i requisiti di installazione per il [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8768-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="e8768-119">Componenti di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8768-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="e8768-120">Descrive ogni componente del [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8768-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="e8768-121">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="e8768-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="e8768-122">Descrive l'interfaccia utente di ogni componente del [!INCLUDE[msCoName](../includes/msconame-md.md)] connettore 1,1 per SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e8768-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
