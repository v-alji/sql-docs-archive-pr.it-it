---
title: Configurare Posta elettronica di SQL Server Agent per l'uso di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712027"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="e4fff-102">Configurare Posta elettronica di SQL Server Agent per l'utilizzo di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="e4fff-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="e4fff-103">In questo argomento viene illustrato come configurare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per utilizzare Posta elettronica database per inviare notifiche e avvisi in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4fff-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="e4fff-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e4fff-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="e4fff-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e4fff-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="e4fff-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fff-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="e4fff-107">Per configurare SQL Server Agent Mail per l'utilizzo di Posta elettronica database tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4fff-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="e4fff-108">Attività di completamento</span><span class="sxs-lookup"><span data-stu-id="e4fff-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e4fff-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4fff-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="e4fff-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e4fff-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="e4fff-111">Abilitare Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="e4fff-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="e4fff-112">Creare un account di Posta elettronica database per l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e4fff-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="e4fff-113">Creare un profilo di Posta elettronica database per l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent da utilizzare e aggiungere l'utente a **DatabaseMailUserRole** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e4fff-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="e4fff-114">Impostare il profilo come predefinito per il database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e4fff-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e4fff-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e4fff-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e4fff-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e4fff-116">Permissions</span></span>  
 <span data-ttu-id="e4fff-117">Per creare gli account dei profili ed eseguire le stored procedure è necessario che l'utente sia un membro del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="e4fff-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e4fff-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e4fff-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e4fff-119">**Per configurare SQL Server Agent Mail per l'utilizzo di Posta elettronica database**</span><span class="sxs-lookup"><span data-stu-id="e4fff-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="e4fff-120">In Esplora oggetti espandere un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4fff-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="e4fff-121">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e4fff-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="e4fff-122">Fare clic su **Sistema avvisi**.</span><span class="sxs-lookup"><span data-stu-id="e4fff-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="e4fff-123">Selezionare **Attiva profilo di posta**.</span><span class="sxs-lookup"><span data-stu-id="e4fff-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="e4fff-124">Nell'elenco **Sistema di posta elettronica** selezionare **Posta elettronica database**.</span><span class="sxs-lookup"><span data-stu-id="e4fff-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="e4fff-125">Selezionare un profilo di posta elettronica per Posta elettronica database nell'elenco **Profilo posta**.</span><span class="sxs-lookup"><span data-stu-id="e4fff-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="e4fff-126">Riavviare SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="e4fff-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a><span data-ttu-id="e4fff-127">Attività di completamento</span><span class="sxs-lookup"><span data-stu-id="e4fff-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="e4fff-128">Le attività seguenti sono necessarie per completare la configurazione dell'agent per inviare avvisi e notifiche.</span><span class="sxs-lookup"><span data-stu-id="e4fff-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="e4fff-129">Avvisi</span><span class="sxs-lookup"><span data-stu-id="e4fff-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="e4fff-130">Gli avvisi possono essere configurati per segnalare a un operatore un evento di database o una condizione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e4fff-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="e4fff-131">Operatori</span><span class="sxs-lookup"><span data-stu-id="e4fff-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="e4fff-132">Gli operatori solo alias di persone o gruppi che possono ricevere notifiche elettroniche</span><span class="sxs-lookup"><span data-stu-id="e4fff-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
