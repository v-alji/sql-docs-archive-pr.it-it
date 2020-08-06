---
title: Finestra di dialogo Visualizzazione dettagliata risultati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.results.f1
- sql12.swb.dmf.policy.resultdetails.f1
ms.assetid: 366f0ff8-722a-40a9-934f-854147e4933d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1c4d669fb1546d27eb8b6ae78e0de8dea5975f24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724543"
---
# <a name="results-detailed-view-dialog-box"></a><span data-ttu-id="1cfea-102">Finestra di dialogo Visualizzazione dettagliata risultati</span><span class="sxs-lookup"><span data-stu-id="1cfea-102">Results Detailed View Dialog Box</span></span>
  <span data-ttu-id="1cfea-103">In questa finestra di dialogo vengono visualizzati i risultati della valutazione dei criteri avviata utilizzando la finestra di dialogo **Valuta criteri** e facendo clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="1cfea-103">This dialog box shows the results of policy evaluation after you have run a policy by using the **Evaluate Policies** dialog box and clicked **Evaluate**.</span></span> <span data-ttu-id="1cfea-104">Questa finestra di dialogo, il cui contenuto è di sola lettura, consente di identificare la parte di un'espressione di proprietà in cui può essersi verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="1cfea-104">This dialog box is read-only, and helps you understand which part of a property expression might be failing.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1cfea-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1cfea-105">Options</span></span>  
 <span data-ttu-id="1cfea-106">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="1cfea-106">**AndOr**</span></span>  
 <span data-ttu-id="1cfea-107">Quando sono presenti più espressioni di proprietà, indica se queste sono cumulative o alternative.</span><span class="sxs-lookup"><span data-stu-id="1cfea-107">When more than one property expression is present, indicates whether the property expressions are cumulative or alternative.</span></span>  
  
 <span data-ttu-id="1cfea-108">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="1cfea-108">**Result**</span></span>  
 <span data-ttu-id="1cfea-109">Icona che rappresenta l'esito positivo o negativo dell'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="1cfea-109">Icon that represents the success or failure of the property expression.</span></span>  
  
 <span data-ttu-id="1cfea-110">**Campo**</span><span class="sxs-lookup"><span data-stu-id="1cfea-110">**Field**</span></span>  
 <span data-ttu-id="1cfea-111">Proprietà del facet da modellare.</span><span class="sxs-lookup"><span data-stu-id="1cfea-111">The property of the facet that is being modeled.</span></span>  
  
 <span data-ttu-id="1cfea-112">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="1cfea-112">**Operator**</span></span>  
 <span data-ttu-id="1cfea-113">Operatore per l'espressione, ad esempio **=** o **Like**.</span><span class="sxs-lookup"><span data-stu-id="1cfea-113">The operator for the expression, for example **=** or **Like**.</span></span>  
  
 <span data-ttu-id="1cfea-114">**Valore previsto**</span><span class="sxs-lookup"><span data-stu-id="1cfea-114">**Expected Value**</span></span>  
 <span data-ttu-id="1cfea-115">Valore per il campo che causa l'esito positivo dell'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="1cfea-115">The value for the field that will cause the property expression to be successful.</span></span>  
  
 <span data-ttu-id="1cfea-116">**Valore effettivo**</span><span class="sxs-lookup"><span data-stu-id="1cfea-116">**Actual Value**</span></span>  
 <span data-ttu-id="1cfea-117">Valore per il campo rilevato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="1cfea-117">The value for the field that was detected by the policy.</span></span>  
  
 <span data-ttu-id="1cfea-118">**Descrizione criteri**</span><span class="sxs-lookup"><span data-stu-id="1cfea-118">**Policy description**</span></span>  
 <span data-ttu-id="1cfea-119">Descrizione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="1cfea-119">The description of the policy.</span></span>  
  
 <span data-ttu-id="1cfea-120">**Informazioni aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="1cfea-120">**Additional help**</span></span>  
 <span data-ttu-id="1cfea-121">Fare clic sul collegamento ipertestuale per aprire una pagina Web correlata ai criteri.</span><span class="sxs-lookup"><span data-stu-id="1cfea-121">Click the hyperlink to open a Web page that is related to this policy.</span></span> <span data-ttu-id="1cfea-122">Il collegamento ipertestuale Guida aggiuntiva viene configurato durante la creazione dei criteri e può essere vuoto o non disponibile.</span><span class="sxs-lookup"><span data-stu-id="1cfea-122">The Additional Help hyperlink is configured when the policy is created and might be blank or unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cfea-123">See Also</span></span>  
 <span data-ttu-id="1cfea-124">[Nodo Gestione criteri &#40;Esplora oggetti&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="1cfea-124">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="1cfea-125">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="1cfea-125">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
