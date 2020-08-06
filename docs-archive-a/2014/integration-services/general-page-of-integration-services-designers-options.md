---
title: Pagina generale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624840"
---
# <a name="general-page"></a><span data-ttu-id="558c9-102">Pagina Generale</span><span class="sxs-lookup"><span data-stu-id="558c9-102">General Page</span></span>
  <span data-ttu-id="558c9-103">Usare la pagina **Generale** della pagina **Finestre di progettazione Integration Services** della finestra di dialogo **Opzioni** per specificare le opzioni per il caricamento, la visualizzazione e l'aggiornamento dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="558c9-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="558c9-104">Per aprire la pagina **Generale** , in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]dal menu **Strumenti** scegliere **Opzioni**, espandere **Finestre di progettazione Business Intelligence**e selezionare **Finestre di progettazione Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="558c9-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="558c9-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="558c9-105">Options</span></span>  
 <span data-ttu-id="558c9-106">**Controlla firma digitale al caricamento di un pacchetto**</span><span class="sxs-lookup"><span data-stu-id="558c9-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="558c9-107">Selezionare questa opzione per fare in modo che [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] controlli la firma digitale al caricamento di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="558c9-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="558c9-108">controllerà solo se la firma digitale è presente, è valida e proviene da una fonte attendibile.</span><span class="sxs-lookup"><span data-stu-id="558c9-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="558c9-109">non controlla se il pacchetto è stato modificato dopo la firma.</span><span class="sxs-lookup"><span data-stu-id="558c9-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="558c9-110">Se si imposta il valore del Registro di sistema **BlockedSignatureStates** , tale valore ha la priorità sull'opzione **Controlla firma digitale al caricamento di un pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="558c9-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="558c9-111">Per altre informazioni, vedere [Implementazione di criteri per le firme impostando un valore del Registro di sistema](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="558c9-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="558c9-112">Per altre informazioni sui certificati e i pacchetti digitali, vedere [Identificazione dell'origine dei pacchetti con firme digitali](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="558c9-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="558c9-113">**Mostra avviso se il pacchetto non è firmato**</span><span class="sxs-lookup"><span data-stu-id="558c9-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="558c9-114">Selezionare questa opzione per visualizzare un avviso quando viene caricato un pacchetto non firmato.</span><span class="sxs-lookup"><span data-stu-id="558c9-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="558c9-115">**Mostra etichette vincolo di precedenza**</span><span class="sxs-lookup"><span data-stu-id="558c9-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="558c9-116">Selezionare l'etichetta (Esito positivo, Esito negativo o Completamento) da visualizzare nei vincoli di precedenza durante la visualizzazione dei pacchetti in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="558c9-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="558c9-117">**Linguaggio di scripting**</span><span class="sxs-lookup"><span data-stu-id="558c9-117">**Scripting language**</span></span>  
 <span data-ttu-id="558c9-118">Selezionare il linguaggio di scripting predefinito per le nuove attività Script e per i componenti Script.</span><span class="sxs-lookup"><span data-stu-id="558c9-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="558c9-119">**Aggiorna stringhe di connessione per l'uso di nuovi nomi di provider**</span><span class="sxs-lookup"><span data-stu-id="558c9-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="558c9-120">Quando si aprono o si aggiornano pacchetti di [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , aggiornare le stringhe di connessione in modo da usare i nomi dei provider seguenti, per la versione corrente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="558c9-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="558c9-121">Provider OLE DB</span><span class="sxs-lookup"><span data-stu-id="558c9-121">OLE DB provider</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="558c9-122">Native Client</span><span class="sxs-lookup"><span data-stu-id="558c9-122">Native Client</span></span>  
  
 <span data-ttu-id="558c9-123">L'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] consente di aggiornare solo le stringhe di connessione archiviate nelle gestioni connessione.</span><span class="sxs-lookup"><span data-stu-id="558c9-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="558c9-124">Non vengono aggiornate le stringhe di connessione costruite dinamicamente utilizzando il linguaggio delle espressioni di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o il codice in un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="558c9-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="558c9-125">**Crea nuovo ID pacchetto**</span><span class="sxs-lookup"><span data-stu-id="558c9-125">**Create new package ID**</span></span>  
 <span data-ttu-id="558c9-126">Durante l'aggiornamento di [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , creare nuovi ID pacchetti per le versioni aggiornate dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="558c9-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558c9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="558c9-127">See Also</span></span>  
 <span data-ttu-id="558c9-128">[Panoramica sulla sicurezza &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="558c9-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="558c9-129">Estensione di pacchetti tramite scripting</span><span class="sxs-lookup"><span data-stu-id="558c9-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
