---
title: Modificare le proprietà delle tabelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626224"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="f5c64-102">Modificare le proprietà delle tabelle</span><span class="sxs-lookup"><span data-stu-id="f5c64-102">Edit the Table Properties</span></span>
  <span data-ttu-id="f5c64-103">Utilizzare questa finestra di dialogo per modificare colonne specifiche della tabella selezionata in cui vengono acquisite le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f5c64-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="f5c64-104">È anche possibile modificare le informazioni **Security Role** e **Capture Instance** .</span><span class="sxs-lookup"><span data-stu-id="f5c64-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="f5c64-105">Per modificare le colonne da includere nell'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="f5c64-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="f5c64-106">Eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5c64-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="f5c64-107">Selezionare la casella di controllo accanto a eventuali colonne aggiuntive che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="f5c64-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="f5c64-108">Deselezionare la casella di controllo accanto alle colonne che non si desidera più includere.</span><span class="sxs-lookup"><span data-stu-id="f5c64-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="f5c64-109">Per modificare il ruolo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f5c64-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="f5c64-110">Digitare un nuovo nome oppure modificare il nome esistente del ruolo di sicurezza nel campo **Security Role** .</span><span class="sxs-lookup"><span data-stu-id="f5c64-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="f5c64-111">Per creare una nuova istanza di acquisizione</span><span class="sxs-lookup"><span data-stu-id="f5c64-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="f5c64-112">Nel campo **Name** della sezione **Security Role** immettere un nome per l'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="f5c64-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="f5c64-113">Per impostazione predefinita, il nome immesso nel campo è il nome dell'istanza di acquisizione corrente con **_NEW** aggiunto alla fine del nome, ad esempio **old_instance_NEW**.</span><span class="sxs-lookup"><span data-stu-id="f5c64-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="f5c64-114">Salvare l'istanza di acquisizione come:</span><span class="sxs-lookup"><span data-stu-id="f5c64-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="f5c64-115">**New Capture Instance**: viene salvata una nuova istanza di acquisizione e l'istanza di acquisizione precedente non viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="f5c64-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="f5c64-116">**Nota**: non possono esistere più di due istanze di acquisizione per tabella.</span><span class="sxs-lookup"><span data-stu-id="f5c64-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="f5c64-117">Se sono già presenti due istanze di acquisizione, l'opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f5c64-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="f5c64-118">**Replace Existing**: l'istanza di acquisizione corrente viene eliminata e sostituita dall'istanza di acquisizione creata.</span><span class="sxs-lookup"><span data-stu-id="f5c64-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="f5c64-119">Se per la tabella sono state definite due istanze di acquisizione, è necessario selezionarne una da sostituire.</span><span class="sxs-lookup"><span data-stu-id="f5c64-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="f5c64-120">**Nota**: è possibile rimuovere un'istanza di acquisizione dall'elenco di tabelle nella scheda **Table** .</span><span class="sxs-lookup"><span data-stu-id="f5c64-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="f5c64-121">Dopo avere immesso le informazioni in questa finestra di dialogo, scegliere **OK** per accettare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f5c64-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c64-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5c64-122">See Also</span></span>  
 <span data-ttu-id="f5c64-123">[Procedura di modifica delle proprietà dell'istanza di CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f5c64-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="f5c64-124">Apportare modifiche alle tabelle selezionate per l'acquisizione di modifiche</span><span class="sxs-lookup"><span data-stu-id="f5c64-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
