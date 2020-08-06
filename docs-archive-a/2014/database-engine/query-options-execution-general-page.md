---
title: Esecuzione di opzioni query (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.general.f1
ms.assetid: 858a0263-2f04-4692-b8bf-63e93c998ead
author: rothja
ms.author: jroth
ms.openlocfilehash: ce3848b51b81f111333ba0e9ac12c96432dd9863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636379"
---
# <a name="query-options-execution-general-page"></a><span data-ttu-id="89991-102">Opzioni query - Esecuzione (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="89991-102">Query Options Execution (General Page)</span></span>
  <span data-ttu-id="89991-103">Utilizzare questa pagina per specificare le opzioni per l'esecuzione di query di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89991-103">Use this page to specify the options for running [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="89991-104">Per accedere a questa finestra di dialogo, fare clic con il pulsante destro del mouse su una finestra dell'editor di query e quindi scegliere **Opzioni query**.</span><span class="sxs-lookup"><span data-stu-id="89991-104">To access this dialog box, right-click the body of a Query Editor window, and then click **Query Options**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="89991-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="89991-105">UI element list</span></span>  
 <span data-ttu-id="89991-106">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="89991-106">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="89991-107">Il valore predefinito 0 indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] rimarrà in attesa di risultati fino a quando non verranno ricevuti tutti i risultati.</span><span class="sxs-lookup"><span data-stu-id="89991-107">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="89991-108">Specificare un valore maggiore di 0 se si desidera che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] interrompa la query dopo aver ottenuto il numero di righe specificato.</span><span class="sxs-lookup"><span data-stu-id="89991-108">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="89991-109">Per disabilitare questa opzione in modo che vengano restituite tutte le righe, specificare SET ROWCOUNT 0.</span><span class="sxs-lookup"><span data-stu-id="89991-109">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="89991-110">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="89991-110">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="89991-111">Il valore predefinito di 2.147.483.647 byte indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fornirà un campo dati completo fino al limite dei campi dati `text`, `ntext`, `nvarchar(max)` e `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="89991-111">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide a complete data field up to the limit of `text`, `ntext`, `nvarchar(max)`, and `varchar(max)` data fields.</span></span> <span data-ttu-id="89991-112">Ciò non ha alcun effetto sul tipo di dati XML.</span><span class="sxs-lookup"><span data-stu-id="89991-112">It does not affect the XML data type.</span></span> <span data-ttu-id="89991-113">Specificare un numero più piccolo per limitare i risultati in caso di valori elevati.</span><span class="sxs-lookup"><span data-stu-id="89991-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="89991-114">Le colonne le cui dimensioni sono maggiori del numero specificato verranno troncate.</span><span class="sxs-lookup"><span data-stu-id="89991-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="89991-115">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="89991-115">**Execution time-out**</span></span>  
 <span data-ttu-id="89991-116">Consente di indicare il numero di secondi di attesa prima dell'annullamento della query.</span><span class="sxs-lookup"><span data-stu-id="89991-116">Indicates the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="89991-117">Il valore 0 indica un'attesa infinita, ovvero nessun timeout.</span><span class="sxs-lookup"><span data-stu-id="89991-117">A value of 0 indicates an infinite wait, or no time-out.</span></span>  
  
 <span data-ttu-id="89991-118">**Separatore batch**</span><span class="sxs-lookup"><span data-stu-id="89991-118">**Batch separator**</span></span>  
 <span data-ttu-id="89991-119">Consente di digitare una parola che verrà utilizzata per separare le istruzioni Transact-SQL in batch.</span><span class="sxs-lookup"><span data-stu-id="89991-119">Type a word that you use to separate Transact-SQL statements into batches.</span></span> <span data-ttu-id="89991-120">Il valore predefinito è GO.</span><span class="sxs-lookup"><span data-stu-id="89991-120">The default is GO.</span></span>  
  
 <span data-ttu-id="89991-121">**Per impostazione predefinita, apri le nuove query in modalità SQLCMD.**</span><span class="sxs-lookup"><span data-stu-id="89991-121">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="89991-122">Selezionare questa casella di controllo per aprire le nuove query in modalità SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="89991-122">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="89991-123">Questa casella di controllo è visibile solo quando la finestra di dialogo viene aperta tramite il menu **strumenti** .</span><span class="sxs-lookup"><span data-stu-id="89991-123">This check box is visible only when the dialog box is opened through the **Tools** menu.</span></span>  
  
 <span data-ttu-id="89991-124">Quando si seleziona questa opzione, tenere presente le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89991-124">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="89991-125">Nell'editor di query del [!INCLUDE[ssDE](../includes/ssde-md.md)] , IntelliSense è disattivata.</span><span class="sxs-lookup"><span data-stu-id="89991-125">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="89991-126">Poiché l'editor di query non è in esecuzione dalla riga di comando, non è possibile passare parametri della riga di comando, ad esempio variabili.</span><span class="sxs-lookup"><span data-stu-id="89991-126">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="89991-127">Poiché l'editor di query non può rispondere ai prompt del sistema operativo, è necessario prestare attenzione a non eseguire istruzioni interattive.</span><span class="sxs-lookup"><span data-stu-id="89991-127">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="89991-128">**Ripristina predefiniti**</span><span class="sxs-lookup"><span data-stu-id="89991-128">**Reset to Default**</span></span>  
 <span data-ttu-id="89991-129">Reimposta le impostazioni predefinite originali per tutti i valori nella pagina.</span><span class="sxs-lookup"><span data-stu-id="89991-129">Resets all values on this page to the original default values.</span></span>  
  
  
