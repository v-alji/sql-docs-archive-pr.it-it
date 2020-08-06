---
title: Installazione di preparazione aggiornamento dal prompt dei comandi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- command prompt [Upgrade Advisor]
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: a6841cc2-ca13-4b1c-9343-9e4d54312c3a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b0c5193f0b235b6d37170992d9d7ca9568b1f675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713724"
---
# <a name="installing-upgrade-advisor-from-the-command-prompt"></a><span data-ttu-id="9e25c-102">Installazione di Preparazione aggiornamento dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="9e25c-102">Installing Upgrade Advisor from the Command Prompt</span></span>
  <span data-ttu-id="9e25c-103">È possibile installare Preparazione aggiornamento utilizzando l'Installazione guidata o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9e25c-103">You can install Upgrade Advisor either by using the Setup Wizard or from the command prompt.</span></span> <span data-ttu-id="9e25c-104">Il prompt dei comandi consente di eseguire installazioni automatiche e automatizzate.</span><span class="sxs-lookup"><span data-stu-id="9e25c-104">By using the command prompt you can perform unattended and automated installations.</span></span>  
  
## <a name="installation-syntax"></a><span data-ttu-id="9e25c-105">Sintassi dell'installazione</span><span class="sxs-lookup"><span data-stu-id="9e25c-105">Installation Syntax</span></span>  
 <span data-ttu-id="9e25c-106">La sintassi di base per l'installazione di Preparazione aggiornamento dal prompt dei comandi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9e25c-106">The basic syntax for installing Upgrade Advisor from the command prompt is as follows:</span></span>  
  
 `SQLUA.msi [options]`  
  
 <span data-ttu-id="9e25c-107">Nella tabella seguente vengono illustrate le opzioni più comuni.</span><span class="sxs-lookup"><span data-stu-id="9e25c-107">The following table shows the most common options.</span></span>  
  
|<span data-ttu-id="9e25c-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="9e25c-108">Argument</span></span>|<span data-ttu-id="9e25c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e25c-109">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9e25c-110">/q [n&#124;b&#124;r&#124;f]</span><span class="sxs-lookup"><span data-stu-id="9e25c-110">/q[n&#124;b&#124;r&#124;f]</span></span>|<span data-ttu-id="9e25c-111">Imposta il livello dell'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="9e25c-111">Sets user interface (UI) level:</span></span><br /><br /> <span data-ttu-id="9e25c-112">n = nessuna interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9e25c-112">n = no UI</span></span><br /><br /> <span data-ttu-id="9e25c-113">b = interfaccia utente di base (solo stato di avanzamento, nessun prompt)</span><span class="sxs-lookup"><span data-stu-id="9e25c-113">b = basic UI (progress only, no prompts)</span></span><br /><br /> <span data-ttu-id="9e25c-114">r = interfaccia utente ridotta (finestra di dialogo alla fine dell'installazione)</span><span class="sxs-lookup"><span data-stu-id="9e25c-114">r = reduced UI (dialog box at the end of installation)</span></span><br /><br /> <span data-ttu-id="9e25c-115">f = interfaccia utente completa</span><span class="sxs-lookup"><span data-stu-id="9e25c-115">f = full UI</span></span>|  
|<span data-ttu-id="9e25c-116">/L</span><span class="sxs-lookup"><span data-stu-id="9e25c-116">/L</span></span>|<span data-ttu-id="9e25c-117">Specifica le opzioni del file di log.</span><span class="sxs-lookup"><span data-stu-id="9e25c-117">Specifies log file options.</span></span> <span data-ttu-id="9e25c-118">Per registrare tutti i messaggi in *log_file_name*, usare **-L \* v**_log_file_name_.</span><span class="sxs-lookup"><span data-stu-id="9e25c-118">To log all messages to *log_file_name*, use **-L\*v**_log_file_name_.</span></span> <span data-ttu-id="9e25c-119">Per registrare solo i messaggi di errore, utilizzare `-Le` *log_file_name*.</span><span class="sxs-lookup"><span data-stu-id="9e25c-119">To log error messages only, use `-Le`*log_file_name*.</span></span>|  
|<span data-ttu-id="9e25c-120">ADDLOCAL = ALL&#124; REMOVE = ALL&#124;REINSTALL = ALL</span><span class="sxs-lookup"><span data-stu-id="9e25c-120">ADDLOCAL=ALL&#124; REMOVE=ALL&#124;REINSTALL=ALL</span></span>|<span data-ttu-id="9e25c-121">Specifica se installare (ADDLOCAL), rimuovere (REMOVE) o reinstallare (REINSTALL) Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="9e25c-121">Specifies to install (ADDLOCAL), remove (REMOVE), or reinstall (REINSTALL) Upgrade Advisor.</span></span>|  
|<span data-ttu-id="9e25c-122">UAINSTALLDIR=path</span><span class="sxs-lookup"><span data-stu-id="9e25c-122">UAINSTALLDIR=path</span></span>|<span data-ttu-id="9e25c-123">Installa Preparazione aggiornamento nel percorso specificato da path.</span><span class="sxs-lookup"><span data-stu-id="9e25c-123">Installs Upgrade Advisor to the location specified by path.</span></span>|  
  
## <a name="installation-examples"></a><span data-ttu-id="9e25c-124">Esempi dell'installazione</span><span class="sxs-lookup"><span data-stu-id="9e25c-124">Installation Examples</span></span>  
 <span data-ttu-id="9e25c-125">Nell'esempio seguente viene illustrato come installare Preparazione aggiornamento dal prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="9e25c-125">The following example shows how to install Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="9e25c-126">È anche possibile utilizzare il programma Msiexec quando si esegue questo comando:</span><span class="sxs-lookup"><span data-stu-id="9e25c-126">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn ADDLOCAL=ALL UAINSTALLDIR="C:\Upgrade Advisor"  
```  
  
 <span data-ttu-id="9e25c-127">Questa soluzione può risultare utile se è necessario utilizzare opzioni di installazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="9e25c-127">This can be helpful if you have to use additional installation options.</span></span>  
  
## <a name="removal-examples"></a><span data-ttu-id="9e25c-128">Esempi di rimozione</span><span class="sxs-lookup"><span data-stu-id="9e25c-128">Removal Examples</span></span>  
 <span data-ttu-id="9e25c-129">Nell'esempio seguente viene illustrato come rimuovere Preparazione aggiornamento dal prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="9e25c-129">The following example shows how to remove Upgrade Advisor by using the command prompt:</span></span>  
  
```  
SQLUA.msi /qn REMOVE=ALL  
```  
  
 <span data-ttu-id="9e25c-130">È anche possibile utilizzare il programma Msiexec quando si esegue questo comando:</span><span class="sxs-lookup"><span data-stu-id="9e25c-130">You can also use the Msiexec program when you run this command:</span></span>  
  
```  
Msiexec.exe /i C:\Downloads\SQLUA.msi /qn REMOVE=ALL  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e25c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e25c-131">See Also</span></span>  
 <span data-ttu-id="9e25c-132">[Installazione di preparazione aggiornamento](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="9e25c-132">[Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="9e25c-133">Prerequisiti di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="9e25c-133">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
