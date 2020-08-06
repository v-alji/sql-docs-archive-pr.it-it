---
title: Posizionare dati e file di log in unità distinte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634979"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="ed0a9-102">Posizionamento di dati e file di log in unità distinte</span><span class="sxs-lookup"><span data-stu-id="ed0a9-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="ed0a9-103">Questa regola consente di controllare se i dati e i file di log si trovano in unità logiche distinte.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="ed0a9-104">Il posizionamento dei dati e dei file di log nello stesso dispositivo può provocare contesa nel dispositivo stesso e comportare prestazioni insufficienti.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="ed0a9-105">Il posizionamento dei file in unità distinte fa sì che l'attività di I/O si verifichi contemporaneamente sia per i dati sia per i file di log.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ed0a9-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="ed0a9-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ed0a9-107">Quando si crea un nuovo database, specificare unità distinte per i dati e per il log.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="ed0a9-108">Per spostare i file una volta creato il database, è necessario che il database sia offline.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="ed0a9-109">Per spostare i file, utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed0a9-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed0a9-110">Questi criteri non sono in grado di rilevare dispositivi fisici separati mediante punti di montaggio</span><span class="sxs-lookup"><span data-stu-id="ed0a9-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="ed0a9-111">Ripristinare il database dal backup utilizzando l'istruzione RESTORE DATABASE con l'opzione WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="ed0a9-112">Scollegare e quindi ricollegare il database specificando posizioni distinte per i dispositivi dei dati e dei log.</span><span class="sxs-lookup"><span data-stu-id="ed0a9-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="ed0a9-113">Specificare una nuova posizione eseguendo l'istruzione ALTER DATABASE con l'opzione MODIFY FILE, riavviando quindi l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed0a9-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ed0a9-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="ed0a9-114">For More Information</span></span>  
 [<span data-ttu-id="ed0a9-115">Spostare file del database</span><span class="sxs-lookup"><span data-stu-id="ed0a9-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="ed0a9-116">Spostare database utente</span><span class="sxs-lookup"><span data-stu-id="ed0a9-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="ed0a9-117">Collegamento e scollegamento di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ed0a9-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed0a9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0a9-118">See Also</span></span>  
 [<span data-ttu-id="ed0a9-119">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="ed0a9-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
