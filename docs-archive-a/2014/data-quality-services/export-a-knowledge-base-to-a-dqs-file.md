---
title: Esportare una Knowledge Base in un file DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 81dfc8e7f20fae9dacd521595d101be3117a6794
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625555"
---
# <a name="export-a-knowledge-base-to-a-dqs-file"></a><span data-ttu-id="6c5bd-102">Esportazione di una Knowledge Base in un file DQS</span><span class="sxs-lookup"><span data-stu-id="6c5bd-102">Export a Knowledge Base to a .dqs File</span></span>
  <span data-ttu-id="6c5bd-103">In questo argomento viene descritto come esportare un'intera Knowledge Base in un file di dati con estensione DQS in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="6c5bd-103">This topic describes how to export an entire knowledge base to a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="6c5bd-104">È possibile esportare un dominio o una Knowledge Base intera in un file di dati.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-104">You can export a domain or an entire knowledge base to a data file.</span></span> <span data-ttu-id="6c5bd-105">Per informazioni sull'esportazione di un dominio, vedere [Esportare un dominio in un file DQS](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span><span class="sxs-lookup"><span data-stu-id="6c5bd-105">For information about exporting a domain, see [Export a Domain to a .dqs File](../../2014/data-quality-services/export-a-domain-to-a-dqs-file.md).</span></span>  
  
 <span data-ttu-id="6c5bd-106">L'esportazione di una Knowledge Base in un file con estensione DQS e la successiva importazione in un'altra Knowledge Base semplifica il processo di generazione delle informazioni e consente di risparmiare tempo e impegno.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-106">Exporting a knowledge base to a .dqs file, and then importing it as another knowledge base simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="6c5bd-107">La procedura permette di condividere una Knowledge Base e le relative informazioni con altri utenti.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-107">It enables you to share a knowledge base and its knowledge with others.</span></span> <span data-ttu-id="6c5bd-108">Il file DQS conterrà tutte le informazioni della Knowledge Base, compresi domini e i criteri di corrispondenza, tranne le informazioni sui dati di riferimento collegati.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-108">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="6c5bd-109">È necessario collegare nuovamente i domini richiesti ai servizi dati di riferimento appropriati, se necessario, dopo avere importato il file DQS.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-109">You must attach the required domains to appropriate reference data services again, if required, after importing the .dqs file.</span></span> <span data-ttu-id="6c5bd-110">Vengono esportati sia i dati pubblicati che quelli non pubblicati in una Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-110">Both published and unpublished data in a knowledge base is exported.</span></span>  
  
 <span data-ttu-id="6c5bd-111">Il file di dati DQS creato dal processo di esportazione viene crittografato, pertanto non è possibile visualizzarne i contenuti.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-111">The .dqs data file created by the export process is encrypted, so the contents cannot be viewed.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6c5bd-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6c5bd-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6c5bd-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6c5bd-113">Prerequisites</span></span>  
 <span data-ttu-id="6c5bd-114">Per esportare una Knowledge Base in un file di dati DQS, è necessario avere creato e aperto una Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-114">To export a knowledge base to a .dqs data file, you must have created and opened a knowledge base.</span></span> <span data-ttu-id="6c5bd-115">Non è necessario disporre di un file DQS in cui esportare, in quanto verrà creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-115">You do not need to have a .dqs file to export into; one will be created for you.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6c5bd-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c5bd-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6c5bd-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6c5bd-117">Permissions</span></span>  
 <span data-ttu-id="6c5bd-118">Per esportare una Knowledge Base da un file DQS è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-118">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to export a knowledge base to a .dqs data file.</span></span>  
  
##  <a name="export-a-knowledge-base-to-a-dqs-file"></a><a name="Export"></a><span data-ttu-id="6c5bd-119">Esportare una Knowledge base in un file DQS</span><span class="sxs-lookup"><span data-stu-id="6c5bd-119">Export a knowledge base to a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="6c5bd-120">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="6c5bd-120">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="6c5bd-121">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] aprire una Knowledge Base nell'attività Gestione dominio.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-121">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="6c5bd-122">Nella pagina Gestione dominio (con qualsiasi scheda selezionata), fare clic sull'icona **Esporta dati Knowledge Base** sopra l'elenco di domini, quindi fare clic su **Esporta Knowledge Base**.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-122">In the Domain Management page (with any tab selected), click the **Export Knowledge Base data** icon above the Domain list, and then click **Export Knowledge Base**.</span></span> <span data-ttu-id="6c5bd-123">In alternativa, è possibile fare clic con il pulsante destro del mouse sull'elenco **Dominio** , selezionare **Esporta**, quindi fare clic su **Esporta Knowledge Base**.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-123">Alternatively, you can also right-click in the **Domain** list, hover over **Export**, and then click **Export Knowledge Base**.</span></span>  
  
4.  <span data-ttu-id="6c5bd-124">Nella finestra di dialogo **Esporta in file di dati** spostarsi nella cartella in cui si vuole salvare il file, denominare il file o mantenere il nome della Knowledge Base, mantenere **File di dati DQS (\*.dqs)** in **Salva come** e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-124">In the **Export to Data File** dialog box, move to the folder that you want to save the file in, name the file or keep the knowledge base name, keep **DQS Data Files (\*.dqs)** as the **Save as** type, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="6c5bd-125">Nella finestra di dialogo **Esporta Knowledge Base** verificare che la riga dello stato indichi che l'esportazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-125">In the **Export Knowledge Base** dialog box, verify that the status line indicates that the export completed.</span></span> <span data-ttu-id="6c5bd-126">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-126">Click **OK**.</span></span>  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a><span data-ttu-id="6c5bd-127">Completamento: dopo l'esportazione di un dominio in un file DQS</span><span class="sxs-lookup"><span data-stu-id="6c5bd-127">Follow Up: After Exporting a Domain to a .dqs File</span></span>  
 <span data-ttu-id="6c5bd-128">Una volta esportata una Knowledge Base in un file DQS, è possibile importarla nello stesso [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (con un nuovo nome) o in un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]diverso.</span><span class="sxs-lookup"><span data-stu-id="6c5bd-128">After you export a knowledge base to a .dqs file, you can import the knowledge base into the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (with a new name) or into a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
  
