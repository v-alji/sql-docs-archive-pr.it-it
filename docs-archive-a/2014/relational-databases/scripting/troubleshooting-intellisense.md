---
title: Risoluzione dei problemi di IntelliSense
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- unavailable options [IntelliSense]
- IntelliSense [SQL Server], troubleshooting
- IntelliSense [SQL Server], unavailable options
- troubleshooting [IntelliSense]
ms.assetid: 4b72ffc6-aea2-4e11-ab36-fa2de4d7bcc5
author: rothja
ms.author: jroth
ms.openlocfilehash: 087baf616fc215c480ae78621623cbe1ed512b57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717753"
---
# <a name="troubleshooting-intellisense-sql-server-management-studio"></a><span data-ttu-id="c37ec-102">Risoluzione dei problemi di IntelliSense (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c37ec-102">Troubleshooting IntelliSense (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c37ec-103">In alcuni casi le opzioni di IntelliSense potrebbero non funzionare nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="c37ec-103">There are certain cases when the IntelliSense options might not work as you expect.</span></span>  
  
## <a name="conditions-that-affect-intellisense"></a><span data-ttu-id="c37ec-104">Condizioni che influiscono su IntelliSense</span><span class="sxs-lookup"><span data-stu-id="c37ec-104">Conditions That Affect IntelliSense</span></span>  
 <span data-ttu-id="c37ec-105">Le condizioni seguenti potrebbero influire sul comportamento di IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="c37ec-105">The following conditions might affect the behavior of IntelliSense:</span></span>  
  
-   <span data-ttu-id="c37ec-106">È presente un errore del codice sopra il cursore.</span><span class="sxs-lookup"><span data-stu-id="c37ec-106">There is a code error above the cursor.</span></span>  
  
     <span data-ttu-id="c37ec-107">Se esiste un'istruzione incompleta o un altro errore del codice sopra la posizione del punto di inserimento, IntelliSense potrebbe non essere in grado di analizzare gli elementi del codice e quindi non funzionare.</span><span class="sxs-lookup"><span data-stu-id="c37ec-107">If there is an incomplete statement or other coding error above the location of the insertion point, IntelliSense may be unable to parse the code elements, and therefore will not work.</span></span> <span data-ttu-id="c37ec-108">Per attivarlo di nuovo, è possibile impostare come commento il codice pertinente.</span><span class="sxs-lookup"><span data-stu-id="c37ec-108">You can comment out the applicable code to enable IntelliSense again.</span></span>  
  
-   <span data-ttu-id="c37ec-109">Il punto di inserimento si trova all'interno di un commento di codice.</span><span class="sxs-lookup"><span data-stu-id="c37ec-109">The insertion point is inside a code comment.</span></span>  
  
     <span data-ttu-id="c37ec-110">Le opzioni di IntelliSense non sono disponibili quando il punto di inserimento si trova all'interno di un commento nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="c37ec-110">IntelliSense options are not available when the insertion point is within a comment in your source file.</span></span>  
  
-   <span data-ttu-id="c37ec-111">Il punto di inserimento si trova all'interno di un valore letterale stringa.</span><span class="sxs-lookup"><span data-stu-id="c37ec-111">The insertion point is inside a string literal.</span></span>  
  
     <span data-ttu-id="c37ec-112">Le opzioni di IntelliSense non sono disponibili quando il punto di inserimento si trova all'interno delle virgolette che racchiudono un valore letterale stringa, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c37ec-112">IntelliSense options are not available when the insertion point is inside the quotation marks around a string literal, for example:</span></span>  
  
     `WHERE FirstName LIKE 'Patri%|'`  
  
-   <span data-ttu-id="c37ec-113">Le opzioni automatiche sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="c37ec-113">The automatic options are turned off.</span></span>  
  
     <span data-ttu-id="c37ec-114">Per impostazione predefinita, molte caratteristiche di IntelliSense operano automaticamente ma possono essere disabilitate.</span><span class="sxs-lookup"><span data-stu-id="c37ec-114">Many IntelliSense features work automatically by default, but you can disable any feature.</span></span>  
  
     <span data-ttu-id="c37ec-115">È possibile utilizzarle anche se il completamento automatico delle istruzioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="c37ec-115">Even when automatic statement completion is disabled, you can use an IntelliSense feature.</span></span> <span data-ttu-id="c37ec-116">Per altre informazioni, vedere [Configurare IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c37ec-116">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
## <a name="database-engine-query-intellisense"></a><span data-ttu-id="c37ec-117">Funzionalità IntelliSense in query del Motore di database</span><span class="sxs-lookup"><span data-stu-id="c37ec-117">Database Engine Query IntelliSense</span></span>  
 <span data-ttu-id="c37ec-118">I problemi descritti di seguito sono relativi all'editor di query del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c37ec-118">The following issues apply to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor:</span></span>  
  
-   <span data-ttu-id="c37ec-119">La funzionalità IntelliSense dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] non supporta tutti gli elementi della sintassi [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c37ec-119">The IntelliSense functionality of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="c37ec-120">La Guida relativa ai parametri non supporta i parametri in alcuni oggetti, ad esempio nelle stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="c37ec-120">Parameter help does not support the parameters in some objects, such as extended stored procedures.</span></span> <span data-ttu-id="c37ec-121">Per altre informazioni, vedere [Sintassi Transact-SQL supportata da IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="c37ec-121">For more information, see [Transact-SQL Syntax Supported by IntelliSense](transact-sql-syntax-supported-by-intellisense.md).</span></span>  
  
-   <span data-ttu-id="c37ec-122">IntelliSense è disponibile solo quando l'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] è connesso a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c37ec-122">IntelliSense is only available when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor is connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="c37ec-123">IntelliSense non è disponibile quando l'editor di query è connesso a versioni precedenti del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c37ec-123">IntelliSense is not available when the Query Editor is connected to earlier versions of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="c37ec-124">IntelliSense è disattivato nell'editor di query di [!INCLUDE[ssDE](../../includes/ssde-md.md)] quando è impostata la modalità SQLCMD.</span><span class="sxs-lookup"><span data-stu-id="c37ec-124">IntelliSense is turned off in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor when the SQLCMD mode is set on.</span></span>  
  
-   <span data-ttu-id="c37ec-125">La funzionalità IntelliSense non può essere utilizzata per oggetti di database creati da un'altra connessione dopo che la finestra dell'editor si è connessa al database.</span><span class="sxs-lookup"><span data-stu-id="c37ec-125">IntelliSense functionality does not cover database objects created by another connection after your editor window connected to the database.</span></span> <span data-ttu-id="c37ec-126">Se nelle caratteristiche di IntelliSense mancano oggetti, ad esempio gli elenchi di completamento, è possibile scegliere uno di questi tre meccanismi per aggiornare la cache degli oggetti per la finestra dell'editor:</span><span class="sxs-lookup"><span data-stu-id="c37ec-126">If objects are missing from IntelliSense features such as completion lists, you can choose one of these three mechanisms to refresh the cache of objects for your editor window:</span></span>  
  
    -   <span data-ttu-id="c37ec-127">Scegliere **IntelliSense** dal menu **Modifica**, quindi fare clic su **Aggiorna cache locale**.</span><span class="sxs-lookup"><span data-stu-id="c37ec-127">Select the **Edit** menu, select **IntelliSense**, then select **Refresh Local Cache**.</span></span>  
  
    -   <span data-ttu-id="c37ec-128">Utilizzare i tasti di scelta rapida CTRL+MAIUSC+R.</span><span class="sxs-lookup"><span data-stu-id="c37ec-128">Use the CTRL+Shift+R keyboard shortcut.</span></span>  
  
    -   <span data-ttu-id="c37ec-129">Disconnettere la finestra dell'editor dall'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)] ed effettuare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="c37ec-129">Disconnect your editor window from the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and reconnect.</span></span>  
  
-   <span data-ttu-id="c37ec-130">Gli elenchi di completamento non includono oggetti di database per cui non si dispone di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c37ec-130">Completion lists do not include database objects for which you do not have permissions.</span></span> <span data-ttu-id="c37ec-131">Tramite IntelliSense vengono contrassegnati i riferimenti a oggetti per i quali si dispone di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c37ec-131">IntelliSense flags references to objects for which you do have permissions.</span></span> <span data-ttu-id="c37ec-132">Se, ad esempio, se si apre uno script scritto da un altro utente, qualsiasi riferimento a oggetti per i quali l'autore dispone di autorizzazioni e l'utente che apre lo script no viene contrassegnato come non corretto.</span><span class="sxs-lookup"><span data-stu-id="c37ec-132">For example, if you open a script that is written by someone else, any references to objects for which that person has permissions and you do not are flagged as incorrect.</span></span>  
  
-   <span data-ttu-id="c37ec-133">Gli elenchi di completamento potrebbero smettere di funzionare se si perde la connessione all'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c37ec-133">Completion lists might stop working if you lose the connection to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="c37ec-134">Connettersi di nuovo all'istanza.</span><span class="sxs-lookup"><span data-stu-id="c37ec-134">Reconnect to the instance.</span></span>  
  
  
