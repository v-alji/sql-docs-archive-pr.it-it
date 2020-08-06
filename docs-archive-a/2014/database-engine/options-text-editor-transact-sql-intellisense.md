---
title: Opzioni (editor di testo-Transact-SQL-IntelliSense) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.Advanced
- VS.ToolsOptionsPages.Text_Editor.SQL_Server_Tools.Advanced
dev_langs:
- TSQL
ms.assetid: 1855d916-5bf9-4d94-b0fb-9f9bb05ff950
author: rothja
ms.author: jroth
ms.openlocfilehash: 2d8f9c865516dc5e4c0ddadbdc908a9b4c8ec366
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635203"
---
# <a name="options-text-editor-transact-sql-intellisense"></a><span data-ttu-id="4d4d2-102">Opzioni (editor di testo-Transact-SQL-IntelliSense)</span><span class="sxs-lookup"><span data-stu-id="4d4d2-102">Options (Text Editor-Transact-SQL-IntelliSense)</span></span>
  <span data-ttu-id="4d4d2-103">La finestra di dialogo **Opzioni** consente di modificare le impostazioni IntelliSense per l'editor di query del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d4d2-103">The **Options** dialog box lets you change the IntelliSense settings for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="4d4d2-104">Per visualizzare queste impostazioni, scegliere **Opzioni** dal menu **Strumenti**, espandere la cartella **Editor di testo**, espandere la cartella **Transact-SQL** e fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, expand the **Transact-SQL** folder, and then click **Advanced**.</span></span>  
  
## <a name="transact-sql-intellisense-settings"></a><span data-ttu-id="4d4d2-105">Impostazioni IntelliSense per Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d4d2-105">Transact-SQL IntelliSense Settings</span></span>  
 <span data-ttu-id="4d4d2-106">Specifica le opzioni IntelliSense per l'editor di query del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d4d2-106">Specifies the IntelliSense options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor.</span></span>  
  
### <a name="enable-intellisense"></a><span data-ttu-id="4d4d2-107">Abilitazione di IntelliSense</span><span class="sxs-lookup"><span data-stu-id="4d4d2-107">Enable IntelliSense</span></span>  
 <span data-ttu-id="4d4d2-108">Abilita le caratteristiche IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-108">Enables the IntelliSense features.</span></span> <span data-ttu-id="4d4d2-109">Quando questa casella non è selezionata, le opzioni IntelliSense non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-109">When this box is not selected, the specific IntelliSense options are unavailable.</span></span> <span data-ttu-id="4d4d2-110">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-110">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4d4d2-111">**Sottolinea errori**</span><span class="sxs-lookup"><span data-stu-id="4d4d2-111">**Underline errors**</span></span>  
 <span data-ttu-id="4d4d2-112">Identifica errori semantici e di sintassi nelle istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-112">Identifies syntax and semantic errors in [!INCLUDE[tsql](../includes/tsql-md.md)] statements in the query window.</span></span> <span data-ttu-id="4d4d2-113">Tutti gli errori e gli avvisi sono visualizzati in rosso.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-113">All errors and warnings appear in red.</span></span> <span data-ttu-id="4d4d2-114">Errori e avvisi sono supportati solo per le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] per le quali è stato implementato IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-114">Errors and warnings are supported only for the [!INCLUDE[tsql](../includes/tsql-md.md)] statements for which IntelliSense has been implemented.</span></span> <span data-ttu-id="4d4d2-115">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-115">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4d4d2-116">**Struttura istruzioni**</span><span class="sxs-lookup"><span data-stu-id="4d4d2-116">**Outline statements**</span></span>  
 <span data-ttu-id="4d4d2-117">Abilita la modalità struttura quando viene aperto un file</span><span class="sxs-lookup"><span data-stu-id="4d4d2-117">Enables the outlining feature when a file is opened.</span></span> <span data-ttu-id="4d4d2-118">in modo da creare blocchi comprimibili del codice [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d4d2-118">This creates collapsible blocks of [!INCLUDE[tsql](../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="4d4d2-119">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-119">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="4d4d2-120">**Dimensione massima script**</span><span class="sxs-lookup"><span data-stu-id="4d4d2-120">**Maximum script size**</span></span>  
 <span data-ttu-id="4d4d2-121">Specifica la dimensione in base alla quale la funzionalità IntelliSense viene disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-121">Specifies the size at which IntelliSense functionality is disabled.</span></span> <span data-ttu-id="4d4d2-122">Se uno script supera la dimensione specificata, viene visualizzato un messaggio di avviso e</span><span class="sxs-lookup"><span data-stu-id="4d4d2-122">If a script exceeds the specified size, a warning message is issued.</span></span> <span data-ttu-id="4d4d2-123">tutte le caratteristiche IntelliSense vengono disabilitate per quella finestra dell'editor, ad eccezione del codice a colori.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-123">All IntelliSense features, except color coding, are disabled for that editor window.</span></span> <span data-ttu-id="4d4d2-124">IntelliSense è riabilitato quando si elimina del testo per ridurre la dimensione dello script entro il limite specificato.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-124">IntelliSense is reenabled when enough text is deleted to reduce the script size to under the limit.</span></span> <span data-ttu-id="4d4d2-125">L'abilitazione di IntelliSense in caso di script di grandi dimensioni può ridurre le prestazioni di computer lenti.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-125">Enabling IntelliSense for large script sizes can decrease performance on slow computers.</span></span> <span data-ttu-id="4d4d2-126">Le dimensioni consentite sono 100 KB, 500 KB, 1 MB, 2 MB e Illimitate.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-126">The allowed sizes are 100 KB, 500 KB, 1 MB, 2 MB, and Unlimited.</span></span> <span data-ttu-id="4d4d2-127">Il valore predefinito è 1 MB.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-127">The default is 1 MB.</span></span>  
  
 <span data-ttu-id="4d4d2-128">**Combinazione di maiuscole e minuscole per nomi di funzioni predefinite**</span><span class="sxs-lookup"><span data-stu-id="4d4d2-128">**Casing for built-in function names**</span></span>  
 <span data-ttu-id="4d4d2-129">Specifica se i nomi delle funzioni [!INCLUDE[tsql](../includes/tsql-md.md)] predefinite inclusi negli elenchi di completamento usano lettere maiuscole, ad esempio DATEADD, o lettere minuscole, ad esempio dateadd.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-129">Specifies whether the names of built-in [!INCLUDE[tsql](../includes/tsql-md.md)] functions that are included in completion lists use uppercase letters, such as DATEADD; or lowercase letters, such as dateadd.</span></span> <span data-ttu-id="4d4d2-130">Selezionare l'opzione corrispondente alle convenzioni di scrittura del codice [!INCLUDE[tsql](../includes/tsql-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="4d4d2-130">Select the option that best matches the [!INCLUDE[tsql](../includes/tsql-md.md)] coding conventions that you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4d2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d4d2-131">See Also</span></span>  
 [<span data-ttu-id="4d4d2-132">Risoluzione dei problemi relativi a IntelliSense &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4d2-132">Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/troubleshooting-intellisense.md)  
  
  
