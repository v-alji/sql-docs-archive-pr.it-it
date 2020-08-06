---
title: Generare lo script per una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627005"
---
# <a name="script-a-table"></a><span data-ttu-id="0e4e9-102">Generare lo script per una tabella</span><span class="sxs-lookup"><span data-stu-id="0e4e9-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0e4e9-103">consente di creare script per selezionare, inserire, aggiornare ed eliminare tabelle o per creare, modificare, eliminare o eseguire stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="0e4e9-104">Talvolta è necessario creare uno script con più opzioni disponibili, come ad esempio le opzioni per eliminare e poi creare una procedura o per creare una tabella e modificarne un'altra.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="0e4e9-105">Per creare script combinati, salvare il primo script in una finestra dell'editor di query e il secondo negli Appunti in modo da incollarlo nella finestra dopo il primo script.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="0e4e9-106">Creazione di uno script di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0e4e9-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="0e4e9-107">Per creare lo script di inserimento per una tabella</span><span class="sxs-lookup"><span data-stu-id="0e4e9-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="0e4e9-108">In Esplora oggetti espandere il server, espandere **Database**, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]e **Tabelle**, fare clic con il pulsante destro del mouse su **HumanResources.Employee**, quindi scegliere **Crea script per tabella**.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="0e4e9-109">Nel menu di scelta rapida sono disponibili sette opzioni di script: **Genera codice per istruzione CREATE in**, **Genera codice per istruzione DROP in**, **Genera codice per istruzione DROP e CREATE in**, **Genera codice per istruzione SELECT in**, **Genera codice per istruzione INSERT in**, **Genera codice per istruzione UPDATE in**e **Genera codice per istruzione DELETE in**.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="0e4e9-110">Scegliere **Genera codice per istruzione UPDATE in**e quindi fare clic su **Nuova finestra editor di query**.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="0e4e9-111">Viene aperta una finestra dell'editor di query che esegue una connessione e presenta l'intera istruzione di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="0e4e9-112">In questa procedura vengono illustrate le potenzialità della funzionalità di creazione di script per numerose operazioni e non soltanto per la creazione di tabelle e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="0e4e9-113">Questa nuova funzionalità consente di aggiungere rapidamente script per la manipolazione dei dati al progetto e per l'esecuzione di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="0e4e9-114">Ciò comporta un notevole risparmio di tempo nei casi di tabelle e procedure contenenti molti campi.</span><span class="sxs-lookup"><span data-stu-id="0e4e9-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0e4e9-115">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="0e4e9-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0e4e9-116">Riepilogo: Scrittura di codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0e4e9-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
