---
title: Escludere file dal controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- excluding files from source control
- source controls [SQL Server Management Studio], file exclusions
ms.assetid: 7dcb6514-db5c-49eb-8b5a-2c766ce39aa7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9fb3c5ccb4fcaad062236eec6d04f995557dc2b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716620"
---
# <a name="exclude-files-from-source-control"></a><span data-ttu-id="3da86-102">Esclusione di file dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3da86-102">Exclude Files from Source Control</span></span>
  <span data-ttu-id="3da86-103">Se la soluzione in uso contiene file che non richiedono servizi di controllo del codice sorgente, è possibile usare il comando **Escludi dal controllo del codice** sorgente per escludere il file dal controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="3da86-103">If the solution you are working on contains files that do not require source control services, you can use the **Exclude from Source Control** command to exclude the file from source control.</span></span> <span data-ttu-id="3da86-104">In questo caso, il file rimarrà nel database di [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe ma non verrà più archiviato o estratto con il progetto.</span><span class="sxs-lookup"><span data-stu-id="3da86-104">When you do this, the file remains in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database, but it is no longer checked in or out with the project.</span></span>  
  
 <span data-ttu-id="3da86-105">Usare il comando **Escludi dal controllo del codice sorgente** solo nei file generati.</span><span class="sxs-lookup"><span data-stu-id="3da86-105">You should use the **Exclude from Source Control** command only on generated files.</span></span> <span data-ttu-id="3da86-106">Un file generato è un file che può essere interamente ricreato da [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] in base al contenuto di un altro file nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="3da86-106">A generated file is one that can be entirely re-created by [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] based on the contents of another file in the solution.</span></span>  
  
### <a name="to-exclude-a-file-from-source-control"></a><span data-ttu-id="3da86-107">Per escludere un file dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3da86-107">To exclude a file from source control</span></span>  
  
1.  <span data-ttu-id="3da86-108">In Esplora soluzioni selezionare il file che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="3da86-108">In Solution Explorer, select the file to exclude.</span></span>  
  
2.  <span data-ttu-id="3da86-109">Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Escludi** *\<file name>* **dal controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="3da86-109">On the **File** menu, point to **Source Control**, and then click **Exclude** *\<file name>* **from Source Control**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da86-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3da86-110">See Also</span></span>  
 <span data-ttu-id="3da86-111">[Nozioni fondamentali sul controllo del codice sorgente](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="3da86-111">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="3da86-112">[Impostare le opzioni di controllo del codice sorgente](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="3da86-112">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="3da86-113">Modifica delle connessioni del controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="3da86-113">Change Source Control Connections</span></span>](../../2014/database-engine/change-source-control-connections.md)  
  
  
