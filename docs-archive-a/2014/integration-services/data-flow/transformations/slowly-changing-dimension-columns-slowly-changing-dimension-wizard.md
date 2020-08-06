---
title: Colonne dimensioni a modifica lenta (Configurazione guidata dimensioni a modifica lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712188"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="e0670-102">Colonne dimensioni a modifica lenta (Configurazione guidata dimensioni a modifica lenta)</span><span class="sxs-lookup"><span data-stu-id="e0670-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="e0670-103">Utilizzare la finestra di dialogo **Colonne dimensioni a modifica lenta** per selezionare un tipo di modifica per ogni colonna delle dimensioni a modifica lenta.</span><span class="sxs-lookup"><span data-stu-id="e0670-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="e0670-104">Per ulteriori informazioni su questa procedura guidata, vedere [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e0670-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0670-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e0670-105">Options</span></span>  
 <span data-ttu-id="e0670-106">**Colonne dimensione**</span><span class="sxs-lookup"><span data-stu-id="e0670-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="e0670-107">Consente di selezionare una colonna nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e0670-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="e0670-108">**Tipo di modifica**</span><span class="sxs-lookup"><span data-stu-id="e0670-108">**Change Type**</span></span>  
 <span data-ttu-id="e0670-109">Consente di selezionare un **Attributo fisso**o uno dei due tipi di attributi modificabili.</span><span class="sxs-lookup"><span data-stu-id="e0670-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="e0670-110">Utilizzare **Attributo fisso** quando il valore di una colonna non deve cambiare. Le modifiche verranno trattate come errori in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0670-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="e0670-111">Utilizzare **Attributo modificabile** per sovrascrivere i valori esistenti con i valori modificati.</span><span class="sxs-lookup"><span data-stu-id="e0670-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="e0670-112">Utilizzare **Attributo cronologico** per salvare i valori modificati in nuovi record, contrassegnando contemporaneamente i record precedenti come obsoleti.</span><span class="sxs-lookup"><span data-stu-id="e0670-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="e0670-113">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="e0670-113">**Remove**</span></span>  
 <span data-ttu-id="e0670-114">Consente di selezionare una colonna delle dimensioni e di rimuoverla dall'elenco di colonne mappate facendo clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="e0670-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0670-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0670-115">See Also</span></span>  
 [<span data-ttu-id="e0670-116">Configurare gli output tramite Configurazione guidata dimensioni a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="e0670-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
