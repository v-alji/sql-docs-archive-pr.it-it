---
title: Membri dimensione derivati (Configurazione guidata dimensioni a modifica lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636309"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="f6193-102">Membri dimensione derivati (Configurazione guidata dimensioni a modifica lenta)</span><span class="sxs-lookup"><span data-stu-id="f6193-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="f6193-103">Utilizzare la finestra di dialogo **Membri dimensione derivati** per specificare le opzioni per l'utilizzo di membri derivati.</span><span class="sxs-lookup"><span data-stu-id="f6193-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="f6193-104">I membri derivati esistono quando una tabella dei fatti fa riferimento a membri della dimensione non ancora caricati.</span><span class="sxs-lookup"><span data-stu-id="f6193-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="f6193-105">Dopo il caricamento dei dati relativi al membro derivato, sarà possibile aggiornare il record esistente anziché crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="f6193-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="f6193-106">Per ulteriori informazioni su questa procedura guidata, vedere [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f6193-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f6193-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f6193-107">Options</span></span>  
 <span data-ttu-id="f6193-108">**Abilita supporto per membri derivati**</span><span class="sxs-lookup"><span data-stu-id="f6193-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="f6193-109">Se si sceglie di abilitare i membri derivati, è necessario selezionare una delle due opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f6193-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="f6193-110">**Tutte le colonne con un tipo di modifica sono Null**</span><span class="sxs-lookup"><span data-stu-id="f6193-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="f6193-111">Consente di specificare se immettere valori Null in tutte le colonne con un tipo di modifica nel nuovo record del membro derivato.</span><span class="sxs-lookup"><span data-stu-id="f6193-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="f6193-112">**Usa una colonna booleana per indicare se il record corrente è un membro derivato**</span><span class="sxs-lookup"><span data-stu-id="f6193-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="f6193-113">Consente di specificare se utilizzare una colonna booleana esistente per indicare se il record corrente è un membro derivato.</span><span class="sxs-lookup"><span data-stu-id="f6193-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="f6193-114">**Indicatore membro derivato**</span><span class="sxs-lookup"><span data-stu-id="f6193-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="f6193-115">Se si è scelto di utilizzare una colonna booleana per indicare membri derivati, come descritto in precedenza, selezionare la colonna nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f6193-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6193-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6193-116">See Also</span></span>  
 [<span data-ttu-id="f6193-117">Configurare gli output tramite Configurazione guidata dimensioni a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="f6193-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
