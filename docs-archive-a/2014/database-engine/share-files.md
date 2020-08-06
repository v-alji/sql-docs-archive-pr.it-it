---
title: Condividi file | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724900"
---
# <a name="share-files"></a><span data-ttu-id="7d889-102">Condivisione di file</span><span class="sxs-lookup"><span data-stu-id="7d889-102">Share Files</span></span>
  <span data-ttu-id="7d889-103">È possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per condividere elementi nei progetti di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7d889-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="7d889-104">Quando un elemento viene condiviso, qualsiasi modifica all'elemento apportata verrà applicata in tutti i progetti con i quali l'elemento è condiviso.</span><span class="sxs-lookup"><span data-stu-id="7d889-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="7d889-105">La condivisione degli elementi offre i vantaggi seguenti agli utenti del controllo del codice sorgente:</span><span class="sxs-lookup"><span data-stu-id="7d889-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="7d889-106">Evita di dover archiviare una copia separata dell'elemento in ogni progetto che utilizza l'elemento condiviso, risparmiando spazio su disco sia nel client che nel server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7d889-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="7d889-107">Il provider del controllo del codice sorgente archivia l'elemento condiviso in un percorso centrale e in ogni progetto con cui è condiviso viene archiviato un puntatore per quel percorso.</span><span class="sxs-lookup"><span data-stu-id="7d889-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="7d889-108">Evita incompatibilità tra le versioni.</span><span class="sxs-lookup"><span data-stu-id="7d889-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="7d889-109">Poiché ogni progetto con cui l'elemento è condiviso utilizza la stessa versione dell'elemento, vengono evitati i conflitti che insorgono quando ogni copia di un elemento cambia in maniera indipendente all'interno di più progetti.</span><span class="sxs-lookup"><span data-stu-id="7d889-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="7d889-110">Per condividere un elemento</span><span class="sxs-lookup"><span data-stu-id="7d889-110">To share an item</span></span>  
  
1.  <span data-ttu-id="7d889-111">In Esplora soluzioni selezionare la cartella o il progetto in cui si desidera posizionare i file condivisi.</span><span class="sxs-lookup"><span data-stu-id="7d889-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="7d889-112">Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Condividi**.</span><span class="sxs-lookup"><span data-stu-id="7d889-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="7d889-113">Nella finestra di dialogo **Condividi con** individuare l'elemento che si desidera condividere nell'elenco di directory, quindi fare clic su tale elemento.</span><span class="sxs-lookup"><span data-stu-id="7d889-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="7d889-114">Fare clic su **Share** (Condividi).</span><span class="sxs-lookup"><span data-stu-id="7d889-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d889-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d889-115">See Also</span></span>  
 [<span data-ttu-id="7d889-116">Nozioni fondamentali sul controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="7d889-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
