---
title: Ripristinare un'installazione di Riesecuzione distribuita | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6fcd8ca8-1ceb-457d-9545-096c74e274d7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 57f5b2bde308e48dbf14b52a8b159b30f6a98bc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635354"
---
# <a name="repair-a-distributed-replay-installation"></a><span data-ttu-id="16ae2-102">Ripristinare un'installazione di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="16ae2-102">Repair a Distributed Replay Installation</span></span>
  <span data-ttu-id="16ae2-103">Il ripristino di un componente Riesecuzione distribuita (controller o client) comporta le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16ae2-103">Repairing a Distributed Replay component (controller or client) will do the following:</span></span>  
  
1.  <span data-ttu-id="16ae2-104">Installare tutti i file associati sul disco e sostituire tutti i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="16ae2-104">Install all associated files on disk again, and replace any existing files.</span></span>  
  
2.  <span data-ttu-id="16ae2-105">Ricreare l'account del servizio Windows se l'account corrispondente è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="16ae2-105">Recreate the Windows service account if the corresponding service account was removed.</span></span>  
  
 <span data-ttu-id="16ae2-106">Non è possibile utilizzare l'operazione Ripristina per aggiungere o rimuovere componenti.</span><span class="sxs-lookup"><span data-stu-id="16ae2-106">You cannot use the Repair operation to add or remove components.</span></span> <span data-ttu-id="16ae2-107">Per aggiungere o rimuovere componenti, selezionare o deselezionare il componente corrispondente nell'albero delle funzionalità nella pagina **Selezione funzionalità** del programma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installazione.</span><span class="sxs-lookup"><span data-stu-id="16ae2-107">To add or remove components, check or uncheck the corresponding component in the Feature tree on the **Feature Selection** page in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-distributed-replay"></a><span data-ttu-id="16ae2-108">Per ripristinare un'installazione con errori di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="16ae2-108">To repair a failed installation of Distributed Replay</span></span>  
  
1.  <span data-ttu-id="16ae2-109">Dal menu **Start** scegliere **Pannello di controllo**e quindi fare doppio clic su **Installazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="16ae2-109">From the **Start** menu, click **Control Panel**, and then double-click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="16ae2-110">Selezionare [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nella finestra **Disinstalla o modifica programma** , quindi nella finestra di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialogo fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="16ae2-110">Select [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in the **Uninstall or change a program** window, and then in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dialog box, click **Repair**.</span></span>  
  
3.  <span data-ttu-id="16ae2-111">Seguire i passaggi della [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] procedura guidata e nella pagina **Selezione funzionalità** selezionare i componenti riesecuzione distribuita che si desidera ripristinare, quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="16ae2-111">Follow the steps in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wizard, and on the **Select Features** page, select the Distributed Replay components you want to repair, and then click **Next.**.</span></span>  
  
4.  <span data-ttu-id="16ae2-112">Completare l'Installazione guidata di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per ripristinare le funzionalità di Riesecuzione distribuita selezionate.</span><span class="sxs-lookup"><span data-stu-id="16ae2-112">Complete the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Installation Wizard to repair the selected Distributed Replay features.</span></span>  
  
  
