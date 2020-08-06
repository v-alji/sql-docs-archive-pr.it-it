---
title: Modifica file archiviati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716639"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="73795-102">Modificare i file archiviati</span><span class="sxs-lookup"><span data-stu-id="73795-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="73795-103">Prima di poter modificare i file inclusi nel controllo del codice sorgente in genere è necessario estrarli.</span><span class="sxs-lookup"><span data-stu-id="73795-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="73795-104">Tuttavia, è possibile configurare in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] modo che sia possibile modificare i file non estratti. Quando si esegue questa operazione, le modifiche vengono mantenute in memoria fino a quando non si salvano i file.</span><span class="sxs-lookup"><span data-stu-id="73795-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="73795-105">In seguito verrà chiesto di estrarre il file dal controllo del codice di origine.</span><span class="sxs-lookup"><span data-stu-id="73795-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="73795-106">Se si lavora in un team, non è consigliabile consentire modifiche dei file archiviati a meno che il provider del controllo del codice sorgente non supporti estrazioni sia della versione locale sia della versione del server.</span><span class="sxs-lookup"><span data-stu-id="73795-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="73795-107">La maggior parte dei provider non supporta estrazioni della versione locale.</span><span class="sxs-lookup"><span data-stu-id="73795-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="73795-108">In questo caso e se un file archiviato viene modificato, sarà necessario unire manualmente la versione in memoria e la versione del server prima di poter archiviare il file.</span><span class="sxs-lookup"><span data-stu-id="73795-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="73795-109">In questo scenario, le unioni automatiche e assistite dal provider non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="73795-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="73795-110">Per modificare i file archiviati</span><span class="sxs-lookup"><span data-stu-id="73795-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="73795-111">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="73795-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="73795-112">Nella finestra di dialogo **Opzioni** espandere la cartella **source**contro l, quindi fare clic su **ambiente**.</span><span class="sxs-lookup"><span data-stu-id="73795-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="73795-113">Fare clic su **Consenti modifica elementi archiviati**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="73795-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73795-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73795-114">See Also</span></span>  
 <span data-ttu-id="73795-115">[Gestisci archiviazioni](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="73795-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="73795-116">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="73795-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
