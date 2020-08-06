---
title: Pagina nuovo modello (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635448"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="4d083-102">Pagina Nuovo modello (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="4d083-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="4d083-103">Questa pagina consente di generare un modello di report predefinito da un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d083-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="4d083-104">È possibile generare modelli di report solo da origini dati multidimensionali di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , origini dati relazionali di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e origini dati relazionali di Oracle.</span><span class="sxs-lookup"><span data-stu-id="4d083-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="4d083-105">I modelli generati in Gestione report sono basati sullo schema dell'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d083-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="4d083-106">Per tutte le tabelle e le colonne nell'origine dati vengono creati entità, cartelle e campi.</span><span class="sxs-lookup"><span data-stu-id="4d083-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="4d083-107">Non è possibile escludere elementi, né impostare opzioni che determinano come viene generato il modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="4d083-108">Se si desidera personalizzare o modificare un modello, è invece necessario utilizzare Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="4d083-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="4d083-109">Spostamento</span><span class="sxs-lookup"><span data-stu-id="4d083-109">Navigation</span></span>  
 <span data-ttu-id="4d083-110">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4d083-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="4d083-111">Per aprire la pagina Nuovo modello</span><span class="sxs-lookup"><span data-stu-id="4d083-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="4d083-112">Aprire Gestione report e individuare l'origine dati condivisa per la quale si desidera generare un modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="4d083-113">Passare con il puntatore del mouse sull'origine dati, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="4d083-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="4d083-114">Nel menu a discesa, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d083-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="4d083-115">Fare clic su **Genera modello di report** per aprire la pagina Nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="4d083-116">Fare clic su **Gestisci** per aprire la pagina delle proprietà Generale per il report.</span><span class="sxs-lookup"><span data-stu-id="4d083-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="4d083-117">Successivamente, fare clic su **Genera modello** per aprire la pagina Nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d083-118">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4d083-118">Options</span></span>  
 <span data-ttu-id="4d083-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="4d083-119">**Name**</span></span>  
 <span data-ttu-id="4d083-120">Consente di specificare il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-120">Specifies the name of the model.</span></span> <span data-ttu-id="4d083-121">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="4d083-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="4d083-122">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="4d083-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="4d083-123">Il nome non può contenere i caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d083-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="4d083-124">; ?</span><span class="sxs-lookup"><span data-stu-id="4d083-124">; ?</span></span> <span data-ttu-id="4d083-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="4d083-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="4d083-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4d083-126">**Description**</span></span>  
 <span data-ttu-id="4d083-127">Indica una descrizione del modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-127">Shows a description of the model.</span></span> <span data-ttu-id="4d083-128">Gli utenti che visualizzano questo elemento tramite Gestione report possono vedere questa descrizione durante l'esplorazione della gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="4d083-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="4d083-129">**Cambia percorso**</span><span class="sxs-lookup"><span data-stu-id="4d083-129">**Change Location**</span></span>  
 <span data-ttu-id="4d083-130">Consente di visualizzare il percorso della cartella per il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="4d083-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="4d083-131">È possibile fare clic sul pulsante **Cambia percorso** per selezionare un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="4d083-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
