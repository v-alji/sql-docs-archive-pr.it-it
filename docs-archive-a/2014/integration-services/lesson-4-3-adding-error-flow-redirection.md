---
title: 'Passaggio 3: Aggiunta del reindirizzamento del flusso degli errori | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627882"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="59d69-102">Passaggio 3: Aggiunta del reindirizzamento del flusso degli errori</span><span class="sxs-lookup"><span data-stu-id="59d69-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="59d69-103">Come dimostrato nell'attività precedente, la trasformazione Lookup Currency Key non crea una corrispondenza quando tenta di elaborare il file flat di esempio danneggiato che ha generato un errore.</span><span class="sxs-lookup"><span data-stu-id="59d69-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="59d69-104">Dato che la trasformazione utilizza le impostazioni predefinite per l'output degli errori, qualsiasi errore determina l'esito negativo della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="59d69-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="59d69-105">Quando la trasformazione viene interrotta, si interrompe anche il resto del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="59d69-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="59d69-106">Anziché consentire la mancata riuscita della trasformazione, è possibile configurare il componente in modo da reindirizzare la riga con esito negativo a un altro percorso di elaborazione utilizzando l'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="59d69-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="59d69-107">L'utilizzo di un percorso di elaborazione separato per gli errori consente di ottenere diversi risultati.</span><span class="sxs-lookup"><span data-stu-id="59d69-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="59d69-108">Ad esempio, è possibile ripulire i dati e quindi rielaborare la riga con esito negativo.</span><span class="sxs-lookup"><span data-stu-id="59d69-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="59d69-109">È inoltre possibile salvare la riga con esito negativo insieme alle informazioni sugli errori aggiuntive in modo da consentire una verifica e una rielaborazione successive.</span><span class="sxs-lookup"><span data-stu-id="59d69-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="59d69-110">In questa attività si configurerà la trasformazione Lookup Currency Key in modo che le righe con esito negativo vengano reindirizzate all'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="59d69-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="59d69-111">Nel ramo del flusso di dati relativo agli errori, queste righe verranno scritte in un file.</span><span class="sxs-lookup"><span data-stu-id="59d69-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="59d69-112">Per impostazione predefinita, le due colonne supplementari in un [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] output degli errori, **ErrorCode** e **ErrorColumn**, contengono solo codici numerici che rappresentano un numero di errore e l'ID della colonna in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="59d69-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="59d69-113">Questi valori numerici possono avere un'utilità limitata senza la descrizione dell'errore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="59d69-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="59d69-114">Per aumentare l'utilità dell'output degli errori, prima che il pacchetto scriva le righe con esito negativo nel file è possibile utilizzare un componente script per accedere all'API di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e ottenere una descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="59d69-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="59d69-115">Per configurare un output degli errori</span><span class="sxs-lookup"><span data-stu-id="59d69-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="59d69-116">Nella **casella degli strumenti SSIS**espandere **comune**, quindi trascinare **componente script** sull'area di progettazione della scheda **flusso di dati** . Inserire **lo script** a destra della trasformazione **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="59d69-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="59d69-117">Nella finestra di dialogo **Seleziona tipo componente script** fare clic su **Trasformazione**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="59d69-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="59d69-118">Fare clic sulla trasformazione **Lookup Currency Key** e quindi trascinare la freccia rossa sulla trasformazione **Script** appena aggiunta per collegare i due componenti.</span><span class="sxs-lookup"><span data-stu-id="59d69-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="59d69-119">La freccia rossa rappresenta l'output degli errori della trasformazione **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="59d69-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="59d69-120">Se si utilizza la freccia rossa per collegare la trasformazione al componente script è possibile reindirizzare qualsiasi errore di elaborazione al componente script, che successivamente elaborerà gli errori e li invierà alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="59d69-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="59d69-121">Nella colonna **Errore** della finestra di dialogo **Configura output errori** selezionare **Reindirizza riga**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="59d69-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="59d69-122">Nell'area di progettazione **Flusso di dati** fare clic su **Componente script** nel **Componente script**appena aggiunto e cambiare il nome in **Get Error Description**.</span><span class="sxs-lookup"><span data-stu-id="59d69-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="59d69-123">Fare doppio clic sulla trasformazione **Get Error Description** .</span><span class="sxs-lookup"><span data-stu-id="59d69-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="59d69-124">Nella pagina **Colonne di input** della finestra di dialogo **Editor trasformazione Script** selezionare la colonna **ErrorCode** .</span><span class="sxs-lookup"><span data-stu-id="59d69-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="59d69-125">Nella pagina **Input e output** espandere **Output 0**, fare clic su **Colonne di output**e fare clic su **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="59d69-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="59d69-126">Nella `Name` Proprietà digitare **ErrorDescription** e impostare la `DataType` proprietà su **stringa Unicode [DT_WSTR]**.</span><span class="sxs-lookup"><span data-stu-id="59d69-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="59d69-127">Nella pagina **script** verificare che la `LocaleID` proprietà sia impostata su **inglese (Stati Uniti.**</span><span class="sxs-lookup"><span data-stu-id="59d69-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="59d69-128">Fare clic su **Modifica script** per aprire [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="59d69-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="59d69-129">Nel metodo `Input0_ProcessInputRow` digitare o incollare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="59d69-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="59d69-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="59d69-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="59d69-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="59d69-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="59d69-132">La subroutine completa risulterà analoga al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="59d69-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="59d69-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="59d69-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="59d69-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="59d69-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="59d69-135">Nel menu **Compila** fare clic su **Compila soluzione** per compilare lo script e salvare le modifiche, quindi chiudere VSTA.</span><span class="sxs-lookup"><span data-stu-id="59d69-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="59d69-136">Scegliere **OK** per chiudere la finestra di dialogo **Editor trasformazione Script** .</span><span class="sxs-lookup"><span data-stu-id="59d69-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="59d69-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="59d69-137">Next Steps</span></span>  
 <span data-ttu-id="59d69-138">[Passaggio 4: aggiunta di una destinazione file flat] (lesson-4-4-adding-a-flat-file-destination.md</span><span class="sxs-lookup"><span data-stu-id="59d69-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
