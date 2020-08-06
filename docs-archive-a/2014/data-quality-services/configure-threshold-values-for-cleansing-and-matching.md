---
title: Configurare valori soglia per le attività di pulizia e di individuazione delle corrispondenze | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.general.f1
helpviewer_keywords:
- cleansing,threshold value
- cleansing threshold values
- matching,threshold value
ms.assetid: d2305409-7115-45a4-8f60-1213c0a47368
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0faf64e96468a3a9aac0de12d3ec3acbb1e1ed85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712403"
---
# <a name="configure-threshold-values-for-cleansing-and-matching"></a><span data-ttu-id="a5d12-102">Configurazione dei valori soglia per le attività di pulizia e di individuazione delle corrispondenze</span><span class="sxs-lookup"><span data-stu-id="a5d12-102">Configure Threshold Values for Cleansing and Matching</span></span>
  <span data-ttu-id="a5d12-103">In questo argomento viene descritto come configurare valori soglia che verranno utilizzati durante le attività computerizzate di pulizia e di individuazione delle corrispondenze in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a5d12-103">This topic describes how to configure threshold values that will be used during the computer-assisted cleansing and matching activities in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5d12-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a5d12-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5d12-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a5d12-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a5d12-106">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a5d12-106">Permissions</span></span>  
 <span data-ttu-id="a5d12-107">Per configurare i valori soglia è necessario disporre del ruolo dqs_administrator per il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a5d12-107">You must have the dqs_administrator role on the DQS_MAIN database to configure these threshold values.</span></span>  
  
##  <a name="configuring-the-threshold-values"></a><a name="Configure"></a> <span data-ttu-id="a5d12-108">Configurazione dei valori soglia</span><span class="sxs-lookup"><span data-stu-id="a5d12-108">Configuring the Threshold Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a5d12-109">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5d12-109">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a5d12-110">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a5d12-110">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="a5d12-111">Fare quindi clic sulla scheda **Impostazioni generali** . Questa scheda consente di specificare valori soglia per le attività di pulizia e di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="a5d12-111">Next, click the **General Settings** tab. This tab enables you to specify threshold values for cleansing as well as matching activities.</span></span>  
  
4.  <span data-ttu-id="a5d12-112">Per specificare valori soglia per l'attività di pulizia, specificare valori adatti nelle caselle seguenti nell'area **Pulizia interattiva** :</span><span class="sxs-lookup"><span data-stu-id="a5d12-112">To specify threshold values for the cleansing activity, specify appropriate values in the following boxes under the **Interactive Cleansing** area:</span></span>  
  
    -   <span data-ttu-id="a5d12-113">**Punteggio minimo per suggerimenti**: il punteggio minimo o livello di confidenza che verrà utilizzato in DQS per suggerire sostituzioni per un valore durante il processo di pulizia computerizzato.</span><span class="sxs-lookup"><span data-stu-id="a5d12-113">**Min score for suggestions**: The minimum score or the confidence level that will be used by DQS for suggesting replacements for a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="a5d12-114">Immettere un valore nella notazione decimale del valore percentuale corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a5d12-114">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="a5d12-115">Ad esempio, digitare 0,75 per 75%.</span><span class="sxs-lookup"><span data-stu-id="a5d12-115">For example, type 0.75 for 75%.</span></span> <span data-ttu-id="a5d12-116">Questo valore deve essere minore o uguale al valore specificato nella casella **Punteggio minimo per correzioni automatiche** .</span><span class="sxs-lookup"><span data-stu-id="a5d12-116">This value should be less than or equal to the value specified in the **Min score for auto corrections** box.</span></span> <span data-ttu-id="a5d12-117">Il valore predefinito è 0,7.</span><span class="sxs-lookup"><span data-stu-id="a5d12-117">The default value is 0.7.</span></span>  
  
    -   <span data-ttu-id="a5d12-118">**Punteggio minimo per correzioni automatiche**: il punteggio minimo o livello di confidenza che verrà utilizzato in DQS per correggere automaticamente un valore durante il processo di pulizia computerizzato.</span><span class="sxs-lookup"><span data-stu-id="a5d12-118">**Min score for auto corrections**: The minimum score or the confidence level that will be used by DQS for automatically correcting a value during the computer-assisted cleansing process.</span></span> <span data-ttu-id="a5d12-119">Immettere un valore nella notazione decimale del valore percentuale corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a5d12-119">Enter a value in the decimal notation of the corresponding percentage value.</span></span> <span data-ttu-id="a5d12-120">Ad esempio, digitare 0,9 per 90%.</span><span class="sxs-lookup"><span data-stu-id="a5d12-120">For example, enter 0.9 for 90%.</span></span> <span data-ttu-id="a5d12-121">Il valore predefinito è 0,8.</span><span class="sxs-lookup"><span data-stu-id="a5d12-121">The default value is 0.8.</span></span>  
  
5.  <span data-ttu-id="a5d12-122">Per specificare il valore soglia per l'attività di individuazione delle corrispondenze, specificare un valore nella casella **Punteggio record minimo** nell'area **Corrispondenza** .</span><span class="sxs-lookup"><span data-stu-id="a5d12-122">To specify threshold value for the matching activity, specify a value in the **Min record score** box under the **Matching** area.</span></span> <span data-ttu-id="a5d12-123">Questo valore rappresenta il punteggio minimo per considerare un record come corrispondenza per un altro record.</span><span class="sxs-lookup"><span data-stu-id="a5d12-123">This value signifies the minimum score for a record to be considered as a match for another record.</span></span> <span data-ttu-id="a5d12-124">Il valore predefinito è 80.</span><span class="sxs-lookup"><span data-stu-id="a5d12-124">The default value is 80%.</span></span>  
  
6.  <span data-ttu-id="a5d12-125">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="a5d12-125">Click **Close**.</span></span>  
  
  
