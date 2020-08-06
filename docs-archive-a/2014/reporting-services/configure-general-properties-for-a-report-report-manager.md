---
title: Configurare le proprietà generali per un report (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723599"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="159e2-102">Configurare le proprietà generali per un report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="159e2-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="159e2-103">Per configurare le proprietà generali del report</span><span class="sxs-lookup"><span data-stu-id="159e2-103">To configure general report properties</span></span>

1.  <span data-ttu-id="159e2-104">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="159e2-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="159e2-105">In Gestione report passare alla pagina **contenuto** .</span><span class="sxs-lookup"><span data-stu-id="159e2-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="159e2-106">quindi passare al report per il quale si desidera configurare le proprietà generali e aprirlo.</span><span class="sxs-lookup"><span data-stu-id="159e2-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="159e2-107">Fare clic sulla scheda **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="159e2-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="159e2-108">In alternativa, se la pagina **contenuto** è in visualizzazione dettagli, fare clic sull'icona della pagina delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="159e2-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="159e2-109">![Icona della pagina delle proprietà](media/prop.gif "Icona della pagina delle proprietà")</span><span class="sxs-lookup"><span data-stu-id="159e2-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="159e2-110">Viene visualizzata la pagina delle proprietà **generale** ed è possibile configurare le proprietà come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="159e2-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="159e2-111">Nella sezione **Proprietà** è possibile modificare il nome e la descrizione del report.</span><span class="sxs-lookup"><span data-stu-id="159e2-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="159e2-112">È possibile selezionare la casella di controllo **Nascondi in visualizzazione elenco** per nascondere l'elemento quando la pagina viene aperta nel layout di pagina predefinito (visualizzazione elenco), che consente di disporre gli elementi in orizzontale e in basso nella pagina.</span><span class="sxs-lookup"><span data-stu-id="159e2-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="159e2-113">Nella sezione **definizione del report** fare clic su **modifica** per estrarre una copia della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="159e2-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="159e2-114">Le modifiche apportate localmente alla definizione del report non vengono salvate nel server di report.</span><span class="sxs-lookup"><span data-stu-id="159e2-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="159e2-115">In alternativa, per aggiornare la definizione del report da un file con estensione rdl, fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="159e2-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="159e2-116">Se si aggiorna la definizione di un report è necessario reimpostare le impostazioni dell'origine dei dati dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="159e2-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="159e2-117">Utilizzare i pulsanti **Elimina** o **Sposta** per eliminare o spostare il report.</span><span class="sxs-lookup"><span data-stu-id="159e2-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="159e2-118">È inoltre possibile creare un report collegato.</span><span class="sxs-lookup"><span data-stu-id="159e2-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="159e2-119">Al termine della configurazione delle proprietà generali per il report, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="159e2-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="159e2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="159e2-120">See Also</span></span>
 <span data-ttu-id="159e2-121">[Spostare o eliminare un elemento &#40;Gestione report](report-server/move-or-delete-an-item-report-manager.md) [pagina contenuto&#41;&#40;](../../2014/reporting-services/contents-page-report-manager.md) Gestione report&#41;la [ricerca, la visualizzazione e la gestione dei report &#40;Generatore report e SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [pagina delle proprietà generale, report &#40;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) Gestione report&#41;</span><span class="sxs-lookup"><span data-stu-id="159e2-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


