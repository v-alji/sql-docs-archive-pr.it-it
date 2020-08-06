---
title: Riconciliare un diagramma di database con un database modificato (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713656"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="8ad16-102">Riconciliazione di un diagramma di database con un database modificato (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8ad16-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="8ad16-103">Il diagramma di database viene salvato per aggiornare il database in modo che corrisponda al diagramma.</span><span class="sxs-lookup"><span data-stu-id="8ad16-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="8ad16-104">Tuttavia, se il database è stato aggiornato da altri utenti dopo l'apertura del diagramma, le modifiche apportate potranno avere effetto sul diagramma e viceversa.</span><span class="sxs-lookup"><span data-stu-id="8ad16-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="8ad16-105">Salvando il diagramma, le differenze tra il database e il diagramma verranno riconciliate sovrascrivendo le modifiche apportate da altri utenti, al fine di garantire la corrispondenza tra il database e il diagramma.</span><span class="sxs-lookup"><span data-stu-id="8ad16-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="8ad16-106">Per aggiornare un database in modo che corrisponda al diagramma</span><span class="sxs-lookup"><span data-stu-id="8ad16-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="8ad16-107">Salvare il diagramma del database.</span><span class="sxs-lookup"><span data-stu-id="8ad16-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="8ad16-108">Se si salva il diagramma per la prima volta, specificare un nome per il diagramma nella finestra di dialogo **Salva nuovo diagramma di database** e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ad16-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="8ad16-109">Nella finestra di dialogo **Salva** è contenuto l'elenco delle tabelle su cui influirà il salvataggio del diagramma.</span><span class="sxs-lookup"><span data-stu-id="8ad16-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="8ad16-110">Scegliere **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="8ad16-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="8ad16-111">Nella finestra di dialogo **Rilevate modifiche al database** vengono elencati gli oggetti modificati che verranno cambiati per assicurare la corrispondenza con il diagramma.</span><span class="sxs-lookup"><span data-stu-id="8ad16-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="8ad16-112">Scegliere **Sì** per salvare il diagramma e accettare l'elenco di modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ad16-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ad16-113">Se il diagramma contiene tabelle e colonne eliminate dal database, salvando il diagramma verranno create nuovamente nel database solo le corrispondenti definizioni.</span><span class="sxs-lookup"><span data-stu-id="8ad16-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="8ad16-114">Con questa operazione non verranno ripristinati i dati contenuti in tali oggetti prima dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8ad16-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="8ad16-115">Per aggiornare il diagramma in modo che corrisponda a un database modificato</span><span class="sxs-lookup"><span data-stu-id="8ad16-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="8ad16-116">Chiudere il diagramma senza salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8ad16-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="8ad16-117">Fare clic con il pulsante destro del mouse sul diagramma in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="8ad16-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="8ad16-118">Scegliere **Aggiorna**dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="8ad16-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="8ad16-119">Aprire nuovamente il diagramma.</span><span class="sxs-lookup"><span data-stu-id="8ad16-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad16-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ad16-120">See Also</span></span>  
 [<span data-ttu-id="8ad16-121">Utilizzare diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8ad16-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
