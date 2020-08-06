---
title: Indirizzare il flusso CDC in base al tipo di modifica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626197"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="796d6-102">Indirizzare il flusso CDC in base al tipo di modifica</span><span class="sxs-lookup"><span data-stu-id="796d6-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="796d6-103">Per aggiungere e configurare una trasformazione CDC Splitter, il pacchetto deve contenere almeno un'attività Flusso di dati e un'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="796d6-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="796d6-104">Per l'origine CDC aggiunta al pacchetto deve essere selezionata una modalità di elaborazione CDC Net.</span><span class="sxs-lookup"><span data-stu-id="796d6-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="796d6-105">Per altre informazioni sulla selezione delle modalità di elaborazione, vedere [Editor origine CDC &#40;pagina Gestione connessione&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="796d6-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="796d6-106">Per indirizzare il flusso CDC in base al tipo di modifica</span><span class="sxs-lookup"><span data-stu-id="796d6-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="796d6-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]aprire il progetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="796d6-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="796d6-108">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="796d6-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="796d6-109">Fare clic sulla scheda **Flusso di dati** , quindi trascinare la barra di divisione CDC dalla **Casella degli strumenti**all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="796d6-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="796d6-110">Connettere l'origine CDC inclusa nel pacchetto alla barra di divisione CDC.</span><span class="sxs-lookup"><span data-stu-id="796d6-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="796d6-111">Connettere la barra di divisione CDC a una o più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="796d6-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="796d6-112">È possibile eseguire la connessione a un massimo di tre output diversi.</span><span class="sxs-lookup"><span data-stu-id="796d6-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="796d6-113">Selezionare uno degli output seguenti:</span><span class="sxs-lookup"><span data-stu-id="796d6-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="796d6-114">Output di eliminazione: output in cui vengono indirizzate le righe delle modifiche DELETE.</span><span class="sxs-lookup"><span data-stu-id="796d6-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="796d6-115">Output di inserimento: output in cui vengono indirizzate le righe delle modifiche INSERT.</span><span class="sxs-lookup"><span data-stu-id="796d6-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="796d6-116">Output di aggiornamento: output in cui vengono indirizzate le righe delle modifiche before/after UPDATE e le righe delle modifiche MERGE.</span><span class="sxs-lookup"><span data-stu-id="796d6-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="796d6-117">È eventualmente possibile configurare le proprietà avanzate utilizzando la finestra di dialogo **Editor avanzato** .</span><span class="sxs-lookup"><span data-stu-id="796d6-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="796d6-118">La finestra di dialogo **Editor avanzato** contiene le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="796d6-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="796d6-119">Per aprire la finestra di dialogo **Editor avanzato** :</span><span class="sxs-lookup"><span data-stu-id="796d6-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="796d6-120">Nella schermata **Flusso di dati** del progetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] fare clic con il pulsante destro del mouse sulla barra di divisione CDC e scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="796d6-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="796d6-121">Per ulteriori informazioni sull'utilizzo della barra di divisione CDC, vedere Componenti CDC per Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="796d6-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796d6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="796d6-122">See Also</span></span>  
 [<span data-ttu-id="796d6-123">CDC Splitter</span><span class="sxs-lookup"><span data-stu-id="796d6-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
