---
title: File di database di destinazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636818"
---
# <a name="destination-database-files"></a><span data-ttu-id="620bf-102">File di database di destinazione</span><span class="sxs-lookup"><span data-stu-id="620bf-102">Destination Database Files</span></span>
  <span data-ttu-id="620bf-103">Utilizzare la finestra di dialogo **File di database di destinazione** per visualizzare o modificare i percorsi e i nomi dei file di database nel server di destinazione oppure per specificare un percorso di file di rete per l'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="620bf-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="620bf-104">Per altre informazioni su questa attività, vedere [Attività Trasferisci database](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="620bf-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="620bf-105">Per inserire automaticamente i percorsi e i nomi dei file di database del server di origine in questa finestra di dialogo, specificare innanzitutto le proprietà **SourceConnection**, **SourceDatabaseName**e **SourceDatabaseFiles** nella pagina **Database** della finestra di dialogo **Editor attività Trasferisci database** .</span><span class="sxs-lookup"><span data-stu-id="620bf-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="620bf-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="620bf-106">Options</span></span>  
 <span data-ttu-id="620bf-107">**File di destinazione**</span><span class="sxs-lookup"><span data-stu-id="620bf-107">**Destination File**</span></span>  
 <span data-ttu-id="620bf-108">Nomi dei file di database trasferiti nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="620bf-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="620bf-109">Immettere il nome del file o fare clic sul nome del file per modificarlo.</span><span class="sxs-lookup"><span data-stu-id="620bf-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="620bf-110">**Cartella di destinazione**</span><span class="sxs-lookup"><span data-stu-id="620bf-110">**Destination Folder**</span></span>  
 <span data-ttu-id="620bf-111">Cartella del server di destinazione in cui verranno trasferiti i file di database.</span><span class="sxs-lookup"><span data-stu-id="620bf-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="620bf-112">Immettere il percorso della cartella, fare clic su tale percorso per modificarlo oppure fare clic su Sfoglia per individuare la cartella del server di destinazione in cui trasferire i file di database.</span><span class="sxs-lookup"><span data-stu-id="620bf-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="620bf-113">**Condivisione file di rete**</span><span class="sxs-lookup"><span data-stu-id="620bf-113">**Network File Share**</span></span>  
 <span data-ttu-id="620bf-114">Cartella di condivisione dei file di rete del server di destinazione in cui verranno trasferiti i file di database.</span><span class="sxs-lookup"><span data-stu-id="620bf-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="620bf-115">Utilizzare **Condivisione file di rete** quando si trasferisce un database in modalità offline specificando **DatabaseOffline** per **Metodo** nella pagina **Database** della finestra di dialogo **Editor attività Trasferisci database** .</span><span class="sxs-lookup"><span data-stu-id="620bf-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="620bf-116">Immettere il percorso di condivisione dei file di rete o fare clic su Sfoglia per individuarlo.</span><span class="sxs-lookup"><span data-stu-id="620bf-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="620bf-117">Durante il trasferimento di un database in modalità offline, prima di essere trasferiti nella posizione **Cartella di destinazione** , i file di database vengono copiati nella cartella **Condivisione file di rete** .</span><span class="sxs-lookup"><span data-stu-id="620bf-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620bf-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="620bf-118">See Also</span></span>  
 <span data-ttu-id="620bf-119">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="620bf-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="620bf-120">[Editor attività Trasferisci database &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="620bf-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="620bf-121">Editor attività Trasferisci database &#40;pagina Database&#41;</span><span class="sxs-lookup"><span data-stu-id="620bf-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
