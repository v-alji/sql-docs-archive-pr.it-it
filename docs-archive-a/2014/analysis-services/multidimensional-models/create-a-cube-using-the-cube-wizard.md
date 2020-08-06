---
title: Creazione di un cubo mediante la creazione guidata cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721960"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="57482-102">Creare un cubo mediante la Creazione guidata cubo</span><span class="sxs-lookup"><span data-stu-id="57482-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="57482-103">È possibile creare un nuovo cubo usando la Creazione guidata cubo in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57482-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="57482-104">Per creare un nuovo cubo</span><span class="sxs-lookup"><span data-stu-id="57482-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="57482-105">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **cubi**, quindi scegliere **nuovo cubo**.</span><span class="sxs-lookup"><span data-stu-id="57482-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="57482-106">Nella pagina **Selezione metodo di creazione** della Creazione guidata cubo selezionare **Usa tabelle esistenti**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57482-107">Si potrebbe dovere creare occasionalmente un cubo senza utilizzare le tabelle esistenti.</span><span class="sxs-lookup"><span data-stu-id="57482-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="57482-108">Per creare un cubo vuoto, selezionare **Crea un cubo vuoto**.</span><span class="sxs-lookup"><span data-stu-id="57482-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="57482-109">Per generare tabelle, selezionare **Genera tabelle nell'origine dati**.</span><span class="sxs-lookup"><span data-stu-id="57482-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="57482-110">Nella pagina **Selezione tabelle del gruppo di misure** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="57482-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="57482-111">Nell'elenco **Vista origine dati** selezionare una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="57482-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="57482-112">Nell'elenco **Tabelle del gruppo di misure** selezionare le tabelle che verranno usate per creare gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="57482-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="57482-113">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="57482-114">Nella pagina **Selezione misure** selezionare le misure da includere nel cubo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="57482-115">Facoltativamente è possibile modificare i nomi delle misure e dei gruppi di misure.</span><span class="sxs-lookup"><span data-stu-id="57482-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="57482-116">Nella pagina **Selezione dimensioni esistenti** selezionare le dimensioni esistenti da includere nel cubo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57482-117">La pagina **Selezione dimensioni esistenti** viene visualizzata se per alcuni dei gruppi di misure selezionati esistono già dimensioni.</span><span class="sxs-lookup"><span data-stu-id="57482-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="57482-118">Nella pagina **Selezione nuove dimensioni** selezionare le nuove dimensioni da creare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57482-119">La pagina **Selezione nuove dimensioni** viene visualizzata se una o più delle tabelle sono idonee per le tabelle delle dimensioni e non sono state già usate da dimensioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="57482-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="57482-120">Nella pagina **Selezione chiavi della dimensione mancanti** selezionare una chiave per la dimensione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="57482-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57482-121">La pagina **Selezione chiavi della dimensione mancanti** viene visualizzata se per una o più delle tabelle delle dimensioni specificate non è stata definita alcuna chiave.</span><span class="sxs-lookup"><span data-stu-id="57482-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="57482-122">Nella pagina **Completamento procedura guidata** assegnare un nome al nuovo cubo e quindi esaminare la struttura del cubo.</span><span class="sxs-lookup"><span data-stu-id="57482-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="57482-123">Per apportare modifiche, fare clic su **Indietro**. In caso contrario, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="57482-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57482-124">È possibile utilizzare Progettazione cubi al termine della procedura guidata per la configurazione dei cubi.</span><span class="sxs-lookup"><span data-stu-id="57482-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="57482-125">È inoltre possibile utilizzare Progettazione dimensioni per aggiungere, rimuovere e configurare attributi e gerarchie nelle dimensioni create.</span><span class="sxs-lookup"><span data-stu-id="57482-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
