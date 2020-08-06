---
title: Configurare il set di campi predefiniti per i report Power View (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712472"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="6662f-102">Configurare il set di campi predefiniti per i report Power View (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="6662f-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="6662f-103">Un set di campi predefiniti è un elenco predefinito di colonne e misure che vengono aggiunte automaticamente all'area di disegno di un report [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] quando si seleziona la tabella nell'elenco dei campi del report.</span><span class="sxs-lookup"><span data-stu-id="6662f-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="6662f-104">I creatori del modello tabulare possono creare un set di campi predefinito per eliminare passaggi ridondanti per i creatori di report che utilizzano il modello.</span><span class="sxs-lookup"><span data-stu-id="6662f-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="6662f-105">Ad esempio, se è noto che la maggior parte degli autori del report che utilizza le informazioni di contatto dei clienti desidera vedere sempre il nome di un contatto, il numero telefonico principale, un indirizzo di posta elettronica e il nome dell'azienda, è possibile pre-selezionare tali colonne in modo che vengano sempre aggiunte all'area di disegno del report quando l'autore fa clic sulla tabella Customer Contact.</span><span class="sxs-lookup"><span data-stu-id="6662f-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6662f-106">Un set di campi predefinito si applica solo a un modello tabulare utilizzato come modello di dati in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6662f-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="6662f-107">I set di campi predefiniti non sono supportati nei report pivot di Excel.</span><span class="sxs-lookup"><span data-stu-id="6662f-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="6662f-108">Creazione di un set di campi predefinito</span><span class="sxs-lookup"><span data-stu-id="6662f-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="6662f-109">È possibile determinare quali campi vengono eventualmente inclusi per impostazione predefinita ogni volta che viene selezionata una tabella specifica in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6662f-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="6662f-110">È possibile inoltre determinare l'ordine di visualizzazione dei campi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6662f-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="6662f-111">Per specificare un set di campi predefinito, è necessario impostare le proprietà del report nel progetto del modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="6662f-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="6662f-112">Per aggiungere un set di campi predefinito</span><span class="sxs-lookup"><span data-stu-id="6662f-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="6662f-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic sulla tabella (scheda) per la quale si sta configurando un elenco di campi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6662f-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="6662f-114">Nella finestra **Proprietà** fare clic su **Fare clic per modificare** nella proprietà **Set di campi predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="6662f-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="6662f-115">Nella finestra di dialogo Set di campi predefinito selezionare uno o più campi.</span><span class="sxs-lookup"><span data-stu-id="6662f-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="6662f-116">È possibile scegliere qualsiasi campo nella tabella, incluse le misure.</span><span class="sxs-lookup"><span data-stu-id="6662f-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="6662f-117">Tenere premuto il tasto MAIUSC per selezionare un intervallo o il tasto CTRL per selezionare singoli campi.</span><span class="sxs-lookup"><span data-stu-id="6662f-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="6662f-118">Fare clic su **Aggiungi** per aggiungerli al set di campi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6662f-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="6662f-119">Utilizzare i pulsanti Su e Giù per specificare un ordine nell'elenco di campi.</span><span class="sxs-lookup"><span data-stu-id="6662f-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="6662f-120">I campi verranno aggiunti al report nell'ordine definito per il set di campi.</span><span class="sxs-lookup"><span data-stu-id="6662f-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="6662f-121">Ripetere questi passaggi per le altre tabelle della cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6662f-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6662f-122">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6662f-122">Next Step</span></span>  
 <span data-ttu-id="6662f-123">Dopo aver creato un set di campi predefinito, è possibile influire ulteriormente sulla progettazione dei report specificando etichette e immagini predefinite, un comportamento del gruppo predefinito o indicando se le righe contenenti lo stesso valore vengono raggruppate in una riga o elencate individualmente.</span><span class="sxs-lookup"><span data-stu-id="6662f-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="6662f-124">Per altre informazioni, vedere [Configurare le proprietà Comportamento tabella per i report Power View &#40;SSAS tabulare&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="6662f-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
