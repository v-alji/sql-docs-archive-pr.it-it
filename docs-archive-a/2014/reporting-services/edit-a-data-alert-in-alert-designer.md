---
title: Modificare un avviso dati nella finestra di progettazione di avvisi| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719643"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="39bd7-102">Modificare un avviso dati nella finestra di progettazione di avvisi</span><span class="sxs-lookup"><span data-stu-id="39bd7-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="39bd7-103">È possibile aprire una definizione di avviso dati da modificare tramite Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="39bd7-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="39bd7-104">La definizione di avviso può essere modificata solo dall'utente che l'ha creata.</span><span class="sxs-lookup"><span data-stu-id="39bd7-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="39bd7-105">Per altre informazioni sull'apertura di gestione avvisi dati, vedere [Gestire gli avvisi dati in Gestione avvisi dati](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="39bd7-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="39bd7-106">Nella figura seguente è illustrato il menu di scelta rapida per un avviso dati in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="39bd7-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="39bd7-107">![Aprire la finestra di progettazione di avvisi dati facendo clic su Modifica](media/rs-alertmanageriwopendesigner.gif "Aprire la finestra di progettazione di avvisi dati facendo clic su Modifica")</span><span class="sxs-lookup"><span data-stu-id="39bd7-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="39bd7-108">Nella procedura seguente sono inclusi i passaggi per aprire la definizione di avviso per la modifica nella finestra di progettazione Avviso dati di Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="39bd7-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="39bd7-109">Per modificare una definizione di avviso in Gestione avvisi dati</span><span class="sxs-lookup"><span data-stu-id="39bd7-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="39bd7-110">In Gestione avvisi dati fare clic con il pulsante destro del mouse sulla definizione di avviso dati che si desidera modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="39bd7-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="39bd7-111">La definizione di avviso viene aperta in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="39bd7-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="39bd7-112">Aggiornare le regole e le impostazioni di pianificazione e di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="39bd7-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="39bd7-113">Per altre informazioni, vedere [Finestra di progettazione Avviso dati](../../2014/reporting-services/data-alert-designer.md) e [Creare un avviso dati nella finestra di progettazione Avviso dati](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="39bd7-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="39bd7-114">Non è possibile scegliere un feed di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="39bd7-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="39bd7-115">Per utilizzare un feed di dati diverso, è necessario creare una nuova definizione di avviso dati.</span><span class="sxs-lookup"><span data-stu-id="39bd7-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="39bd7-116">Fare clic su **Save**.</span><span class="sxs-lookup"><span data-stu-id="39bd7-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="39bd7-117">Se il report è cambiato e i feed di dati generati dal report sono cambiati, la definizione di avviso potrebbe non essere più valida.</span><span class="sxs-lookup"><span data-stu-id="39bd7-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="39bd7-118">Questa condizione si verifica quando una colonna, a cui fa riferimento la definizione di avviso nelle regole, viene eliminata dal report, quando il tipo di dati contenuto in tale colonna viene modificato oppure quando il report viene eliminato o spostato.</span><span class="sxs-lookup"><span data-stu-id="39bd7-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="39bd7-119">È possibile aprire una definizione di avviso che non è valida, ma non è possibile salvarla di nuovo fino a quando non diventa valida in base alla versione corrente del feed di dati del report in base a cui è compilata.</span><span class="sxs-lookup"><span data-stu-id="39bd7-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="39bd7-120">Per altre informazioni sulla modalità di generazione di feed di dati dai report, vedere [Generazione di feed di dati dai report &#40;Generatore report e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39bd7-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39bd7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39bd7-121">See Also</span></span>
 <span data-ttu-id="39bd7-122">[Gestione avvisi dati per gli amministratori di](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) avvisi [Reporting Services avvisi dati](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="39bd7-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


