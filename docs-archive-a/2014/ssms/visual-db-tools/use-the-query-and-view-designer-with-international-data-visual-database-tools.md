---
title: Utilizzo di progettazione query e Progettazione viste con dati internazionali (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719290"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="9120b-102">Utilizzazione di Progettazione query e Progettazione viste con dati internazionali (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9120b-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="9120b-103">È possibile usare [Progettazione query e Progettazione viste](visual-database-tools.md) con dati in qualsiasi lingua e con qualsiasi versione del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="9120b-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="9120b-104">Le seguenti indicazioni evidenziano le differenze esistenti e forniscono informazioni sulla gestione di dati in applicazioni internazionali.</span><span class="sxs-lookup"><span data-stu-id="9120b-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="9120b-105">Informazioni localizzate nei riquadri Criteri e SQL</span><span class="sxs-lookup"><span data-stu-id="9120b-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="9120b-106">Se si utilizza il riquadro Criteri per creare una query, è possibile immettere le informazioni nel formato corrispondente alle impostazioni internazionali di Windows configurate nel computer.</span><span class="sxs-lookup"><span data-stu-id="9120b-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="9120b-107">Se ad esempio si stanno cercando dei dati, è possibile immettere i dati nelle colonne dei criteri utilizzando il formato desiderato, con le seguenti eccezioni:</span><span class="sxs-lookup"><span data-stu-id="9120b-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="9120b-108">I formati di dati long non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9120b-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="9120b-109">I simboli di valuta non dovrebbero essere immessi nel riquadro Criteri.</span><span class="sxs-lookup"><span data-stu-id="9120b-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="9120b-110">I simboli di valuta non verranno visualizzati nel riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="9120b-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9120b-111">Nel riquadro Risultati è possibile immettere il simbolo di valuta che corrisponde alle impostazioni internazionali di Windows del computer in uso, ma verrà rimosso e non sarà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9120b-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="9120b-112">L'operatore meno unario viene sempre visualizzato a sinistra del numero (ad esempio, -1) indipendentemente dalle impostazioni internazionali.</span><span class="sxs-lookup"><span data-stu-id="9120b-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="9120b-113">Al contrario, i dati e le parole chiave nel riquadro SQL devono sempre essere in formato ANSI (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="9120b-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="9120b-114">Quando, ad esempio, in Progettazione query e Progettazione viste viene compilata una query, viene inserito il formato ANSI di tutte le parole chiave SQL quali SELECT e FROM.</span><span class="sxs-lookup"><span data-stu-id="9120b-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="9120b-115">Se si aggiungono elementi all'istruzione nel riquadro SQL, assicurarsi di utilizzare il formato ANSI standard per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="9120b-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="9120b-116">Quando si immettono dati utilizzando un formato locale specifico nel riquadro Criteri, in Progettazione query e Progettazione viste tali dati vengono automaticamente convertiti in formato ANSI nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="9120b-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="9120b-117">Se ad esempio le impostazioni internazionali sono configurate su Tedesco (standard), è possibile immettere i dati nel riquadro Criteri in un formato quale "31.12.96".</span><span class="sxs-lookup"><span data-stu-id="9120b-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="9120b-118">La data tuttavia verrà visualizzata nel riquadro SQL con il formato data e ora ANSI, ovvero come `{ ts '1996-12-31 00:00:00' }.` Se si immettono dati direttamente nel riquadro SQL, è necessario usare il formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="9120b-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="9120b-119">Ordinamento</span><span class="sxs-lookup"><span data-stu-id="9120b-119">Sort Order</span></span>  
 <span data-ttu-id="9120b-120">Il criterio di ordinamento dei dati nella query è determinato dal database.</span><span class="sxs-lookup"><span data-stu-id="9120b-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="9120b-121">Le opzioni impostate nella finestra di dialogo Impostazioni internazionali di Windows non influiscono sui criteri di ordinamento delle query.</span><span class="sxs-lookup"><span data-stu-id="9120b-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="9120b-122">In ciascuna query, tuttavia, è possibile fare in modo che le righe vengano restituite in un particolare ordine.</span><span class="sxs-lookup"><span data-stu-id="9120b-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="9120b-123">Utilizzo di caratteri a byte doppio</span><span class="sxs-lookup"><span data-stu-id="9120b-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="9120b-124">È possibile utilizzare caratteri DBCS per valori letterali o nomi di oggetti di database quali nomi di tabelle e visualizzazioni o alias.</span><span class="sxs-lookup"><span data-stu-id="9120b-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="9120b-125">È inoltre possibile utilizzare caratteri DBCS per i nomi dei parametri e i caratteri dei marcatori dei parametri.</span><span class="sxs-lookup"><span data-stu-id="9120b-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="9120b-126">Non è invece possibile utilizzare caratteri DBCS in elementi del linguaggio SQL quali i nomi delle funzioni o le parole chiave SQL.</span><span class="sxs-lookup"><span data-stu-id="9120b-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9120b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9120b-127">See Also</span></span>  
 [<span data-ttu-id="9120b-128">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9120b-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
