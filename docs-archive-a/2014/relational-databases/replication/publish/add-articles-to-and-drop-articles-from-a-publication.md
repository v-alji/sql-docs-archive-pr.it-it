---
title: Aggiungere ed eliminare articoli in una pubblicazione (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7af1cac1f3ee8ecc9cb79632f8a4ef1e66ec82f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637778"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a><span data-ttu-id="b7ead-102">Aggiunta ed eliminazione di articoli in una pubblicazione (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b7ead-102">Add Articles to and Drop Articles from a Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b7ead-103">Aggiungere inizialmente articoli a una pubblicazione durante la creazione nell'ambito della Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b7ead-103">Initially add articles to a publication when you create it in the New Publication Wizard.</span></span> <span data-ttu-id="b7ead-104">Per altre informazioni sull'uso di questa procedura guidata, vedere [Creare una pubblicazione](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="b7ead-104">For more information about using this wizard, see [Create a Publication](create-a-publication.md).</span></span>  
  
 <span data-ttu-id="b7ead-105">Dopo la creazione di una pubblicazione, aggiungere ed eliminare articoli nella pagina **Articoli** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="b7ead-105">After a publication is created, add and delete articles on the **Articles** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="b7ead-106">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b7ead-106">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="b7ead-107">Per altre informazioni sulle considerazioni relative all'aggiunta e l'eliminazione di articoli, vedere [Aggiungere ed eliminare articoli in pubblicazioni esistenti](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="b7ead-107">For information about the considerations for adding and dropping articles, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a><span data-ttu-id="b7ead-108">Per aggiungere un articolo dopo la creazione di una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="b7ead-108">To add an article after a publication is created</span></span>  
  
1.  <span data-ttu-id="b7ead-109">Nella pagina **Articoli** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** deselezionare la casella di controllo **Mostra solo oggetti selezionati nell'elenco**.</span><span class="sxs-lookup"><span data-stu-id="b7ead-109">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the **Show only checked objects in the list** check box.</span></span> <span data-ttu-id="b7ead-110">Ciò consente di visualizzare gli oggetti non pubblicati nel database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b7ead-110">This allows you to see the unpublished objects in the publication database.</span></span>  
  
2.  <span data-ttu-id="b7ead-111">Selezionare la casella di controllo accanto a ogni articolo che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b7ead-111">Select the check box next to each article you want to add.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a><span data-ttu-id="b7ead-112">Per eliminare un articolo</span><span class="sxs-lookup"><span data-stu-id="b7ead-112">To delete an article</span></span>  
  
1.  <span data-ttu-id="b7ead-113">Nella pagina **Articoli** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** deselezionare la casella di controllo accanto a ogni articolo che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="b7ead-113">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the check box next to each article you want to delete.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7ead-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7ead-114">See Also</span></span>  
 <span data-ttu-id="b7ead-115">[Define an Article](define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="b7ead-115">[Define an Article](define-an-article.md) </span></span>  
 [<span data-ttu-id="b7ead-116">Pubblicare dati e oggetti di database</span><span class="sxs-lookup"><span data-stu-id="b7ead-116">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
