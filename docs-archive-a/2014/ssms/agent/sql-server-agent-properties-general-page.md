---
title: Proprietà SQL Server Agent (pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636518"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="3eeab-102">Proprietà SQL Server Agent (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="3eeab-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="3eeab-103">Utilizzare questa pagina per visualizzare e modificare le proprietà generali del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servizio Agent.</span><span class="sxs-lookup"><span data-stu-id="3eeab-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3eeab-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3eeab-104">Options</span></span>  
 <span data-ttu-id="3eeab-105">**Stato del servizio**</span><span class="sxs-lookup"><span data-stu-id="3eeab-105">**Service state**</span></span>  
 <span data-ttu-id="3eeab-106">Visualizza lo stato corrente del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3eeab-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="3eeab-107">**Riavvia automaticamente SQL Server in caso di arresto imprevisto**</span><span class="sxs-lookup"><span data-stu-id="3eeab-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3eeab-108">Agent esegue il riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando si verifica un arresto imprevisto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3eeab-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="3eeab-109">**Riavvia automaticamente SQL Server Agent in caso di arresto imprevisto**</span><span class="sxs-lookup"><span data-stu-id="3eeab-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3eeab-110">esegue il riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent quando si verifica un arresto imprevisto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3eeab-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="3eeab-111">**Filename**</span><span class="sxs-lookup"><span data-stu-id="3eeab-111">**Filename**</span></span>  
 <span data-ttu-id="3eeab-112">Consente di specificare il nome del file per il log degli errori.</span><span class="sxs-lookup"><span data-stu-id="3eeab-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="3eeab-113">**...**</span><span class="sxs-lookup"><span data-stu-id="3eeab-113">**...**</span></span>  
 <span data-ttu-id="3eeab-114">Consente di individuare i file di log degli errori.</span><span class="sxs-lookup"><span data-stu-id="3eeab-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="3eeab-115">**Includi messaggi di traccia esecuzione**</span><span class="sxs-lookup"><span data-stu-id="3eeab-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="3eeab-116">Consente di includere messaggi di traccia dell'esecuzione nel log degli errori.</span><span class="sxs-lookup"><span data-stu-id="3eeab-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="3eeab-117">Nei messaggi di traccia sono incluse informazioni dettagliate sull'operazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3eeab-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="3eeab-118">Se questa opzione è selezionata, per il file di log sarà necessario ulteriore spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="3eeab-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="3eeab-119">È consigliabile selezionare questa opzione solo durante la risoluzione di un problema che potrebbe coinvolgere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3eeab-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="3eeab-120">**Scrivi file OEM**</span><span class="sxs-lookup"><span data-stu-id="3eeab-120">**Write OEM file**</span></span>  
 <span data-ttu-id="3eeab-121">Consente di scrivere il file di log degli errori come file non Unicode.</span><span class="sxs-lookup"><span data-stu-id="3eeab-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="3eeab-122">In questo modo, è possibile ridurre la quantità di spazio su disco utilizzata dal file di log.</span><span class="sxs-lookup"><span data-stu-id="3eeab-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="3eeab-123">Quando questa opzione è selezionata, è tuttavia possibile che i messaggi contenenti dati Unicode siano più difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="3eeab-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="3eeab-124">**Destinatario Net Send**</span><span class="sxs-lookup"><span data-stu-id="3eeab-124">**Net send recipient**</span></span>  
 <span data-ttu-id="3eeab-125">Consente di digitare il nome dell'operatore destinato a ricevere la notifica Net Send dei messaggi scritti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nel file di log.</span><span class="sxs-lookup"><span data-stu-id="3eeab-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eeab-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eeab-126">See Also</span></span>  
 <span data-ttu-id="3eeab-127">[Operatori](operators.md) </span><span class="sxs-lookup"><span data-stu-id="3eeab-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="3eeab-128">Log degli errori di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="3eeab-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
