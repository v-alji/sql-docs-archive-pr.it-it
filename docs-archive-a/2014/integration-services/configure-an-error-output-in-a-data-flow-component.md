---
title: Configurare un output degli errori in un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724876"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="ee595-102">Configurazione di un output degli errori in un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ee595-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="ee595-103">Molti componenti del flusso di dati supportano l'output degli errori. A seconda del componente, in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] sono disponibili strumenti diversi per la configurazione di un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="ee595-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="ee595-104">Oltre a configurare un output degli errori, è possibile configurare le relative colonne,</span><span class="sxs-lookup"><span data-stu-id="ee595-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="ee595-105">tra cui le colonne **ErrorCode** e **ErrorColumn** aggiunte dal componente.</span><span class="sxs-lookup"><span data-stu-id="ee595-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="ee595-106">Configurazione di un output degli errori</span><span class="sxs-lookup"><span data-stu-id="ee595-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="ee595-107">Per configurare un output degli errori sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="ee595-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="ee595-108">Usare la finestra di dialogo **Configura output errori** .</span><span class="sxs-lookup"><span data-stu-id="ee595-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="ee595-109">Questa finestra di dialogo consente di configurare un output degli errori in qualsiasi componente del flusso di dati che supporti l'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="ee595-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="ee595-110">Utilizzare la finestra di dialogo dell'editor per il componente.</span><span class="sxs-lookup"><span data-stu-id="ee595-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="ee595-111">Alcuni componenti consentono di configurare gli output degli errori direttamente dalla finestra di dialogo dell'editor.</span><span class="sxs-lookup"><span data-stu-id="ee595-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="ee595-112">Non è tuttavia possibile configurare output degli errori dalla finestra di dialogo dell'editor per l'origine ADO NET, la trasformazione Importa colonna, la trasformazione Comando OLE DB o la destinazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="ee595-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="ee595-113">Nelle procedure seguenti viene descritto come utilizzare queste finestre di dialogo per configurare gli output degli errori.</span><span class="sxs-lookup"><span data-stu-id="ee595-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="ee595-114">Per configurare un output degli errori tramite la finestra di dialogo Configura output errori</span><span class="sxs-lookup"><span data-stu-id="ee595-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="ee595-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee595-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ee595-116">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="ee595-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ee595-117">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="ee595-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ee595-118">Trascinare l'output degli errori, rappresentato da una freccia rossa, dal componente corrispondente all'origine degli errori a un altro componente del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="ee595-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="ee595-119">Nella finestra di dialogo **Configura output errori** selezionare un'azione nelle colonne **Errore** e **Troncamento** per ogni colonna dell'input del componente.</span><span class="sxs-lookup"><span data-stu-id="ee595-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="ee595-120">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="ee595-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="ee595-121">Per aggiungere un output degli errori tramite la finestra di dialogo dell'editor per il componente</span><span class="sxs-lookup"><span data-stu-id="ee595-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="ee595-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee595-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ee595-123">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="ee595-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ee595-124">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="ee595-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ee595-125">Fare doppio clic sui componenti del flusso di dati in cui si desidera configurare un output degli errori e, a seconda del componente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee595-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="ee595-126">Fare clic su **Configura output errori**.</span><span class="sxs-lookup"><span data-stu-id="ee595-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="ee595-127">Fare clic su **Output degli errori**.</span><span class="sxs-lookup"><span data-stu-id="ee595-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="ee595-128">Impostare l'opzione **Errore** per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="ee595-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="ee595-129">Impostare l'opzione **Troncamento** per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="ee595-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="ee595-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee595-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="ee595-131">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="ee595-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="ee595-132">Configurazione delle colonne dell'output degli errori</span><span class="sxs-lookup"><span data-stu-id="ee595-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="ee595-133">Per configurare le colonne dell'output degli errori, è necessario usare la scheda **Proprietà input e output** della finestra di dialogo **Editor avanzato** .</span><span class="sxs-lookup"><span data-stu-id="ee595-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="ee595-134">Per configurare le colonne dell'output degli errori</span><span class="sxs-lookup"><span data-stu-id="ee595-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="ee595-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee595-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ee595-136">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="ee595-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ee595-137">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="ee595-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ee595-138">Fare clic con il pulsante destro del mouse sul componente di cui si desidera configurare le colonne dell'output degli errori, quindi scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="ee595-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="ee595-139">Fare clic sulla scheda **Proprietà input e output**. Espandere **Output errori \<component name>** , quindi **Colonne di output**.</span><span class="sxs-lookup"><span data-stu-id="ee595-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="ee595-140">Fare clic su una colonna e aggiornarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ee595-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee595-141">L'elenco di colonne include le colonne dell'input del componente, le colonne **ErrorCode** e **ErrorColumn** aggiunte dall'output degli errori precedente e le colonne **ErrorCode** e **ErrorColumn** aggiunte dal componente corrente.</span><span class="sxs-lookup"><span data-stu-id="ee595-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="ee595-142">Scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee595-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="ee595-143">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="ee595-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee595-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee595-144">See Also</span></span>  
 [<span data-ttu-id="ee595-145">Gestione degli errori nei dati</span><span class="sxs-lookup"><span data-stu-id="ee595-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
