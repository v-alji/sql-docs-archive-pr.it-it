---
title: Ricerca di report e altri elementi (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623853"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="403a0-102">Ricerca di report e altri elementi (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="403a0-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="403a0-103">È possibile utilizzare Gestione report per cercare elementi specifici in un server di report utilizzando il nome o la descrizione degli elementi come criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="403a0-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="403a0-104">È possibile cercare report pubblicati, modelli di report, cartelle, origini dei dati condivise e risorse.</span><span class="sxs-lookup"><span data-stu-id="403a0-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="403a0-105">Non è possibile cercare pianificazioni, proprietari, assegnazioni di ruolo, snapshot specifici della cronologia dei report o sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="403a0-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="403a0-106">La ricerca viene eseguita nel database del server di report in cui vengono archiviati gli elementi.</span><span class="sxs-lookup"><span data-stu-id="403a0-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="403a0-107">Se si esegue una ricerca nel file system, nei risultati non saranno compresi elementi gestiti da un server di report.</span><span class="sxs-lookup"><span data-stu-id="403a0-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="403a0-108">Per cercare elementi in Gestione report, digitare una stringa di ricerca nella casella di testo **Cerca** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="403a0-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="403a0-109">Le ricerche iniziano dal nodo principale della gerarchia di cartelle e proseguono in ogni ramo.</span><span class="sxs-lookup"><span data-stu-id="403a0-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="403a0-110">Se non si dispone delle autorizzazioni per l'accesso a un ramo specifico, questo viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="403a0-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="403a0-111">Questa regola è valida per le cartelle Report personali appartenenti ad altri utenti e per altre cartelle che in genere non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="403a0-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="403a0-112">Nei risultati delle ricerche sono inclusi solo i report e gli elementi che l'utente che esegue la ricerca è autorizzato a visualizzare.</span><span class="sxs-lookup"><span data-stu-id="403a0-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="403a0-113">Per cercare un elemento in base al nome o alla descrizione, specificare tutto il testo per il quale si desidera trovare una corrispondenza o solo parte di esso.</span><span class="sxs-lookup"><span data-stu-id="403a0-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="403a0-114">La stringa di ricerca non supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="403a0-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="403a0-115">Non è possibile usare operatori di ricerca quali i segni di addizione (+) o di sottrazione (–) per includere o escludere i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="403a0-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="403a0-116">Per cercare testo specifico all'interno di un report, utilizzare la barra degli strumenti nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="403a0-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="403a0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="403a0-117">See Also</span></span>  
 <span data-ttu-id="403a0-118">[Ricerca e visualizzazione di report in Gestione report &#40;Generatore report e SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="403a0-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="403a0-119">[Uso di Report personali &#40;Generatore report e SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="403a0-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="403a0-120">[Ricerca, visualizzazione e gestione dei report &#40;Generatore report e SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="403a0-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="403a0-121">Aprire e chiudere un report &#40;Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="403a0-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
