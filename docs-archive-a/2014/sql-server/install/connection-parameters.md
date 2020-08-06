---
title: Parametri di connessione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626489"
---
# <a name="connection-parameters"></a><span data-ttu-id="0b197-102">Parametri di connessione</span><span class="sxs-lookup"><span data-stu-id="0b197-102">Connection Parameters</span></span>
  <span data-ttu-id="0b197-103">Per analizzare determinati tipi di server, ad esempio il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], è necessario selezionare un'istanza specifica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b197-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0b197-104">Viene automaticamente selezionata l'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b197-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="0b197-105">È possibile modificare questa selezione, selezionando però solo un'istanza alla volta per l'analisi da Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0b197-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="0b197-106">Se è stato incluso un tipo di server che richiede l'autenticazione, è necessario immettere la modalità di autenticazione e le credenziali.</span><span class="sxs-lookup"><span data-stu-id="0b197-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0b197-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0b197-107">Options</span></span>  
 <span data-ttu-id="0b197-108">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="0b197-108">**Server name**</span></span>  
 <span data-ttu-id="0b197-109">Questo campo viene prepopolato con il nome del computer immesso nel riquadro Componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b197-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="0b197-110">**Nome istanza**</span><span class="sxs-lookup"><span data-stu-id="0b197-110">**Instance name**</span></span>  
 <span data-ttu-id="0b197-111">Selezionare una delle istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="0b197-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="0b197-112">Se l'elenco di istanze non viene visualizzato, utilizzare MSSQLSERVER per analizzare l'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="0b197-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="0b197-113">Ciò riguarda soprattutto i computer remoti.</span><span class="sxs-lookup"><span data-stu-id="0b197-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="0b197-114">È anche possibile utilizzare l'espressione "valore predefinito" per analizzare l'istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="0b197-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="0b197-115">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="0b197-115">**Authentication**</span></span>  
 <span data-ttu-id="0b197-116">Selezionare una delle modalità di autenticazione disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="0b197-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="0b197-117">Per impostazione predefinita, la modalità di autenticazione è l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="0b197-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="0b197-118">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="0b197-118">**User name**</span></span>  
 <span data-ttu-id="0b197-119">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], immettere un nome utente nella casella.</span><span class="sxs-lookup"><span data-stu-id="0b197-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="0b197-120">È consigliabile che il nome utente disponga delle credenziali amministrative nel computer.</span><span class="sxs-lookup"><span data-stu-id="0b197-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b197-121">Se si seleziona l'autenticazione di Windows, il nome utente dell'utente attualmente connesso viene popolato nella casella di testo **nome utente** .</span><span class="sxs-lookup"><span data-stu-id="0b197-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="0b197-122">**Password**</span><span class="sxs-lookup"><span data-stu-id="0b197-122">**Password**</span></span>  
 <span data-ttu-id="0b197-123">Immettere la password per l'utente specificato.</span><span class="sxs-lookup"><span data-stu-id="0b197-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b197-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b197-124">See Also</span></span>  
 <span data-ttu-id="0b197-125">[Utilizzo di preparazione aggiornamento](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0b197-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="0b197-126">Guida di riferimento all'interfaccia utente di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0b197-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
