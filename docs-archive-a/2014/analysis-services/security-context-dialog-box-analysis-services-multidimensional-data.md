---
title: Finestra di dialogo contesto di sicurezza (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625611"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="d007e-102">Finestra di dialogo Contesto di sicurezza (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="d007e-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d007e-103">Utilizzare la finestra di dialogo **Contesto di sicurezza** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per modificare l'utente e il ruolo utilizzati per analizzare i dati o i metadati per un oggetto [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d007e-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="d007e-104">Per visualizzare la finestra di dialogo **Contesto di sicurezza** fare clic su **Contesto di sicurezza** nel riquadro **Barra degli strumenti** della scheda **Calcoli** o della scheda **Esplorazione** in Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="d007e-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d007e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d007e-105">Options</span></span>  
 <span data-ttu-id="d007e-106">**Utente corrente**</span><span class="sxs-lookup"><span data-stu-id="d007e-106">**Current user**</span></span>  
 <span data-ttu-id="d007e-107">Consente di utilizzare il dominio e il nome dell'utente corrente durante la visualizzazione dei dati e dei metadati dell'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d007e-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="d007e-108">**Altro utente**</span><span class="sxs-lookup"><span data-stu-id="d007e-108">**Other user**</span></span>  
 <span data-ttu-id="d007e-109">Consente di digitare il dominio e il nome di un altro utente o gruppo da usare durante la visualizzazione dei dati e dei metadati dell'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d007e-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="d007e-110">Il dominio e il nome dell'utente o del gruppo utilizzano il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d007e-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="d007e-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="d007e-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="d007e-112">**Ruoli**</span><span class="sxs-lookup"><span data-stu-id="d007e-112">**Roles**</span></span>  
 <span data-ttu-id="d007e-113">Selezionare questa casella di controllo per utilizzare uno o più ruoli specificati durante la visualizzazione dei dati e dei metadati dell'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d007e-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="d007e-114">Se nel database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sono definiti più ruoli è possibile selezionare i ruoli da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d007e-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d007e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d007e-115">See Also</span></span>  
 <span data-ttu-id="d007e-116">[Indicatori KPI &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d007e-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="d007e-117">[Progettazione cubi &#40;browser&#41; &#40;Analysis Services Dati multidimensionali&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d007e-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="d007e-118">Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="d007e-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
