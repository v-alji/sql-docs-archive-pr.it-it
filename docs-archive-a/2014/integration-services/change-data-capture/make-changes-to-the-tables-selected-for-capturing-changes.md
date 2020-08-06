---
title: Apportare modifiche alle tabelle selezionate per l'acquisizione di modifiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626219"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="11102-102">Apportare modifiche alle tabelle selezionate per l'acquisizione di modifiche</span><span class="sxs-lookup"><span data-stu-id="11102-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="11102-103">In questa finestra di dialogo è possibile selezionare colonne specifiche della tabella selezionata da cui acquisire le modifiche.</span><span class="sxs-lookup"><span data-stu-id="11102-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="11102-104">È anche possibile modificare le informazioni **Security Role** e **Capture Instance** .</span><span class="sxs-lookup"><span data-stu-id="11102-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="11102-105">È possibile apportare le modifiche seguenti alle tabelle selezionate per l'acquisizione delle modifiche in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="11102-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="11102-106">**Cambiare le colonne incluse nell'istanza di CDC:**</span><span class="sxs-lookup"><span data-stu-id="11102-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="11102-107">Eseguire una o entrambe le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="11102-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="11102-108">Selezionare la casella di controllo accanto a eventuali colonne aggiuntive che si desidera includere.</span><span class="sxs-lookup"><span data-stu-id="11102-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="11102-109">Deselezionare la casella di controllo accanto alle colonne che non si desidera più includere.</span><span class="sxs-lookup"><span data-stu-id="11102-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="11102-110">**Modificare il tipo di dati per una colonna specifica**:</span><span class="sxs-lookup"><span data-stu-id="11102-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="11102-111">È possibile selezionare un tipo di dati diverso per una colonna specifica.</span><span class="sxs-lookup"><span data-stu-id="11102-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="11102-112">È possibile solo modificare il tipo di dati su un tipo di dati compatibile con il tipo di dati originale.</span><span class="sxs-lookup"><span data-stu-id="11102-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="11102-113">Per modificare il tipo di dati, fare clic nella colonna **Tipo di dati** e selezionare un tipo di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="11102-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="11102-114">Sono disponibili solo i tipi di dati compatibili con il tipo di dati originale.</span><span class="sxs-lookup"><span data-stu-id="11102-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11102-115">Se non è possibile selezionare tipi di dati aggiuntivi, l'elenco a discesa non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="11102-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="11102-116">**Modificare il ruolo di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="11102-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="11102-117">Digitare un nuovo nome oppure modificare il nome esistente del ruolo di sicurezza nel campo **Ruolo di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="11102-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="11102-118">**Modificare o aggiungere un'istanza di acquisizione**</span><span class="sxs-lookup"><span data-stu-id="11102-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="11102-119">Nel campo **Istanza di acquisizione** immettere un nome per l'istanza di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="11102-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11102-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11102-120">See Also</span></span>  
 <span data-ttu-id="11102-121">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="11102-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="11102-122">Selezionare tabelle e colonne Oracle</span><span class="sxs-lookup"><span data-stu-id="11102-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
