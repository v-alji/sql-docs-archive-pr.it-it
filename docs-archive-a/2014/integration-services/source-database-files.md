---
title: File di database di origine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726023"
---
# <a name="source-database-files"></a><span data-ttu-id="49132-102">File di database di origine</span><span class="sxs-lookup"><span data-stu-id="49132-102">Source database files</span></span>
  <span data-ttu-id="49132-103">Utilizzare la finestra di dialogo **File di database di origine** per visualizzare i nomi e i percorsi dei file di database nel server di origine oppure per specificare il percorso di condivisione dei file in rete per l'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="49132-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="49132-104">Per altre informazioni su questa attività, vedere [Attività Trasferisci database](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="49132-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="49132-105">Per popolare questa finestra di dialogo con i nomi e i percorsi dei file di database nel server di origine, impostare innanzitutto le opzioni **SourceConnection** e **SourceDatabaseName** nelle pagine **Database** della finestra di dialogo **Editor attività Trasferisci database** .</span><span class="sxs-lookup"><span data-stu-id="49132-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="49132-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="49132-106">Options</span></span>  
 <span data-ttu-id="49132-107">**File di origine**</span><span class="sxs-lookup"><span data-stu-id="49132-107">**Source File**</span></span>  
 <span data-ttu-id="49132-108">Nomi dei file di database nel server di origine che verranno trasferiti.</span><span class="sxs-lookup"><span data-stu-id="49132-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="49132-109">Il valore**File di origine** è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="49132-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="49132-110">**Cartella di origine**</span><span class="sxs-lookup"><span data-stu-id="49132-110">**Source Folder**</span></span>  
 <span data-ttu-id="49132-111">Cartella nel server di origine in cui si trovano i file di database da trasferire.</span><span class="sxs-lookup"><span data-stu-id="49132-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="49132-112">Il valore**Cartella di origine** è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="49132-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="49132-113">**Condivisione file di rete**</span><span class="sxs-lookup"><span data-stu-id="49132-113">**Network File Share**</span></span>  
 <span data-ttu-id="49132-114">Cartella di rete condivisa nel server di origine da cui verranno trasferiti i file di database.</span><span class="sxs-lookup"><span data-stu-id="49132-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="49132-115">Utilizzare **Condivisione file di rete** quando si trasferisce un database in modalità offline impostando l'opzione **DatabaseOffline** per **Metodo** nella pagina **Database** della finestra di dialogo **Editor attività Trasferisci database** .</span><span class="sxs-lookup"><span data-stu-id="49132-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="49132-116">Digitare il percorso della condivisione file di rete oppure fare clic sul pulsante Sfoglia **(...)** per individuarlo.</span><span class="sxs-lookup"><span data-stu-id="49132-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="49132-117">Quando si trasferisce un database in modalità offline, i rispettivi file vengono copiati nel percorso specificato in **Condivisione file di rete** nel server di origine prima di essere trasferiti al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="49132-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49132-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49132-118">See Also</span></span>  
 <span data-ttu-id="49132-119">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="49132-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="49132-120">[Editor attività Trasferisci database &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="49132-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="49132-121">Editor attività Trasferisci database &#40;pagina Database&#41;</span><span class="sxs-lookup"><span data-stu-id="49132-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
