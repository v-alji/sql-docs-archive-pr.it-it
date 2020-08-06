---
title: Finestra di dialogo abilitazione-disabilitazione writeback (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638138"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="cd72b-102">Finestra di dialogo Abilita-Disabilita writeback (Analysis Services-Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="cd72b-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="cd72b-103">La finestra di dialogo **Enable/Disable Writeback** (Abilita/Disabilita writeback) attiva o disabilita il writeback per un gruppo di misure in un cubo.</span><span class="sxs-lookup"><span data-stu-id="cd72b-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="cd72b-104">L'attivazione del writeback su un gruppo di misure definisce una partizione writeback e crea una tabella writeback per tale gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="cd72b-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="cd72b-105">La disabilitazione del writeback su un gruppo di misure elimina la partizione writeback ma non la tabella writeback, per evitare una perdita imprevista di dati.</span><span class="sxs-lookup"><span data-stu-id="cd72b-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="cd72b-106">La finestra di dialogo **Enable/Disable Writeback** (Abilita/Disabilita writeback) può essere visualizzata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd72b-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="cd72b-107">Facendo clic su **Impostazioni writeback** nel riquadro **Gruppi di misure** della scheda **Partizioni** in Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="cd72b-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="cd72b-108">Facendo clic con il pulsante destro del mouse su una partizione nella griglia **Partizioni** nel riquadro **Gruppi di misure** della scheda **Partizioni** in Progettazione cubi e scegliendo **Impostazioni writeback** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="cd72b-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd72b-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cd72b-109">Options</span></span>  
 <span data-ttu-id="cd72b-110">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="cd72b-110">**Table name**</span></span>  
 <span data-ttu-id="cd72b-111">Consente di digitare il nome della tabella writeback da creare per la partizione selezionata.</span><span class="sxs-lookup"><span data-stu-id="cd72b-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="cd72b-112">La tabella di writeback archivia le modifiche apportate al gruppo di misure da un’applicazione client.</span><span class="sxs-lookup"><span data-stu-id="cd72b-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd72b-113">Se il writeback non è abilitato questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd72b-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="cd72b-114">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="cd72b-114">**Data source**</span></span>  
 <span data-ttu-id="cd72b-115">Consente di selezionare l'origine dei dati che deve contenere la tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="cd72b-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd72b-116">Se il writeback non è abilitato questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd72b-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="cd72b-117">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="cd72b-117">**New**</span></span>  
 <span data-ttu-id="cd72b-118">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Gestione connessione** e definire una nuova origine dei dati che deve contenere la tabella writeback.</span><span class="sxs-lookup"><span data-stu-id="cd72b-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd72b-119">Se il writeback non è abilitato questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd72b-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
