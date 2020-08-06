---
title: Proprietà - SQL Server Browser (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636500"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="16f6e-102">Proprietà - SQL Server Browser (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="16f6e-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="16f6e-103">Il programma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser viene eseguito come servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="16f6e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="16f6e-104">Browser rimane in attesa delle richieste in entrata di risorse di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e fornisce informazioni sulle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="16f6e-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="16f6e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="16f6e-105">Options</span></span>  
 <span data-ttu-id="16f6e-106">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="16f6e-106">**Clustered**</span></span>  
 <span data-ttu-id="16f6e-107">Indica se il servizio è installato come risorsa di un server di cluster.</span><span class="sxs-lookup"><span data-stu-id="16f6e-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="16f6e-108">**Segnalazione commenti e suggerimenti utenti**</span><span class="sxs-lookup"><span data-stu-id="16f6e-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="16f6e-109">Indica se il monitoraggio della qualità del servizio è stato abilitato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="16f6e-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="16f6e-110">Per ulteriori informazioni sulla funzionalità di segnalazione del feedback dei clienti, cercare l'argomento "Impostazioni segnalazione errori e utilizzo funzionalità" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="16f6e-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="16f6e-111">**Directory dump**</span><span class="sxs-lookup"><span data-stu-id="16f6e-111">**Dump Directory**</span></span>  
 <span data-ttu-id="16f6e-112">Posizione in cui vengono memorizzati i dump di memoria in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="16f6e-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="16f6e-113">**Segnalazione errori**</span><span class="sxs-lookup"><span data-stu-id="16f6e-113">**Error Reporting**</span></span>  
 <span data-ttu-id="16f6e-114">Se l'opzione è impostata su **Sì**, il programma Dr. Watson inoltra le informazioni a [!INCLUDE[msCoName](../../includes/msconame-md.md)] o al server interno per la segnalazione degli errori se si verifica un errore grave.</span><span class="sxs-lookup"><span data-stu-id="16f6e-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="16f6e-115">Per ulteriori informazioni sulla funzionalità di segnalazione degli errori, cercare l'argomento "Impostazioni segnalazione errori e utilizzo funzionalità" nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="16f6e-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="16f6e-116">**ID istanza**</span><span class="sxs-lookup"><span data-stu-id="16f6e-116">**Instance ID**</span></span>  
 <span data-ttu-id="16f6e-117">Indica l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ha usato questa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="16f6e-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="16f6e-118">L'istanza predefinita è **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="16f6e-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f6e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16f6e-119">See Also</span></span>  
 [<span data-ttu-id="16f6e-120">Servizio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="16f6e-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
