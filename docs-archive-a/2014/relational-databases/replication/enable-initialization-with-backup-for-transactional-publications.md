---
title: Abilitare l'inizializzazione con un backup per le pubblicazioni transazionali (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e22614c8c4f5250db3966e747b686091512774
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624611"
---
# <a name="enable-initialization-with-a-backup-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="5c0ea-102">Abilitazione dell'inizializzazione con un backup per le pubblicazioni transazionali (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5c0ea-102">Enable Initialization with a Backup for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5c0ea-103">Per inizializzare una sottoscrizione di una pubblicazione transazionale da un backup, attivare la pubblicazione in modo da consentire l'inizializzazione da un backup e quindi specificare le informazioni di backup durante la creazione della sottoscrizione:</span><span class="sxs-lookup"><span data-stu-id="5c0ea-103">To initialize a subscription to a transactional publication from a backup, enable the publication to allow initialization from a backup, and then specify backup information when creating the subscription:</span></span>  
  
-   <span data-ttu-id="5c0ea-104">Abilitare la pubblicazione nella pagina **Opzioni sottoscrizione** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="5c0ea-104">Enable the publication on the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="5c0ea-105">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ea-105">For more information about accessing this dialog box, see [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="5c0ea-106">Specificare le informazioni di backup con la stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c0ea-106">Specify backup information with the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="5c0ea-107">Per altre informazioni sui parametri necessari per **sp_addsubscription**, vedere [Inizializzare una sottoscrizione transazionale da un backup &#40;programmazione Transact-SQL della replica&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ea-107">For more information about the parameters required by **sp_addsubscription**, see [Initialize a Transactional Subscription from a Backup &#40;Replication Transact-SQL Programming&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span></span>  
  
### <a name="to-enable-initialization-with-a-backup"></a><span data-ttu-id="5c0ea-108">Per attivare l'inizializzazione con un backup</span><span class="sxs-lookup"><span data-stu-id="5c0ea-108">To enable initialization with a backup</span></span>  
  
1.  <span data-ttu-id="5c0ea-109">Nella pagina **Opzioni sottoscrizione** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** selezionare il valore **Vero** per l'opzione **Consenti inizializzazione dai file di backup**.</span><span class="sxs-lookup"><span data-stu-id="5c0ea-109">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, select a value of **True** for the **Allow initialization from backup files** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0ea-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c0ea-110">See Also</span></span>  
 [<span data-ttu-id="5c0ea-111">Inizializzare una sottoscrizione transazionale senza uno snapshot</span><span class="sxs-lookup"><span data-stu-id="5c0ea-111">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
