---
title: Opzioni attributi fissi e modificabili (Configurazione guidata dimensioni a modifica lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.attriboption.f1
ms.assetid: c841345c-7d03-452f-9379-1c8c464f029c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df654cd97b343179828ebd94dea40eacc90e003d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625482"
---
# <a name="fixed-and-changing-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="8403e-102">Opzioni attributi fissi e modificabili (Configurazione guidata dimensioni a modifica lenta)</span><span class="sxs-lookup"><span data-stu-id="8403e-102">Fixed and Changing Attribute Options (Slowly Changing Dimension Wizard</span></span>
  <span data-ttu-id="8403e-103">Utilizzare la finestra di dialogo **Opzioni attributi fissi e modificabili** per specificare le modalità di risposta alle modifiche degli attributi fissi e modificabili.</span><span class="sxs-lookup"><span data-stu-id="8403e-103">Use the **Fixed and Changing Attribute Options** dialog box to specify how to respond to changes in fixed and changing attributes.</span></span>  
  
 <span data-ttu-id="8403e-104">Per ulteriori informazioni su questa procedura guidata, vedere [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8403e-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8403e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8403e-105">Options</span></span>  
 <span data-ttu-id="8403e-106">**Attributi fissi**</span><span class="sxs-lookup"><span data-stu-id="8403e-106">**Fixed attributes**</span></span>  
 <span data-ttu-id="8403e-107">Per gli attributi fissi, consente di indicare se l'attività deve essere interrotta in caso venga rilevata una modifica a un attributo fisso.</span><span class="sxs-lookup"><span data-stu-id="8403e-107">For fixed attributes, indicate whether the task should fail if a change is detected in a fixed attribute.</span></span>  
  
 <span data-ttu-id="8403e-108">**Attributi modificabili**</span><span class="sxs-lookup"><span data-stu-id="8403e-108">**Changing attributes**</span></span>  
 <span data-ttu-id="8403e-109">Per gli attributi modificabili, consente di indicare se l'attività deve modificare i record obsoleti o scaduti oltre ai record correnti, in caso venga rilevata una modifica a un attributo modificabile.</span><span class="sxs-lookup"><span data-stu-id="8403e-109">For changing attributes, indicate whether the task should change outdated or expired records, in addition to current records, when a change is detected in a changing attribute.</span></span> <span data-ttu-id="8403e-110">Per record scaduto si intende un record che è stato sostituito con un record più recente mediante una modifica in un attributo cronologico (una modifica di tipo 2).</span><span class="sxs-lookup"><span data-stu-id="8403e-110">An expired record is a record that has been replaced with a newer record by a change in a historical attribute (a Type 2 change).</span></span> <span data-ttu-id="8403e-111">Se si seleziona questa opzione, è possibile che vengano imposti ulteriori requisiti di elaborazione in un oggetto multidimensionale costruito sul data warehouse relazionale.</span><span class="sxs-lookup"><span data-stu-id="8403e-111">Selecting this option may impose additional processing requirements on a multidimensional object constructed on the relational data warehouse.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8403e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8403e-112">See Also</span></span>  
 [<span data-ttu-id="8403e-113">Configurare gli output tramite Configurazione guidata dimensioni a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="8403e-113">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
