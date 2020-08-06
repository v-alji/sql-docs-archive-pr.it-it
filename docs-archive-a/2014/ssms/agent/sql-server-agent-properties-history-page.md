---
title: Proprietà SQL Server Agent (pagina Cronologia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636517"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="1586f-102">Proprietà SQL Server Agent (pagina Cronologia)</span><span class="sxs-lookup"><span data-stu-id="1586f-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="1586f-103">Utilizzare questa pagina per visualizzare e modificare le impostazioni per la gestione del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log della cronologia del servizio Agent.</span><span class="sxs-lookup"><span data-stu-id="1586f-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1586f-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1586f-104">Options</span></span>  
 <span data-ttu-id="1586f-105">**Limita dimensioni log cronologia processo**</span><span class="sxs-lookup"><span data-stu-id="1586f-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="1586f-106">Consente di impostare limiti sulla quantità di informazioni sulla cronologia processo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene nel log.</span><span class="sxs-lookup"><span data-stu-id="1586f-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="1586f-107">**Dimensioni massime log cronologia processo (righe)**</span><span class="sxs-lookup"><span data-stu-id="1586f-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="1586f-108">Consente di impostare il numero massimo di righe che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene nel log.</span><span class="sxs-lookup"><span data-stu-id="1586f-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="1586f-109">Quando il log raggiunge dimensioni tali da contenere questo numero di righe, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rimuove le righe meno recenti per consentire l'inserimento delle nuove.</span><span class="sxs-lookup"><span data-stu-id="1586f-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="1586f-110">**Numero massimo di righe di cronologia per processo**</span><span class="sxs-lookup"><span data-stu-id="1586f-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="1586f-111">Consente di impostare il numero massimo di righe che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene per ogni processo.</span><span class="sxs-lookup"><span data-stu-id="1586f-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="1586f-112">Quando la cronologia di un determinato processo si estende fino a contenere questo numero di righe, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consente di rimuovere le righe meno recenti per consentire l'inserimento delle nuove.</span><span class="sxs-lookup"><span data-stu-id="1586f-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="1586f-113">**Rimuovi cronologia dell'agente**</span><span class="sxs-lookup"><span data-stu-id="1586f-113">**Remove agent history**</span></span>  
 <span data-ttu-id="1586f-114">Viene indicato che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consentirà di rimuovere le voci presenti nel log da più tempo rispetto a quanto specificato.</span><span class="sxs-lookup"><span data-stu-id="1586f-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="1586f-115">Si tratta di un'esecuzione singola che consente di rimuovere la cronologia.</span><span class="sxs-lookup"><span data-stu-id="1586f-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="1586f-116">Se è necessario un processo ricorrente, creare e pianificare un piano di manutenzione con un processo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="1586f-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="1586f-117">**Più vecchia di**</span><span class="sxs-lookup"><span data-stu-id="1586f-117">**Older than**</span></span>  
 <span data-ttu-id="1586f-118">Consente di impostare il periodo di tempo per cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent manterrà le voci.</span><span class="sxs-lookup"><span data-stu-id="1586f-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1586f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1586f-119">See Also</span></span>  
 [<span data-ttu-id="1586f-120">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="1586f-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
