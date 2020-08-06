---
title: Opzioni (esecuzione query-SQL Server-pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636853"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="b5433-102">Opzioni (esecuzione query-SQL Server-pagina generale)</span><span class="sxs-lookup"><span data-stu-id="b5433-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="b5433-103">Utilizzare questa pagina per specificare le opzioni per l'esecuzione di query di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5433-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="b5433-104">Le modifiche apportate a queste opzioni si applicano soltanto alle nuove query di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5433-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="b5433-105">Per modificare le opzioni per una query corrente, scegliere **Opzioni query** dal menu **Query** oppure fare clic con il pulsante destro del mouse nella finestra Query di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e scegliere **Opzioni query**.</span><span class="sxs-lookup"><span data-stu-id="b5433-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5433-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b5433-106">Options</span></span>  
 <span data-ttu-id="b5433-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="b5433-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="b5433-108">Il valore predefinito 0 indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] rimarrà in attesa di risultati fino a quando non verranno ricevuti tutti i risultati.</span><span class="sxs-lookup"><span data-stu-id="b5433-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="b5433-109">Specificare un valore maggiore di 0 se si desidera che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interrompa la query dopo aver ottenuto il numero di righe specificato.</span><span class="sxs-lookup"><span data-stu-id="b5433-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="b5433-110">Per disabilitare questa opzione in modo che vengano restituite tutte le righe, specificare SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="b5433-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="b5433-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="b5433-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="b5433-112">Il valore predefinito 2.147.483.647 byte indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornirà campi dati completi fino al limite dei campi dati `text` e `ntext`.</span><span class="sxs-lookup"><span data-stu-id="b5433-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="b5433-113">Specificare un numero più piccolo per limitare i risultati in caso di valori elevati.</span><span class="sxs-lookup"><span data-stu-id="b5433-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="b5433-114">Le colonne le cui dimensioni sono maggiori del numero specificato verranno troncate.</span><span class="sxs-lookup"><span data-stu-id="b5433-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="b5433-115">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="b5433-115">**Execution time-out**</span></span>  
 <span data-ttu-id="b5433-116">Consente di impostare il valore predefinito nella finestra di dialogo **Nuova connessione** .</span><span class="sxs-lookup"><span data-stu-id="b5433-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="b5433-117">Usare questa casella di selezione per indicare a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] il numero di secondi di attesa prima dell'annullamento della query.</span><span class="sxs-lookup"><span data-stu-id="b5433-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="b5433-118">Il valore 0 indica un'attesa infinita o nessun timeout. Questo valore è 0 in una nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="b5433-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="b5433-119">**Separatore batch**</span><span class="sxs-lookup"><span data-stu-id="b5433-119">**Batch separator**</span></span>  
 <span data-ttu-id="b5433-120">Consente di digitare una parola che verrà utilizzata per separare le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] in batch.</span><span class="sxs-lookup"><span data-stu-id="b5433-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="b5433-121">Il valore predefinito è GO.</span><span class="sxs-lookup"><span data-stu-id="b5433-121">The default is GO.</span></span>  
  
 <span data-ttu-id="b5433-122">**Per impostazione predefinita, apri le nuove query in modalità SQLCMD.**</span><span class="sxs-lookup"><span data-stu-id="b5433-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="b5433-123">Selezionare questa casella di controllo per aprire le nuove query in modalità SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="b5433-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="b5433-124">Per altre informazioni sulla modalità SQLCMD, vedere [Modifica di script SQLCMD con l'editor di query](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="b5433-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="b5433-125">Quando si seleziona questa opzione, tenere presente le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5433-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="b5433-126">Nell'editor di query del [!INCLUDE[ssDE](../includes/ssde-md.md)] , IntelliSense è disattivata.</span><span class="sxs-lookup"><span data-stu-id="b5433-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="b5433-127">Poiché l'editor di query non è in esecuzione dalla riga di comando, non è possibile passare parametri della riga di comando, ad esempio variabili.</span><span class="sxs-lookup"><span data-stu-id="b5433-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="b5433-128">Poiché l'editor di query non può rispondere ai prompt del sistema operativo, è necessario prestare attenzione a non eseguire istruzioni interattive.</span><span class="sxs-lookup"><span data-stu-id="b5433-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="b5433-129">**Ripristina predefiniti**</span><span class="sxs-lookup"><span data-stu-id="b5433-129">**Reset to Default**</span></span>  
 <span data-ttu-id="b5433-130">Fare clic su questo pulsante per reimpostare le impostazioni predefinite originali per tutti i valori della pagina.</span><span class="sxs-lookup"><span data-stu-id="b5433-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5433-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5433-131">See Also</span></span>  
 [<span data-ttu-id="b5433-132">Utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b5433-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
