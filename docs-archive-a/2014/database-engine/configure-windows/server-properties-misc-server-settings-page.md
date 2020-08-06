---
title: Proprietà server - pagina Impostazioni varie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.miscserversettings.f1
ms.assetid: b170c066-30cd-42dd-8d34-aa129ea09551
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a82a787140141c3bfa7b18776328a813be9f41f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629601"
---
# <a name="server-properties-misc-server-settings-page"></a><span data-ttu-id="bf0c2-102">Proprietà server (pagina Impostazioni varie)</span><span class="sxs-lookup"><span data-stu-id="bf0c2-102">Server Properties (Misc Server Settings Page)</span></span>
  <span data-ttu-id="bf0c2-103">Utilizzare questa pagina per visualizzare o modificare le impostazioni del server.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-103">Use this page to view or modify your server settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf0c2-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bf0c2-104">Options</span></span>  
 <span data-ttu-id="bf0c2-105">**Lingua predefinita per l'utente**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-105">**Default language for users**</span></span>  
 <span data-ttu-id="bf0c2-106">Specifica la lingua predefinita per tutti i nuovi account di accesso creati.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-106">Specifies the default language for all newly created logins.</span></span>  
  
 <span data-ttu-id="bf0c2-107">**Consenti attivazione di trigger da altri trigger**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-107">**Allow triggers to fire other triggers**</span></span>  
 <span data-ttu-id="bf0c2-108">Consente di controllare l'esecuzione di un'azione da parte di un trigger per l'inizializzazione di un altro trigger.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-108">Controls whether a trigger can perform an action that initiates another trigger.</span></span> <span data-ttu-id="bf0c2-109">Quando questa opzione è deselezionata, i trigger non possono essere attivati da altri trigger.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-109">When cleared, triggers cannot be fired by another trigger.</span></span> <span data-ttu-id="bf0c2-110">Quando questa opzione è selezionata, i trigger possono essere attivati da altri trigger fino a un massimo di 32 livelli.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-110">When selected, triggers can be fired by other triggers to as many as 32 levels.</span></span>  
  
 <span data-ttu-id="bf0c2-111">**Usa Query Governor per evitare query con esecuzione prolungata**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-111">**Use query governor to prevent long-running queries**</span></span>  
 <span data-ttu-id="bf0c2-112">Consente di specificare un limite di tempo massimo entro il quale può essere eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-112">Specifies an upper limit on the time within which a query can run.</span></span> <span data-ttu-id="bf0c2-113">Il costo della query equivale al tempo, in secondi, stimato per l'esecuzione di una query in una configurazione hardware specifica.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-113">Query cost refers to the estimated elapsed time, in seconds, required to execute a query on a specific hardware configuration.</span></span> <span data-ttu-id="bf0c2-114">Per impostazione predefinita, la funzionalità Query Governor è disattivata ed è consentita l'esecuzione di tutte le query.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-114">By default, the query governor is turned off and all queries are allowed to run.</span></span> <span data-ttu-id="bf0c2-115">Se questa opzione è selezionata, è necessario immettere un limite di tempo nella casella di testo sottostante.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-115">If this option is selected, you must enter a time limit in the text box below.</span></span> <span data-ttu-id="bf0c2-116">Se si specifica un valore diverso da zero e positivo, Query Governor non consentirà l'esecuzione delle query il cui costo stimato supera tale valore.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-116">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost exceeding that value.</span></span>  
  
 <span data-ttu-id="bf0c2-117">**Interpreta l'immissione di un anno a due cifre come un anno compreso nell'intervallo dal**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-117">**Interpret a two-digit year as falling between**</span></span>  
 <span data-ttu-id="bf0c2-118">Consente di specificare l'intervallo di date a 100 anni per l'interpretazione dei valori degli anni immessi con due cifre.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-118">Specifies the 100-year date range for interpreting two-digit year values.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="bf0c2-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interpreterà i valori delle date immesse con due cifre come riferiti all'anno che termina per tali cifre e rientra nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will interpret two-digit date values to refer to the year ending in those digits that falls within the specified range.</span></span>  
  
 <span data-ttu-id="bf0c2-120">Impostare l'anno di fine nella casella a destra.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-120">Set the right box with the ending year.</span></span> <span data-ttu-id="bf0c2-121">Quando l'anno di fine viene salvato, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] popola automaticamente la casella a sinistra con l'anno di inizio.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-121">When the ending year is saved, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will automatically populate the left box with the beginning year.</span></span>  
  
 <span data-ttu-id="bf0c2-122">**Valori configurati**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-122">**Configured Values**</span></span>  
 <span data-ttu-id="bf0c2-123">Consente di visualizzare i valori configurati per le opzioni nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-123">Displays the configured values for the options on this pane.</span></span> <span data-ttu-id="bf0c2-124">Se si modificano i valori, fare clic su **Valori correnti** per verificare se le modifiche sono diventate effettive.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-124">If you change these values, click **Running Values** to see whether the changes have taken effect.</span></span> <span data-ttu-id="bf0c2-125">Se le modifiche non sono diventate effettive, è innanzitutto necessario riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf0c2-125">If the changes have not taken effect, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restated first.</span></span>  
  
 <span data-ttu-id="bf0c2-126">**Valori correnti**</span><span class="sxs-lookup"><span data-stu-id="bf0c2-126">**Running Values**</span></span>  
 <span data-ttu-id="bf0c2-127">Consente di visualizzare i valori correnti per le opzioni contenute nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-127">View the currently running values for the options on this pane.</span></span> <span data-ttu-id="bf0c2-128">I valori sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="bf0c2-128">These values are read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0c2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf0c2-129">See Also</span></span>  
 [<span data-ttu-id="bf0c2-130">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bf0c2-130">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
