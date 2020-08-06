---
title: Finestra di dialogo Importa criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624687"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="4df54-102">Finestra di dialogo Importa criteri</span><span class="sxs-lookup"><span data-stu-id="4df54-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="4df54-103">Utilizzare questa finestra di dialogo per importare nell'istanza corrente del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] i criteri salvati come file XML e le relative condizioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4df54-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4df54-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4df54-104">Options</span></span>  
 <span data-ttu-id="4df54-105">**File da importare**</span><span class="sxs-lookup"><span data-stu-id="4df54-105">**Files to import**</span></span>  
 <span data-ttu-id="4df54-106">Per importare i criteri da un file XML, digitare il percorso e il nome del file oppure usare il pulsante Sfoglia ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="4df54-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="4df54-107">**Sostituisci duplicati con gli elementi importati**</span><span class="sxs-lookup"><span data-stu-id="4df54-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="4df54-108">Selezionare questa opzione per sovrascrivere eventuali criteri o condizioni con lo stesso nome che esistono già nell'istanza corrente del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4df54-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="4df54-109">Non è possibile sovrascrivere una condizione con criteri dipendenti, a meno che non vengano sovrascritti anche questi ultimi.</span><span class="sxs-lookup"><span data-stu-id="4df54-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="4df54-110">Se questa opzione non viene selezionata, una condizione esistente che utilizza la stessa espressione di condizione non genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="4df54-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="4df54-111">**Stato criteri**</span><span class="sxs-lookup"><span data-stu-id="4df54-111">**Policy state**</span></span>  
 <span data-ttu-id="4df54-112">Consente di selezionare lo stato desiderato per i criteri importati:</span><span class="sxs-lookup"><span data-stu-id="4df54-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="4df54-113">**Mantieni lo stato dei criteri durante l'importazione**</span><span class="sxs-lookup"><span data-stu-id="4df54-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="4df54-114">**Abilita tutti i criteri durante l'importazione**</span><span class="sxs-lookup"><span data-stu-id="4df54-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="4df54-115">**Disabilita tutti i criteri durante l'importazione**</span><span class="sxs-lookup"><span data-stu-id="4df54-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df54-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4df54-116">See Also</span></span>  
 <span data-ttu-id="4df54-117">[Amministrazione di server tramite la gestione basata su criteri](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="4df54-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="4df54-118">[Importare i criteri della gestione basata su criteri](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="4df54-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="4df54-119">Esportare i criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="4df54-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
