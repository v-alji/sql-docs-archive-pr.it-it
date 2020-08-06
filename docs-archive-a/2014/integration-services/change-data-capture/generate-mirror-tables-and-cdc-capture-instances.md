---
title: Generare tabelle mirror e istanze di acquisizione di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- mirTab
ms.assetid: 260c1617-eecc-4007-a84d-3c5778ce46b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78daea310112cf7e9e78e489097fe9a76e69996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712303"
---
# <a name="generate-mirror-tables-and-cdc-capture-instances"></a><span data-ttu-id="309b9-102">Generare tabelle mirror e istanze di acquisizione di CDC</span><span class="sxs-lookup"><span data-stu-id="309b9-102">Generate Mirror Tables and CDC Capture Instances</span></span>
  <span data-ttu-id="309b9-103">Utilizzare la pagina Generate Mirror Tables per generare le tabelle mirror per le tabelle incluse nell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="309b9-103">Use the Generate Mirror Tables page to generate the mirror tables for the tables you included in the CDC instance</span></span>  
  
 <span data-ttu-id="309b9-104">Fare clic su **Run** per creare le tabelle mirror.</span><span class="sxs-lookup"><span data-stu-id="309b9-104">Click **Run** to create the mirror tables.</span></span> <span data-ttu-id="309b9-105">Viene visualizzato lo stato di avanzamento della creazione di ogni tabella e un messaggio indica se ogni tabella mirror viene completata correttamente o con errori.</span><span class="sxs-lookup"><span data-stu-id="309b9-105">The progress for the creation of each table is displayed and a message is displayed to let you know whether each mirror table is completed successfully or with errors.</span></span> <span data-ttu-id="309b9-106">Se si verifica un errore, fare clic su **Details** per visualizzare una finestra di dialogo contenente una spiegazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="309b9-106">If any errors occur, click **Details** to see a dialog box with an explanation of the error.</span></span>  
  
 <span data-ttu-id="309b9-107">Se alcune tabelle non vengono create completamente, è possibile scegliere di continuare o di eliminare tutte le tabelle che non sono state create completamente.</span><span class="sxs-lookup"><span data-stu-id="309b9-107">If any of the tables fail to be created, you can choose to continue or delete any tables that failed before continuing.</span></span> <span data-ttu-id="309b9-108">Dopo avere completato la procedura guidata, è possibile decidere se correggere la tabella nel database di origine Oracle o se non utilizzarla nell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="309b9-108">After you finish running the wizard, you can decide whether to fix the table in the Oracle source database or not use it in the CDC instance.</span></span> <span data-ttu-id="309b9-109">Se si corregge la tabella, è possibile aggiungerla alla modifica delle tabelle ( [Edit Tables](edit-tables.md)).</span><span class="sxs-lookup"><span data-stu-id="309b9-109">If you fix the table, you can add it when you [Edit Tables](edit-tables.md).</span></span>  
  
 <span data-ttu-id="309b9-110">Scegliere **Avanti** per aprire la pagina [Finish](finish.md) .</span><span class="sxs-lookup"><span data-stu-id="309b9-110">Click **Next** to open the [Finish](finish.md) page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="309b9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="309b9-111">See Also</span></span>  
 [<span data-ttu-id="309b9-112">Procedura di creazione dell'istanza del database delle modifiche di SQL Server</span><span class="sxs-lookup"><span data-stu-id="309b9-112">How to Create the SQL Server Change Database Instance</span></span>](how-to-create-the-sql-server-change-database-instance.md)  
  
  
