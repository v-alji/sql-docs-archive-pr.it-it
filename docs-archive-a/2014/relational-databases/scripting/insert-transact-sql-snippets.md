---
title: Inserimento di frammenti di Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], snippets
- Transact-SQL snippets, code
- snippets [Transact-SQL], how to insert
ms.assetid: d66c96f4-2e84-4d79-9bfd-3635fdd98425
author: rothja
ms.author: jroth
ms.openlocfilehash: 26a7a224e700c726ee3d4437321843d45ddb6e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637227"
---
# <a name="insert-transact-sql-snippets"></a><span data-ttu-id="aeb0e-102">Inserimento di frammenti di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aeb0e-102">Insert Transact-SQL Snippets</span></span>
  <span data-ttu-id="aeb0e-103">Un frammento di codice [!INCLUDE[tsql](../../includes/tsql-md.md)] è un modello che è possibile utilizzare come punto iniziale per la scrittura di nuove istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] nell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aeb0e-103">A [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is a template you can use as a starting point when writing new [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="inserting-snippets"></a><span data-ttu-id="aeb0e-104">Inserimento di frammenti</span><span class="sxs-lookup"><span data-stu-id="aeb0e-104">Inserting Snippets</span></span>  
 <span data-ttu-id="aeb0e-105">È possibile usare il menu **Inserisci frammento** per aprire un elenco di frammenti suddiviso per categorie in cui scegliere.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-105">You can use the **Insert Snippet** menu to open a categorized list of snippets to choose from.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="aeb0e-106">I frammenti contengono punti di sostituzione, ovvero un testo che suggerisce la sintassi pertinente per il punto specifico.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-106">snippets contain replacement points: text that suggests the syntax relevant to that point.</span></span> <span data-ttu-id="aeb0e-107">Il frammento CREATE TABLE, ad esempio, include punti di sostituzione per elementi quali nome di tabella, nomi di colonna e tipi di dati di colonna.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-107">For example, the CREATE TABLE snippet has replacement points for elements such as the table name, column names, and column data types.</span></span> <span data-ttu-id="aeb0e-108">Dopo aver inserito il frammento, è necessario modificare il testo di sostituzione per formare un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] valida.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-108">After inserting the snippet, you must change the replacement text to form a valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="aeb0e-109">Per altre informazioni, vedere [Completare frammenti di Transact-SQL](complete-transact-sql-snippets.md).</span><span class="sxs-lookup"><span data-stu-id="aeb0e-109">For more information, see [Complete Transact-SQL Snippets](complete-transact-sql-snippets.md).</span></span>  
  
#### <a name="inserting-a-snippet-by-using-the-insert-snippet-menu"></a><span data-ttu-id="aeb0e-110">Inserimento di un frammento tramite il menu Inserisci frammento</span><span class="sxs-lookup"><span data-stu-id="aeb0e-110">Inserting a Snippet by Using the Insert Snippet Menu</span></span>  
  
1.  <span data-ttu-id="aeb0e-111">Nella finestra dell'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] posizionare il cursore nel punto in cui si desidera inserire il frammento [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aeb0e-111">In the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, put the cursor where you want to insert the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet.</span></span>  
  
2.  <span data-ttu-id="aeb0e-112">Avviare la descrizione comando della selezione frammento in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeb0e-112">Launch the snippet picker tooltip in one of three ways:</span></span>  
  
    -   <span data-ttu-id="aeb0e-113">Premere CTRL+K, CTRL+X.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-113">Press CTRL+K, CTRL+X.</span></span>  
  
    -   <span data-ttu-id="aeb0e-114">Nel menu **Modifica** scegliere **IntelliSense**, quindi fare clic su **Inserisci frammento**.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-114">On the **Edit** menu, point to **IntelliSense**, then click **Insert Snippet**.</span></span>  
  
    -   <span data-ttu-id="aeb0e-115">Fare clic con il pulsante destro del mouse, quindi scegliere **Inserisci frammento** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-115">Right-click the mouse and then select the **Insert Snippet** command from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="aeb0e-116">Fare doppio clic sul frammento o selezionare il frammento dalla selezione frammento, quindi premere TAB o INVIO.</span><span class="sxs-lookup"><span data-stu-id="aeb0e-116">Double-click the snippet, or select the snippet from the snippet picker and then press TAB or ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeb0e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aeb0e-117">See Also</span></span>  
 [<span data-ttu-id="aeb0e-118">Inserire frammenti Transact-SQL racchiusi</span><span class="sxs-lookup"><span data-stu-id="aeb0e-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
