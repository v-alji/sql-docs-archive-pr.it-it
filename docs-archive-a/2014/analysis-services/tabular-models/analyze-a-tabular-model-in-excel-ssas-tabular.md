---
title: Analizzare un modello tabulare in Excel (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635738"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="6739c-102">Analizzare un modello tabulare in Excel (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="6739c-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="6739c-103">La funzionalità Analizza in Excel di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] consente di aprire Microsoft Excel, di creare una connessione dell'origine dati al database dell'area di lavoro del modello e di aggiungere automaticamente una tabella pivot al foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6739c-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="6739c-104">Gli oggetti del modello (tabelle, colonne, misure, gerarchie e indicatori KPI) sono inclusi come campi nel relativo elenco della tabella pivot.</span><span class="sxs-lookup"><span data-stu-id="6739c-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6739c-105">Per usare la funzionalità Analizza in Excel, è necessario che Microsoft Office 2003 o versione successiva sia installato nello stesso computer di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6739c-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="6739c-106">In caso contrario, è possibile utilizzare Excel in un altro computer e connettersi al database dell'area di lavoro modello come origine dati.</span><span class="sxs-lookup"><span data-stu-id="6739c-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="6739c-107">Successivamente, è possibile aggiungere manualmente una tabella pivot al foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6739c-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="6739c-108">Gli oggetti del modello (tabelle, colonne, misure e indicatori KPI) sono inclusi come campi nel relativo elenco della tabella pivot.</span><span class="sxs-lookup"><span data-stu-id="6739c-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="6739c-109">Attività</span><span class="sxs-lookup"><span data-stu-id="6739c-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="6739c-110">Per analizzare un progetto di modello tabulare tramite la funzionalità Analizza in Excel</span><span class="sxs-lookup"><span data-stu-id="6739c-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="6739c-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]fare clic sul menu **Modello** e quindi scegliere **Analizza in Excel**.</span><span class="sxs-lookup"><span data-stu-id="6739c-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="6739c-112">Nella finestra di dialogo **Scegli credenziale e prospettive** selezionare una delle seguenti opzioni relative alle credenziali per connettersi all'origine dati dell'area di lavoro del modello:</span><span class="sxs-lookup"><span data-stu-id="6739c-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="6739c-113">Per usare l'account utente corrente, selezionare **Utente di Windows corrente**.</span><span class="sxs-lookup"><span data-stu-id="6739c-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="6739c-114">Per usare un account utente diverso, selezionare **Altro utente di Windows**.</span><span class="sxs-lookup"><span data-stu-id="6739c-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="6739c-115">In genere, questo account utente sarà membro di un ruolo.</span><span class="sxs-lookup"><span data-stu-id="6739c-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="6739c-116">Non è necessaria alcuna password.</span><span class="sxs-lookup"><span data-stu-id="6739c-116">No password is required.</span></span> <span data-ttu-id="6739c-117">L'account può essere utilizzato solo nel contesto di una connessione di Excel al database dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6739c-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="6739c-118">Per usare un ruolo di sicurezza, fare clic su **Ruolo**e quindi, nella casella di riepilogo, selezionare uno o più ruoli.</span><span class="sxs-lookup"><span data-stu-id="6739c-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="6739c-119">I ruoli di sicurezza devono essere definiti utilizzando Gestione ruoli.</span><span class="sxs-lookup"><span data-stu-id="6739c-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="6739c-120">Per altre informazioni, vedere [Creare e gestire ruoli &#40;SSAS tabulare&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="6739c-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="6739c-121">Per usare una prospettiva, nella casella di riepilogo **Prospettiva** selezionare una prospettiva.</span><span class="sxs-lookup"><span data-stu-id="6739c-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="6739c-122">Le prospettive (diverse dall'impostazione predefinita) devono essere definite tramite la finestra di dialogo Prospettive.</span><span class="sxs-lookup"><span data-stu-id="6739c-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="6739c-123">Per altre informazioni, vedere [creare e gestire prospettive &#40;SSAS tabulare&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="6739c-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6739c-124">L'elenco di campi della tabella pivot in Excel non viene aggiornato automaticamente mentre si apportano modifiche al progetto di modello in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="6739c-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="6739c-125">Per aggiornare l'elenco di campi della tabella pivot, fare clic su **Aggiorna** nella barra multifunzione **Opzioni**di Excel.</span><span class="sxs-lookup"><span data-stu-id="6739c-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6739c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6739c-126">See Also</span></span>  
 [<span data-ttu-id="6739c-127">Analizzare in Excel &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="6739c-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
