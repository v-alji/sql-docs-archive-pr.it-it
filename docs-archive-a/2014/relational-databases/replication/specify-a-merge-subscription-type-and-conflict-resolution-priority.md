---
title: Specificare una sottoscrizione di tipo merge e la priorità per la risoluzione dei conflitti (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726888"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="6ed3e-102">Impostazione di una sottoscrizione di tipo merge e della priorità per la risoluzione dei conflitti (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6ed3e-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6ed3e-103">Specificare una sottoscrizione di tipo merge e la priorità per la risoluzione dei conflitti nella pagina **Tipo di sottoscrizione** della Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="6ed3e-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="6ed3e-104">Per ulteriori informazioni sull'utilizzo di questa procedura guidata, vedere [Create a Pull Subscription](create-a-pull-subscription.md) e [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6ed3e-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="6ed3e-105">Dopo la creazione di una sottoscrizione non è più possibile modificarne il tipo. È tuttavia possibile modificare la priorità per il tipo di sottoscrizione server nella finestra di dialogo **Proprietà sottoscrizione - \<Publisher>:\<PublicationDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="6ed3e-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="6ed3e-106">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) e [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6ed3e-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="6ed3e-107">Per specificare una sottoscrizione di tipo merge e la priorità per la risoluzione dei conflitti</span><span class="sxs-lookup"><span data-stu-id="6ed3e-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="6ed3e-108">Nella pagina **Tipo di sottoscrizione** della Creazione guidata sottoscrizione selezionare **Client** o **Server** per l'opzione **Tipo di sottoscrizione** .</span><span class="sxs-lookup"><span data-stu-id="6ed3e-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="6ed3e-109">Se si seleziona un tipo di sottoscrizione **Server**, immettere anche un valore compreso tra 0,00 e 99,99 per l'opzione **Priorità per la risoluzione dei conflitti** .</span><span class="sxs-lookup"><span data-stu-id="6ed3e-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="6ed3e-110">Per modificare la priorità per la risoluzione dei conflitti</span><span class="sxs-lookup"><span data-stu-id="6ed3e-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="6ed3e-111">Nella finestra di dialogo **Proprietà sottoscrizione - \<Publisher>:\<PublicationDatabase>** visualizzata sul server di pubblicazione immettere un valore compreso tra 0,00 e 99,99 per l'opzione **Priorità**.</span><span class="sxs-lookup"><span data-stu-id="6ed3e-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ed3e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ed3e-112">See Also</span></span>  
 <span data-ttu-id="6ed3e-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="6ed3e-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="6ed3e-114">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="6ed3e-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
