---
title: Gestisci estrazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638028"
---
# <a name="manage-checkouts"></a><span data-ttu-id="9ac98-102">Gestione delle estrazioni</span><span class="sxs-lookup"><span data-stu-id="9ac98-102">Manage Checkouts</span></span>
  <span data-ttu-id="9ac98-103">Dopo aver aggiunto un file al controllo del codice sorgente, prima di poterlo modificare è necessario estrarlo.</span><span class="sxs-lookup"><span data-stu-id="9ac98-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="9ac98-104">Quando un file viene estratto dal controllo del codice sorgente, il provider del controllo del codice sorgente crea una copia dell'ultima versione sul disco locale e rimuove l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="9ac98-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="9ac98-105">In alcuni casi potrebbe essere necessario modificare un file senza estrarlo.</span><span class="sxs-lookup"><span data-stu-id="9ac98-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="9ac98-106">Per ulteriori informazioni sulla modifica di un file senza estrarlo, vedere [modifica di file archiviati](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="9ac98-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="9ac98-107">È possibile usare [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per estrarre i file manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9ac98-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="9ac98-108">Per estrarre i file manualmente, aprire la soluzione che contiene i file nell' [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] ambiente, quindi fare clic sul comando **Estrai** .</span><span class="sxs-lookup"><span data-stu-id="9ac98-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="9ac98-109">Per estrarli automaticamente, è necessario configurare l'ambiente [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ac98-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="9ac98-110">In base alle opzioni impostate dall'amministratore nel provider del controllo del codice sorgente, è possibile estrarre i file anche in modalità esclusiva o condivisa.</span><span class="sxs-lookup"><span data-stu-id="9ac98-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="9ac98-111">Quando si estrae un file in modalità esclusiva, solo l'utente che ha eseguito l'estrazione può modificarlo. Il file non può essere estratto da altri utenti finché non viene archiviato.</span><span class="sxs-lookup"><span data-stu-id="9ac98-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="9ac98-112">Quando si estrae un file in modalità condivisa, esso può essere estratto da qualsiasi numero di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="9ac98-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="9ac98-113">Quando ogni utente archivia il file, il provider del controllo del codice sorgente tenta di unirlo con l'ultima versione del server del file.</span><span class="sxs-lookup"><span data-stu-id="9ac98-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="9ac98-114">In caso di conflitto tra la versione che viene archiviata e l'ultima versione, il provider del controllo del codice sorgente chiede all'utente di risolverlo.</span><span class="sxs-lookup"><span data-stu-id="9ac98-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="9ac98-115">Gli argomenti disponibili in questa sezione sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9ac98-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="9ac98-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="9ac98-116">Topic</span></span>|<span data-ttu-id="9ac98-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ac98-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9ac98-118">Estrazione di file</span><span class="sxs-lookup"><span data-stu-id="9ac98-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="9ac98-119">Vengono fornite istruzioni su come estrarre un file per poterlo modificare.</span><span class="sxs-lookup"><span data-stu-id="9ac98-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="9ac98-120">Annullare estrazioni</span><span class="sxs-lookup"><span data-stu-id="9ac98-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="9ac98-121">Viene spiegato come annullare un'estrazione esistente.</span><span class="sxs-lookup"><span data-stu-id="9ac98-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="9ac98-122">Estrarre automaticamente i file al momento della modifica</span><span class="sxs-lookup"><span data-stu-id="9ac98-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="9ac98-123">Viene spiegato come configurare il controllo del codice sorgente per estrarre un file quando si inizia a modificarlo.</span><span class="sxs-lookup"><span data-stu-id="9ac98-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ac98-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ac98-124">See Also</span></span>  
 <span data-ttu-id="9ac98-125">[Gestisci archiviazioni](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="9ac98-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="9ac98-126">Modificare i file archiviati</span><span class="sxs-lookup"><span data-stu-id="9ac98-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
