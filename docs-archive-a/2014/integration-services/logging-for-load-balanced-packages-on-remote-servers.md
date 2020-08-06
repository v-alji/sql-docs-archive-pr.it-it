---
title: Registrazione per pacchetti con bilanciamento del carico in server remoti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628812"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a><span data-ttu-id="43380-102">Registrazione per pacchetti con bilanciamento del carico in server remoti</span><span class="sxs-lookup"><span data-stu-id="43380-102">Logging for Load Balanced Packages on Remote Servers</span></span>
  <span data-ttu-id="43380-103">La gestione dei log di tutti i pacchetti figlio in esecuzione su più server risulta più semplice se tutti i pacchetti figlio utilizzano lo stesso provider di log e scrivono nella stessa destinazione.</span><span class="sxs-lookup"><span data-stu-id="43380-103">It is easier for an administrator to manage the logs for all the child packages that are running on various servers when all the child packages use the same log provider and they all write to the same destination.</span></span> <span data-ttu-id="43380-104">Per creare un file di log comune per tutti i pacchetti figlio, è possibile configurare i pacchetti figlio in modo da registrare i propri eventi in un provider di log di tipo SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43380-104">One way that you can create a common log file for all child packages is to configure the child packages to log their events to a SQL Server log provider.</span></span> <span data-ttu-id="43380-105">È possibile configurare tutti i pacchetti in modo che utilizzino lo stesso database, lo stesso server e la stessa istanza del server.</span><span class="sxs-lookup"><span data-stu-id="43380-105">You can configure all the packages to use the same database, the same server, and the same instance of the server.</span></span>  
  
 <span data-ttu-id="43380-106">Per visualizzare tutti i file di log, l'amministratore deve semplicemente accedere a un server e visualizzare il file di log per tutti i pacchetti figlio.</span><span class="sxs-lookup"><span data-stu-id="43380-106">To view the log files, the administrator only has to log on to a single server to view the log files for all child packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="43380-107">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="43380-107">Related Tasks</span></span>  
 <span data-ttu-id="43380-108">Per informazioni su come abilitare la registrazione in un pacchetto, vedere [Abilitare la registrazione di pacchetti in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43380-108">For information about how to enable logging in a package, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43380-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43380-109">See Also</span></span>  
 [<span data-ttu-id="43380-110">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="43380-110">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
