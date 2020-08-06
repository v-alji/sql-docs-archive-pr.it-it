---
title: Configura log degli errori di SQL Server Agent (pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.configure.f1
ms.assetid: e08de622-6f87-470c-aee0-b2d6cb6cca88
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd4c083ea7e7d220d5da20594079b7679c0bb724
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630249"
---
# <a name="configure-sql-server-agent-error-logs-general-page"></a><span data-ttu-id="9ce7b-102">Configura log degli errori di SQL Server Agent (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="9ce7b-102">Configure SQL Server Agent Error Logs (General Page)</span></span>
  <span data-ttu-id="9ce7b-103">Utilizzare questa schermata per visualizzare e aggiornare le impostazioni relative alla registrazione degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-103">Use this screen to view and update settings for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logging.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9ce7b-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9ce7b-104">Options</span></span>  
 <span data-ttu-id="9ce7b-105">**File di log degli errori**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-105">**Error log file**</span></span>  
 <span data-ttu-id="9ce7b-106">Consente di specificare il file in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dovrà scrivere i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-106">Specifies the file to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes error logs.</span></span>  
  
 <span data-ttu-id="9ce7b-107">**...**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-107">**...**</span></span>  
 <span data-ttu-id="9ce7b-108">Consente di individuare i file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-108">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="9ce7b-109">**Scrivi log degli errori OEM**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-109">**Write OEM error log**</span></span>  
 <span data-ttu-id="9ce7b-110">Consente di scrivere il file di log degli errori come file non Unicode.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-110">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="9ce7b-111">In questo modo, è possibile ridurre la quantità di spazio su disco utilizzata dal file di log.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-111">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="9ce7b-112">Quando questa opzione è selezionata, è tuttavia possibile che i messaggi contenenti dati Unicode siano più difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-112">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="9ce7b-113">**Errori**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-113">**Errors**</span></span>  
 <span data-ttu-id="9ce7b-114">Nel file di log vengono scritti soltanto gli errori e i messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-114">Writes only errors and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="9ce7b-115">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-115">**Warnings**</span></span>  
 <span data-ttu-id="9ce7b-116">Nel file di log vengono scritti gli avvisi e i messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-116">Writes only warnings and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="9ce7b-117">**Informazioni**</span><span class="sxs-lookup"><span data-stu-id="9ce7b-117">**Information**</span></span>  
 <span data-ttu-id="9ce7b-118">Nel file di log vengono scritti soltanto i messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="9ce7b-118">Writes only informational messages to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce7b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ce7b-119">See Also</span></span>  
 [<span data-ttu-id="9ce7b-120">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="9ce7b-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
