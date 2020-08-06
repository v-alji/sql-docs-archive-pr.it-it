---
title: Codifica con colori negli editor di query
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f23b37cec051b52082cdb310a134a4603423b8c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627154"
---
# <a name="color-coding-in-query-editors"></a><span data-ttu-id="1c00d-102">Codifica con colori negli editor di query</span><span class="sxs-lookup"><span data-stu-id="1c00d-102">Color Coding in Query Editors</span></span>
  <span data-ttu-id="1c00d-103">Al testo immesso negli editor del codice viene assegnata una categoria. Ogni categoria viene identificata con un colore.</span><span class="sxs-lookup"><span data-stu-id="1c00d-103">The text entered in the code editors is assigned a category; each category is identified by a color.</span></span> <span data-ttu-id="1c00d-104">I colore consentono di individuare rapidamente il testo nel codice.</span><span class="sxs-lookup"><span data-stu-id="1c00d-104">The colors help you quickly find text in your code.</span></span> <span data-ttu-id="1c00d-105">I commenti ad esempio vengono evidenziati con il colore verde scuro.</span><span class="sxs-lookup"><span data-stu-id="1c00d-105">For example, comments stand out in dark green.</span></span> <span data-ttu-id="1c00d-106">Nella tabella seguente sono riportati i colori più comuni.</span><span class="sxs-lookup"><span data-stu-id="1c00d-106">The following table lists the most common colors.</span></span> <span data-ttu-id="1c00d-107">È possibile visualizzare l'intero elenco dei colori e le relative categorie e configurare uno schema di colori personalizzato dal menu **Strumenti**, **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="1c00d-107">You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools**, **Options** menu.</span></span> <span data-ttu-id="1c00d-108">Per altre informazioni su come modificare i colori predefiniti, vedere [Modificare lo stile, le dimensioni e il colore del carattere](change-font-color-size-and-style.md).</span><span class="sxs-lookup"><span data-stu-id="1c00d-108">For more information about how to change the default colors, see [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span></span>  
  
## <a name="default-code-colors"></a><span data-ttu-id="1c00d-109">Colori del codice predefiniti</span><span class="sxs-lookup"><span data-stu-id="1c00d-109">Default Code Colors</span></span>  
  
|<span data-ttu-id="1c00d-110">Colore</span><span class="sxs-lookup"><span data-stu-id="1c00d-110">Color</span></span>|<span data-ttu-id="1c00d-111">Category</span><span class="sxs-lookup"><span data-stu-id="1c00d-111">Category</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="1c00d-112">Rosso</span><span class="sxs-lookup"><span data-stu-id="1c00d-112">Red</span></span>|<span data-ttu-id="1c00d-113">Stringa SQL</span><span class="sxs-lookup"><span data-stu-id="1c00d-113">SQL string</span></span>|  
|<span data-ttu-id="1c00d-114">Verde scuro</span><span class="sxs-lookup"><span data-stu-id="1c00d-114">Dark green</span></span>|<span data-ttu-id="1c00d-115">Comment</span><span class="sxs-lookup"><span data-stu-id="1c00d-115">Comment</span></span>|  
|<span data-ttu-id="1c00d-116">Nero su sfondo argento</span><span class="sxs-lookup"><span data-stu-id="1c00d-116">Black on silver background</span></span>|<span data-ttu-id="1c00d-117">Comando SQLCMD</span><span class="sxs-lookup"><span data-stu-id="1c00d-117">SQLCMD command</span></span>|  
|<span data-ttu-id="1c00d-118">Fucsia</span><span class="sxs-lookup"><span data-stu-id="1c00d-118">Magenta</span></span>|<span data-ttu-id="1c00d-119">Funzioni di sistema</span><span class="sxs-lookup"><span data-stu-id="1c00d-119">System function</span></span>|  
|<span data-ttu-id="1c00d-120">Green</span><span class="sxs-lookup"><span data-stu-id="1c00d-120">Green</span></span>|<span data-ttu-id="1c00d-121">Tabella di sistema o funzione con valori di tabella,</span><span class="sxs-lookup"><span data-stu-id="1c00d-121">System table, view, or table-valued function.</span></span> <span data-ttu-id="1c00d-122">nonché gli schemi di sistema sys e INFORMATION_SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="1c00d-122">Also, the system schemas sys and INFORMATION_SCHEMA.</span></span>|  
|<span data-ttu-id="1c00d-123">Blu</span><span class="sxs-lookup"><span data-stu-id="1c00d-123">Blue</span></span>|<span data-ttu-id="1c00d-124">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="1c00d-124">Keyword</span></span>|  
|<span data-ttu-id="1c00d-125">Verde acqua</span><span class="sxs-lookup"><span data-stu-id="1c00d-125">Teal</span></span>|<span data-ttu-id="1c00d-126">Numeri di riga o parametro modello</span><span class="sxs-lookup"><span data-stu-id="1c00d-126">Line numbers or template parameter</span></span>|  
|<span data-ttu-id="1c00d-127">Bordeaux</span><span class="sxs-lookup"><span data-stu-id="1c00d-127">Maroon</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1c00d-128">stored procedure</span><span class="sxs-lookup"><span data-stu-id="1c00d-128">stored procedure</span></span>|  
|<span data-ttu-id="1c00d-129">Grigio scuro</span><span class="sxs-lookup"><span data-stu-id="1c00d-129">Dark gray</span></span>|<span data-ttu-id="1c00d-130">Operatori</span><span class="sxs-lookup"><span data-stu-id="1c00d-130">Operators</span></span>|  
  
## <a name="status-bar"></a><span data-ttu-id="1c00d-131">Barra di stato</span><span class="sxs-lookup"><span data-stu-id="1c00d-131">Status Bar</span></span>  
 <span data-ttu-id="1c00d-132">È possibile configurare server registrati o server [!INCLUDE[ssDE](../../includes/ssde-md.md)] in Esplora oggetti per avere colori diversi nella barra di stato dell'Editor di query [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c00d-132">You can configure registered servers or [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor status bar.</span></span> <span data-ttu-id="1c00d-133">Ciò consente di identificare a quale server è connessa ogni finestra dell'editor quando si dispone di molte finestre aperte contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1c00d-133">This helps you identify which server each editor window is connected to when you have many windows open at the same time.</span></span> <span data-ttu-id="1c00d-134">Per altre informazioni sull'impostazione dei colori della barra di stato, vedere [Barra di stato &#40;editor di query del motore di database&#41;](status-bar-database-engine-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="1c00d-134">For more information about setting status bar colors, see [Status Bar &#40;Database Engine Query Editor&#41;](status-bar-database-engine-query-editor.md).</span></span>  
  
 <span data-ttu-id="1c00d-135">In alcuni tipi di editor la barra di stato non viene visualizzata oppure non supporta più colori.</span><span class="sxs-lookup"><span data-stu-id="1c00d-135">Some types of editors do not display the status bar, or do not support multiple colors.</span></span>  
  
  
