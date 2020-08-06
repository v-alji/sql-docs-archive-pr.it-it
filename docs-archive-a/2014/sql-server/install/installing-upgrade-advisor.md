---
title: Installazione di preparazione aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713727"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="d8ad8-102">Installazione di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d8ad8-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="d8ad8-103">Il computer in cui installare Preparazione aggiornamento a SQL Server 2014 dipende dai componenti che verranno analizzati.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="d8ad8-104">Preparazione aggiornamento supporta l'analisi remota di tutti i componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8ad8-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="d8ad8-105">Se non si stanno analizzando le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , è possibile installare Preparazione aggiornamento in qualsiasi computer in grado di connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che soddisfi i [prerequisiti di preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d8ad8-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="d8ad8-106">Se si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario installare Preparazione aggiornamento nel server di report.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="d8ad8-107">Eseguire il file di **SQLUA.msi** per installare Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="d8ad8-108">È possibile eseguire l'installazione dal prompt dei comandi per installazioni automatiche e automatizzate.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="d8ad8-109">Per la sintassi e gli esempi, vedere [installazione di preparazione aggiornamento dal prompt dei comandi](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) .</span><span class="sxs-lookup"><span data-stu-id="d8ad8-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="d8ad8-110">Ottenere SQLUA.msi:</span><span class="sxs-lookup"><span data-stu-id="d8ad8-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="d8ad8-111">Nella cartella **Redist** del supporto del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prodotto.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="d8ad8-112">Come parte del [download del Feature Pack di SQL 2014](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="d8ad8-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="d8ad8-113">Disinstallazione di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d8ad8-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="d8ad8-114">È possibile disinstallare Preparazione aggiornamento utilizzando **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="d8ad8-115">La sintassi del prompt dei comandi supporta anche la rimozione e/o la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="d8ad8-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
