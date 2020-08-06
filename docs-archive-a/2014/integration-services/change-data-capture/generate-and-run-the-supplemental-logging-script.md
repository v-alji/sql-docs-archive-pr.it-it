---
title: Generare ed eseguire lo script di registrazione supplementare | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712308"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="094e5-102">Generare ed eseguire lo script di registrazione supplementare</span><span class="sxs-lookup"><span data-stu-id="094e5-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="094e5-103">Utilizzare la pagina Set up Tables for Capturing Changes per eseguire uno script nel database di origine Oracle per l'impostazione della registrazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="094e5-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="094e5-104">**Per eseguire gli script di registrazione supplementare**</span><span class="sxs-lookup"><span data-stu-id="094e5-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="094e5-105">Fare clic su **Run Script** per eseguire lo script di registrazione supplementare nelle tabelle definite per l'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="094e5-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="094e5-106">Tramite questo script verranno scritte tutte le colonne di interesse nei log delle transazioni durante la registrazione delle operazioni UPDATE nelle tabelle acquisite.</span><span class="sxs-lookup"><span data-stu-id="094e5-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="094e5-107">Lo script viene in genere esaminato ed eseguito da un amministratore di sistema Oracle.</span><span class="sxs-lookup"><span data-stu-id="094e5-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="094e5-108">È anche possibile eseguire gli script manualmente tramite SQL \* Plus.</span><span class="sxs-lookup"><span data-stu-id="094e5-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="094e5-109">**Per eseguire gli script manualmente**</span><span class="sxs-lookup"><span data-stu-id="094e5-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="094e5-110">Scegliere **Copy** per incollare lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="094e5-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="094e5-111">Aprire SQL\* Plus e accedere alla directory contenente il database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="094e5-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="094e5-112">Incollare lo script in SQL\*Plus per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="094e5-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="094e5-113">Per salvare lo script di registrazione supplementare in un file di testo, scegliere **Save as** e accedere al percorso in cui si desidera salvare il file.</span><span class="sxs-lookup"><span data-stu-id="094e5-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="094e5-114">Assegnare un nome al file e scegliere **Save** per salvarlo.</span><span class="sxs-lookup"><span data-stu-id="094e5-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="094e5-115">Scegliere **Next** per [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span><span class="sxs-lookup"><span data-stu-id="094e5-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="094e5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="094e5-116">See Also</span></span>  
 <span data-ttu-id="094e5-117">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="094e5-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="094e5-118">Rivedere e generare script di registrazione supplementare</span><span class="sxs-lookup"><span data-stu-id="094e5-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
