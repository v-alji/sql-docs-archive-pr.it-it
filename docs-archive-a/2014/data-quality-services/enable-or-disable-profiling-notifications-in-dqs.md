---
title: Abilitare o disabilitare le notifiche di profiling in DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b3b5e8cec1cac3eb1ce4357480c0f994a33d4c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715731"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a><span data-ttu-id="63e2a-102">Abilitare o disabilitare le notifiche di profiling in DQS</span><span class="sxs-lookup"><span data-stu-id="63e2a-102">Enable or Disable Profiling Notifications in DQS</span></span>
  <span data-ttu-id="63e2a-103">In questo argomento viene descritto come abilitare o disabilitare le notifiche di profiling in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="63e2a-103">This topic describes how to enable or disable profiling notifications in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="63e2a-104">Per impostazione predefinita, le notifiche di profiling in DQS sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="63e2a-104">By default, profiling notifications are enabled in DQS.</span></span> <span data-ttu-id="63e2a-105">Le notifiche di profiling forniscono informazioni importanti sull'origine dati e sull'efficacia dell'attività corrente in esecuzione sui dati.</span><span class="sxs-lookup"><span data-stu-id="63e2a-105">Profiling notifications tell you important facts about the data source and the effectiveness of the current activity performed on the data.</span></span> <span data-ttu-id="63e2a-106">Per altre informazioni, vedere [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="63e2a-106">For more information, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63e2a-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="63e2a-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63e2a-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="63e2a-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63e2a-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="63e2a-109">Permissions</span></span>  
 <span data-ttu-id="63e2a-110">Per abilitare le notifiche, è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="63e2a-110">You must have the dqs_administrator role on the DQS_MAIN database to enable notifications.</span></span>  
  
##  <a name="enable-or-disable-profiling-notifications"></a><a name="Enable"></a><span data-ttu-id="63e2a-111">Abilitare o disabilitare le notifiche di profiling</span><span class="sxs-lookup"><span data-stu-id="63e2a-111">Enable or Disable Profiling Notifications</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="63e2a-112">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="63e2a-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="63e2a-113">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="63e2a-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="63e2a-114">Fare clic sulla scheda **Impostazioni generali** .</span><span class="sxs-lookup"><span data-stu-id="63e2a-114">Next, click the **General Settings** tab.</span></span>  
  
4.  <span data-ttu-id="63e2a-115">Deselezionare o selezionare la casella di controllo **Abilita notifiche** per disabilitare o abilitare le notifiche di profiling per le varie attività in DQS.</span><span class="sxs-lookup"><span data-stu-id="63e2a-115">Clear or select the **Enable Notifications** check box to disable or enable profiling notifications for various activities in DQS.</span></span>  
  
5.  <span data-ttu-id="63e2a-116">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="63e2a-116">Click **Close**.</span></span>  
  
  
