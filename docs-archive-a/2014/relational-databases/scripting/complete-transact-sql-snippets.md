---
title: Completare frammenti di Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], completing snippets
- snippets [Transact-SQL], completing
- Transact-SQL snippets, completing
ms.assetid: a8316a58-bb57-485e-845f-84c23360314c
author: rothja
ms.author: jroth
ms.openlocfilehash: d90c77f72ba8ce80d26503645d9b04d795f5e503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627152"
---
# <a name="complete-transact-sql-snippets"></a><span data-ttu-id="9b07f-102">Completare frammenti di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b07f-102">Complete Transact-SQL Snippets</span></span>
  <span data-ttu-id="9b07f-103">Dopo aver inserito un frammento di codice [!INCLUDE[tsql](../../includes/tsql-md.md)] in uno script, è necessario modificare il contenuto del frammento per compilare un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] completa.</span><span class="sxs-lookup"><span data-stu-id="9b07f-103">Once a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet has been inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="completing-snippets"></a><span data-ttu-id="9b07f-104">Completamento di frammenti</span><span class="sxs-lookup"><span data-stu-id="9b07f-104">Completing Snippets</span></span>  
 <span data-ttu-id="9b07f-105">Quando si aggiunge un frammento [!INCLUDE[tsql](../../includes/tsql-md.md)] allo script, l'istruzione del frammento inserito include uno o più punti di sostituzione, evidenziati.</span><span class="sxs-lookup"><span data-stu-id="9b07f-105">When you add a [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted.</span></span> <span data-ttu-id="9b07f-106">Se si posiziona il puntatore del mouse su un punto di sostituzione, viene visualizzata una descrizione comando con una descrizione dell'elemento di sintassi che è possibile specificare.</span><span class="sxs-lookup"><span data-stu-id="9b07f-106">If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify.</span></span> <span data-ttu-id="9b07f-107">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] riconosce il frammento come separato dallo script circostante fino a quando non si chiude il file di origine.</span><span class="sxs-lookup"><span data-stu-id="9b07f-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file.</span></span> <span data-ttu-id="9b07f-108">I punti di sostituzione rimangono attivi fino a quando non si chiude il file di origine.</span><span class="sxs-lookup"><span data-stu-id="9b07f-108">The replacement points remain active until you close the source file.</span></span>  
  
 <span data-ttu-id="9b07f-109">È inoltre possibile aggiungere altri elementi di sintassi al codice del modello inserito da un frammento.</span><span class="sxs-lookup"><span data-stu-id="9b07f-109">You can also add additional syntax elements to the template code inserted by a snippet.</span></span> <span data-ttu-id="9b07f-110">Il modello di frammento Crea tabella, ad esempio, genera due definizioni di colonna. È necessario aggiungere altre definizioni di colonna per creare una tabella con più di due colonne.</span><span class="sxs-lookup"><span data-stu-id="9b07f-110">For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.</span></span>  
  
#### <a name="completing-the-snippet-statement"></a><span data-ttu-id="9b07f-111">Completamento dell'istruzione del frammento</span><span class="sxs-lookup"><span data-stu-id="9b07f-111">Completing the Snippet Statement</span></span>  
  
1.  <span data-ttu-id="9b07f-112">Utilizzare il tasto TAB per spostarsi da un punto di sostituzione al successivo.</span><span class="sxs-lookup"><span data-stu-id="9b07f-112">Use the TAB key to move from one replacement point to the next.</span></span> <span data-ttu-id="9b07f-113">Utilizzare MAIUSC+TAB per spostarsi al punto di sostituzione precedente.</span><span class="sxs-lookup"><span data-stu-id="9b07f-113">Use SHIFT+TAB to move to the previous replacement point.</span></span>  
  
2.  <span data-ttu-id="9b07f-114">Premere CTRL+BARRA SPAZIATRICE per richiamare IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9b07f-114">Click CTRL+SPACE to invoke IntelliSense.</span></span>  
  
3.  <span data-ttu-id="9b07f-115">Selezionare un elemento nell'elenco o digitare una sostituzione desiderata.</span><span class="sxs-lookup"><span data-stu-id="9b07f-115">Select an item from the list, or type a replacement of your choice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b07f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b07f-116">See Also</span></span>  
 <span data-ttu-id="9b07f-117">[Inserimento di frammenti di Transact-SQL](insert-transact-sql-snippets.md) </span><span class="sxs-lookup"><span data-stu-id="9b07f-117">[Insert Transact-SQL Snippets](insert-transact-sql-snippets.md) </span></span>  
 [<span data-ttu-id="9b07f-118">Inserire frammenti Transact-SQL racchiusi</span><span class="sxs-lookup"><span data-stu-id="9b07f-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
