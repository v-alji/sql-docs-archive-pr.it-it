---
title: Aprire Monitoraggio attività (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723719"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="5fad9-102">Aprire Monitoraggio attività (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5fad9-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5fad9-103">In questo argomento viene descritto come aprire Monitoraggio attività per ottenere informazioni sui processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e sul modo in cui questi processi influiscono sull'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fad9-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5fad9-104">Viene inoltre descritto come impostare l'intervallo di aggiornamento del Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="5fad9-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="5fad9-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5fad9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5fad9-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5fad9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5fad9-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5fad9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5fad9-108">**Per aprire il Monitoraggio attività:**</span><span class="sxs-lookup"><span data-stu-id="5fad9-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="5fad9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fad9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="5fad9-110">**Per impostare l'intervallo di aggiornamento usando:**  [SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="5fad9-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5fad9-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5fad9-111">Before You Begin</span></span>  
 <span data-ttu-id="5fad9-112">Monitoraggio attività esegue query sull'istanza monitorata per ottenere informazioni per i riquadri di visualizzazione di Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="5fad9-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="5fad9-113">Quando l'intervallo di aggiornamento viene impostato su un valore inferiore a 10 secondi, il tempo utilizzato per eseguire queste query può ridurre le prestazioni del server</span><span class="sxs-lookup"><span data-stu-id="5fad9-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5fad9-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5fad9-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5fad9-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5fad9-115">Permissions</span></span>  
 <span data-ttu-id="5fad9-116">Per visualizzare Monitoraggio attività, è necessario che l'utente disponga dell'autorizzazione VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="5fad9-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="5fad9-117">Per visualizzare la sezione I/O dati di file di Monitoraggio attività, è necessario disporre delle autorizzazioni CREATE DATABASE, ALTER ANY DATABASE, o VIEW ANY DEFINITION oltre a VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="5fad9-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="5fad9-118">Per eseguire il comando KILL in un processo, è necessario che l'utente sia un membro del ruolo predefinito del server sysadmin o processadmin.</span><span class="sxs-lookup"><span data-stu-id="5fad9-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5fad9-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fad9-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="5fad9-120">Per aprire Monitoraggio attività in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fad9-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5fad9-121">Nella barra degli strumenti standard di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fare clic su **Monitoraggio attività**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="5fad9-122">Nella finestra di dialogo **Connetti al server** selezionare il nome del server e la modalità di autenticazione, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="5fad9-123">È inoltre possibile aprire Monitoraggio attività in qualsiasi momento premendo CTRL+ALT A.</span><span class="sxs-lookup"><span data-stu-id="5fad9-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="5fad9-124">Per aprire Monitoraggio attività in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="5fad9-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="5fad9-125">In Esplora oggetti fare clic con il pulsante destro del mouse sul nome dell'istanza, quindi scegliere **Monitoraggio attività**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="5fad9-126">Per aprire Monitoraggio attività all'apertura di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5fad9-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5fad9-127">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="5fad9-128">Nella finestra di dialogo **Opzioni** espandere **Ambiente**, quindi selezionare **Generale**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="5fad9-129">Nella casella **All'avvio** selezionare **Apri Esplora oggetti e Monitoraggio attività**.</span><span class="sxs-lookup"><span data-stu-id="5fad9-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="5fad9-130">Per attivare le modifiche, chiudere e riaprire [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fad9-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="5fad9-131">Per impostare l'intervallo di aggiornamento di monitoraggio attività</span><span class="sxs-lookup"><span data-stu-id="5fad9-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="5fad9-132">Aprire il Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="5fad9-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="5fad9-133">Fare clic con il pulsante destro del mouse su **Panoramica**, selezionare **Intervallo di aggiornamento**, quindi selezionare l'intervallo con cui Monitoraggio attività deve ottenere nuove informazioni sull'istanza.</span><span class="sxs-lookup"><span data-stu-id="5fad9-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
