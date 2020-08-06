---
title: Pubblicare dati da Excel a MDS (Componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 89fce454-a816-4b33-a26a-d1b9741d269b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 597a954760816d8938628974998fe8f6daad1af5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636245"
---
# <a name="publish-data-from-excel-to-mds-mds-add-in-for-excel"></a><span data-ttu-id="b9a81-102">Pubblicare dati da Excel in MDS (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="b9a81-102">Publish Data from Excel to MDS (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="b9a81-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]è possibile pubblicare i dati nel repository MDS se dopo aver usato Excel si vuole salvare le modifiche perché altri utenti possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="b9a81-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], publish data to the MDS repository when you are finished working in Excel and want to save your changes so other users have access to them.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="b9a81-104">Quando si pubblicano le modifiche, vengono eliminati i commenti sulle celle gestite da MDS.</span><span class="sxs-lookup"><span data-stu-id="b9a81-104">When you publish changes, comments on MDS-managed cells are deleted.</span></span>  
> -   <span data-ttu-id="b9a81-105">Una formula non è supportata in una cella gestita da MDS.</span><span class="sxs-lookup"><span data-stu-id="b9a81-105">A formula is not supported in an MDS-managed cell.</span></span> <span data-ttu-id="b9a81-106">Una formula in una cella gestita da MDS viene gestita come valore di testo.</span><span class="sxs-lookup"><span data-stu-id="b9a81-106">A formula in an MDS-managed cell is handled as a text value.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b9a81-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b9a81-107">Prerequisites</span></span>  
 <span data-ttu-id="b9a81-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="b9a81-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b9a81-109">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="b9a81-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="b9a81-110">Il foglio di lavoro attivo deve contenere dati gestiti da MDS ed è necessario avere apportato modifiche o aggiunte ai dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="b9a81-110">The active worksheet must contain MDS-managed data and you must have made changes or additions to the MDS-managed data.</span></span>  
  
-   <span data-ttu-id="b9a81-111">Se si aggiungono membri, non è necessario specificare un valore **Code** se i codici per l'entità vengono generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b9a81-111">If you are adding members, you do not have to specify a **Code** value if codes for the entity are being automatically generated.</span></span> <span data-ttu-id="b9a81-112">Per ulteriori informazioni, vedere [creazione automatica di codice &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b9a81-112">For more information, see [Automatic Code Creation &#40;Master Data Services&#41;](../automatic-code-creation-master-data-services.md).</span></span>  
  
### <a name="to-publish-data-to-the-mds-repository"></a><span data-ttu-id="b9a81-113">Per pubblicare dati al repository MDS</span><span class="sxs-lookup"><span data-stu-id="b9a81-113">To publish data to the MDS repository</span></span>  
  
1.  <span data-ttu-id="b9a81-114">Nel gruppo **Pubblica e convalida** fare clic su **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="b9a81-114">In the **Publish and Validate** group, click **Publish**.</span></span>  
  
2.  <span data-ttu-id="b9a81-115">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b9a81-115">Optional.</span></span> <span data-ttu-id="b9a81-116">Se viene visualizzata la finestra di dialogo **Pubblicazione e annotazione** , scegliere di condividere la stessa annotazione (commento) per tutti gli aggiornamenti o annotare individualmente ogni modifica.</span><span class="sxs-lookup"><span data-stu-id="b9a81-116">If the **Publish and Annotate** dialog box is displayed, choose to share the same annotation (comment) for all updates, or to annotate each change individually.</span></span>  
  
3.  <span data-ttu-id="b9a81-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b9a81-117">Optional.</span></span> <span data-ttu-id="b9a81-118">Selezionare la casella di controllo **Non visualizzare più questa finestra di dialogo** .</span><span class="sxs-lookup"><span data-stu-id="b9a81-118">Select the **Do not show this dialog box again** check box.</span></span> <span data-ttu-id="b9a81-119">È possibile mostrare sempre la finestra di dialogo in futuro scegliendo **Impostazioni** e selezionando la finestra di dialogo **Mostra la finestra di dialogo Pubblicazione e annotazione durante la pubblicazione** .</span><span class="sxs-lookup"><span data-stu-id="b9a81-119">You can always show the dialog box in the future by choosing **Settings** and selecting the **Show Publish and Annotate dialog box when publishing** check box.</span></span>  
  
4.  <span data-ttu-id="b9a81-120">Fare clic su **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="b9a81-120">Click **Publish**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9a81-121">Se si aggiungono i nuovi membri (righe) al foglio di lavoro e non è possibile pubblicarli correttamente nel repository MDS, è possibile che non si disponga dell'autorizzazione **Update** per tutti gli attributi nel foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b9a81-121">If you are adding new members (rows) to your worksheet and you cannot successfully publish them to the MDS repository, you may not have **Update** permission to all of the attributes in the worksheet.</span></span> <span data-ttu-id="b9a81-122">Nella scheda **Verifica** nel gruppo **Modifiche** fare clic su **Rimuovi protezione foglio** e tentare di nuovo la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b9a81-122">On the **Review** tab, in the **Changes** group, click **Unprotect Sheet** and try to publish again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b9a81-123">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b9a81-123">Next Steps</span></span>  
 [<span data-ttu-id="b9a81-124">Applicare le regole di business &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="b9a81-124">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="b9a81-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9a81-125">See Also</span></span>  
 <span data-ttu-id="b9a81-126">[Pubblicazione dei dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b9a81-126">[Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="b9a81-127">Convalida dei dati &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="b9a81-127">Validating Data &#40;MDS Add-in for Excel&#41;</span></span>](validating-data-mds-add-in-for-excel.md)  
  
  
