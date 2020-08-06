---
title: Eseguire l'applicazione Data Quality Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726291"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="059e3-102">Eseguire l'applicazione client Data Quality</span><span class="sxs-lookup"><span data-stu-id="059e3-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="059e3-103">È possibile utilizzare [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) eseguendo il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] e accedendo a un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="059e3-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="059e3-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="059e3-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="059e3-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="059e3-105">Prerequisites</span></span>  
 <span data-ttu-id="059e3-106">È necessario aver completato l'installazione di [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] tramite l'esecuzione del file DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="059e3-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="059e3-107">Per altre informazioni, vedere [Eseguire DQSInstaller.exe per completare l'installazione del server DQS](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="059e3-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="059e3-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="059e3-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="059e3-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="059e3-109">Permissions</span></span>  
 <span data-ttu-id="059e3-110">Per potere accedere al [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], è necessario disporre di uno dei tre ruoli DQS (dqs_adminstrator, dqs_kb_editor o dqs_kb_operator) concessi per il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="059e3-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="059e3-111">Esegui Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="059e3-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="059e3-112">Per eseguire il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] nel computer in cui è stato installato, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="059e3-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="059e3-113">Fare clic su **Start**, puntare **Tutti i programmi**, fare clic su **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, su **Data Quality Services**, quindi su **Client Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="059e3-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="059e3-114">Nella finestra di dialogo **Connetti al server**:</span><span class="sxs-lookup"><span data-stu-id="059e3-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="059e3-115">Specificare il server a cui si desidera connettere l'applicazione [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="059e3-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="059e3-116">Selezionare **(LOCAL)** per connettersi al [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="059e3-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="059e3-117">È anche possibile fare clic sulla freccia in giù e selezionare **\<Browse network for more servers>** per connettersi a un server diverso (o per connettersi al server locale in base al nome).</span><span class="sxs-lookup"><span data-stu-id="059e3-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="059e3-118">Verrà visualizzata la finestra di dialogo **Cerca server** .</span><span class="sxs-lookup"><span data-stu-id="059e3-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="059e3-119">È possibile selezionare un server nella scheda **Server locali** o nella scheda **Server di rete** .</span><span class="sxs-lookup"><span data-stu-id="059e3-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="059e3-120">Se si desidera crittografare il trasferimento dei dati tra il [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], fare clic su **Opzioni** e quindi selezionare la casella di controllo **Crittografa connessione**.</span><span class="sxs-lookup"><span data-stu-id="059e3-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="059e3-121">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="059e3-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="059e3-122">Verrà visualizzata la schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="059e3-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="059e3-123">Per altre informazioni, vedere [Schermata iniziale del client Data Quality](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="059e3-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  
