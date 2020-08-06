---
title: Informazioni parametri (IntelliSense)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
author: rothja
ms.author: jroth
ms.openlocfilehash: b7e5e7496753006808f75378182db0d3cb606d4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636669"
---
# <a name="parameter-info-intellisense"></a><span data-ttu-id="115e2-102">Informazioni parametri (IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="115e2-102">Parameter Info (IntelliSense)</span></span>
  <span data-ttu-id="115e2-103">L'opzione [!INCLUDE[msCoName](../../includes/msconame-md.md)] Informazione sul parametro **di** IntelliSense consente di aprire un elenco di parametri che include informazioni relative a numero, nomi e tipi dei parametri necessari per una funzione o per una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="115e2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense **Parameter Info** option opens a parameters list that provides information about the number, names, and types of the parameters that are required by a function or stored procedure.</span></span> <span data-ttu-id="115e2-104">Il parametro in grassetto indica il parametro successivo necessario quando viene digitata una funzione o una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="115e2-104">The parameter in bold indicates the next parameter that is required as you type a function or stored procedure.</span></span>  
  
 <span data-ttu-id="115e2-105">L'elenco dei parametri è visualizzato anche per le funzioni nidificate.</span><span class="sxs-lookup"><span data-stu-id="115e2-105">The parameter list is also displayed for nested functions.</span></span> <span data-ttu-id="115e2-106">Se si digita una funzione come parametro per un'altra funzione, nell'elenco dei parametri verranno visualizzati i parametri per la funzione interna.</span><span class="sxs-lookup"><span data-stu-id="115e2-106">If you type a function as a parameter to another function, the parameter list displays the parameters for the inner function.</span></span> <span data-ttu-id="115e2-107">Quando l'elenco dei parametri della funzione interna è completo, verranno quindi visualizzati i parametri della funzione esterna.</span><span class="sxs-lookup"><span data-stu-id="115e2-107">Then, when the inner function parameter list is complete, the parameter list reverts to displaying the outer function parameters.</span></span>  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a><span data-ttu-id="115e2-108">Per visualizzare le informazioni sul parametro per le funzioni o le stored procedure</span><span class="sxs-lookup"><span data-stu-id="115e2-108">To view Parameter Info for functions or stored procedures</span></span>  
  
1.  <span data-ttu-id="115e2-109">Dopo il nome di una funzione, digitare una normale parentesi aperta per aprire l'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="115e2-109">After the name of a function, type an open parenthesis as you usually type to open the parameters list.</span></span> <span data-ttu-id="115e2-110">Dopo avere digitato il nome di una stored procedure, digitare un normale spazio per ottenere informazioni sui parametri della procedura.</span><span class="sxs-lookup"><span data-stu-id="115e2-110">After you type the name of a stored procedure, type a space as you usually type to obtain information about the procedure parameters.</span></span>  
  
     <span data-ttu-id="115e2-111">In IntelliSense viene visualizzata la dichiarazione completa per la funzione o per i parametri di una stored procedure in una finestra popup subito al di sotto del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="115e2-111">IntelliSense displays the complete declaration for the function or the parameters for a stored procedure in a pop-up window just under the insertion point.</span></span> <span data-ttu-id="115e2-112">Il primo parametro dell'elenco viene visualizzato in grassetto.</span><span class="sxs-lookup"><span data-stu-id="115e2-112">The first parameter in the list appears in bold.</span></span>  
  
2.  <span data-ttu-id="115e2-113">Durante l'immissione dei parametri, il grassetto cambia per indicare il parametro successivo da immettere.</span><span class="sxs-lookup"><span data-stu-id="115e2-113">As you type the parameters, the bold font changes to reflect the next parameter that you need to enter.</span></span>  
  
3.  <span data-ttu-id="115e2-114">Premere ESC in qualsiasi momento per chiudere l'elenco oppure continuare a digitare fino a completare la funzione.</span><span class="sxs-lookup"><span data-stu-id="115e2-114">Press ESC at any time to close the list, or continue typing until you have completed the function.</span></span>  
  
     <span data-ttu-id="115e2-115">Nel caso di una funzione, se viene digitata la parentesi di chiusura viene chiuso anche l'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="115e2-115">For a function, if you type the closing parenthesis you also close the parameter list.</span></span>  
  
#### <a name="to-manually-start-parameter-info"></a><span data-ttu-id="115e2-116">Per avviare manualmente l'opzione Informazioni sul parametro</span><span class="sxs-lookup"><span data-stu-id="115e2-116">To manually start Parameter Info</span></span>  
  
1.  <span data-ttu-id="115e2-117">Scegliere **IntelliSense** dal menu **Modifica** , quindi selezionare **Informazioni parametri**.</span><span class="sxs-lookup"><span data-stu-id="115e2-117">On the **Edit** menu, select **IntelliSense** and then select **Parameter Info**.</span></span>  
  
2.  <span data-ttu-id="115e2-118">Utilizzare i tasti di scelta rapida CTRL+MAIUSC+BARRA SPAZIATRICE.</span><span class="sxs-lookup"><span data-stu-id="115e2-118">Press the CTRL+SHIFT+SPACE keyboard shortcut.</span></span>  
  
 <span data-ttu-id="115e2-119">Per altre informazioni, vedere [Configurare IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="115e2-119">For more information, see [Configure IntelliSense &#40;SQL Server Management Studio&#41;](configure-intellisense-sql-server-management-studio.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="115e2-120">L'opzione **Informazioni parametri** è disponibile solo per l'editor di query di [!INCLUDE[ssDE](../../includes/ssde-md.md)] e per l'editor di query XML.</span><span class="sxs-lookup"><span data-stu-id="115e2-120">The **Parameter Info** option is available only for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor and the XML Query Editor.</span></span>  
  
  
