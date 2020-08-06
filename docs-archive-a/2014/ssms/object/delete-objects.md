---
title: Eliminare oggetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623024"
---
# <a name="delete-objects"></a><span data-ttu-id="64331-102">Elimina oggetti</span><span class="sxs-lookup"><span data-stu-id="64331-102">Delete Objects</span></span>
  <span data-ttu-id="64331-103">Utilizzare questa finestra di dialogo per eliminare un database o un oggetto di database.</span><span class="sxs-lookup"><span data-stu-id="64331-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="64331-104">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="64331-104">UI element list</span></span>  
 <span data-ttu-id="64331-105">**Oggetto da eliminare**</span><span class="sxs-lookup"><span data-stu-id="64331-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="64331-106">Consente di visualizzare i nomi, i tipi, i proprietari e lo stato degli oggetti da eliminare, nonché gli eventuali messaggi relativi agli errori verificatisi durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64331-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64331-107">L'esecuzione dell'opzione **Elimina** su un database equivale all'esecuzione di DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64331-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="64331-108">**Mostra dipendenze**</span><span class="sxs-lookup"><span data-stu-id="64331-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="64331-109">Fare clic su questo pulsante per visualizzare sia gli oggetti che dipendono dall'oggetto attualmente selezionato che gli oggetti dal quale dipende l'oggetto corrente (dipendenza verso l'alto e verso il basso).</span><span class="sxs-lookup"><span data-stu-id="64331-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="64331-110">Le informazioni visualizzate nella finestra di dialogo **Mostra dipendenze** sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="64331-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64331-111">Il pulsante **Mostra dipendenze** non viene visualizzato per tutti i tipi di oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="64331-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="64331-112">Per visualizzare le dipendenze quando il pulsante **Mostra dipendenze** non è disponibile, fare clic sull'oggetto con il pulsante destro del mouse in Esplora oggetti e scegliere **Visualizza dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="64331-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="64331-113">**Elimina informazioni di cronologia di backup e ripristino per i database**</span><span class="sxs-lookup"><span data-stu-id="64331-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="64331-114">Questa casella di controllo viene visualizzata solo quando viene eliminato un database e comporta l'eliminazione dal database **msdb** della cronologia di backup e ripristino del database eliminato.</span><span class="sxs-lookup"><span data-stu-id="64331-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="64331-115">**Chiudi connessioni esistenti**</span><span class="sxs-lookup"><span data-stu-id="64331-115">**Close existing connections**</span></span>  
 <span data-ttu-id="64331-116">Questa casella di controllo viene visualizzata solo quando viene eliminato un database e interrompe le connessioni al database eliminato.</span><span class="sxs-lookup"><span data-stu-id="64331-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
