---
title: Modificare la query di origine OData in fase di esecuzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724824"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="801b8-102">Modificare la query di origine OData in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="801b8-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="801b8-103">È possibile modificare la query di origine OData in fase di esecuzione aggiungendo un'espressione alla proprietà **[Origine OData].[Query]** dell'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="801b8-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="801b8-104">Si noti che le colonne devono essere le stesse di quelle utilizzate in fase di progettazione; in caso contrario, verrà visualizzato un errore al momento dell'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="801b8-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="801b8-105">Assicurarsi di specificare le stesse colonne (nello stesso ordine) quando si utilizza l'opzione query $select.</span><span class="sxs-lookup"><span data-stu-id="801b8-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="801b8-106">Un'alternativa più sicura all'uso dell'opzione $select consiste nel deselezionare le colonne non desiderate direttamente dall'interfaccia utente del componente di origine.</span><span class="sxs-lookup"><span data-stu-id="801b8-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="801b8-107">Sono disponibili alcune modalità differenti per impostare dinamicamente il valore di query in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="801b8-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="801b8-108">Di seguito sono riportati alcuni dei metodi più comuni.</span><span class="sxs-lookup"><span data-stu-id="801b8-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="801b8-109">Esposizione della query come parametro</span><span class="sxs-lookup"><span data-stu-id="801b8-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="801b8-110">Nella procedura seguente sono riportati i passaggi per esporre la query utilizzata da un componente di origine OData come parametro nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="801b8-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="801b8-111">Fare clic con il pulsante destro del mouse sull'**attività Flusso di dati** e selezionare l'opzione **Imposta parametri**.</span><span class="sxs-lookup"><span data-stu-id="801b8-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="801b8-112">Nella finestra di dialogo **Imposta parametri** selezionare **[\<Name of the OData Source Component>].[Query]** per **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="801b8-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="801b8-113">Scegliere se **creare un nuovo parametro** o **usare un parametro esistente**.</span><span class="sxs-lookup"><span data-stu-id="801b8-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="801b8-114">Se si seleziona **Crea nuovo parametro**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="801b8-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="801b8-115">Immettere un **nome** e una **descrizione** per il parametro.</span><span class="sxs-lookup"><span data-stu-id="801b8-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="801b8-116">Specificare il **valore** predefinito per il parametro.</span><span class="sxs-lookup"><span data-stu-id="801b8-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="801b8-117">Specificare l' **ambito** (**pacchetto** o **progetto**) per il parametro.</span><span class="sxs-lookup"><span data-stu-id="801b8-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="801b8-118">Specificare se il parametro è **obbligatorio** o meno.</span><span class="sxs-lookup"><span data-stu-id="801b8-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="801b8-119">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="801b8-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="801b8-120">Utilizzo di un'espressione</span><span class="sxs-lookup"><span data-stu-id="801b8-120">Using an Expression</span></span>  
 <span data-ttu-id="801b8-121">Questo metodo è utile quando si desidera creare dinamicamente la stringa di query in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="801b8-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="801b8-122">In questo esempio, la variabile MaxRows verrà impostata in altro modo (script, parametro e così via).</span><span class="sxs-lookup"><span data-stu-id="801b8-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="801b8-123">Selezionare l' **attività Flusso di dati** contenente l' **Origine OData**.</span><span class="sxs-lookup"><span data-stu-id="801b8-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="801b8-124">Nella finestra **Proprietà** selezionare la proprietà **Espressioni** .</span><span class="sxs-lookup"><span data-stu-id="801b8-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="801b8-125">Fare clic su... pulsante (ellissi) per visualizzare l' **Editor espressioni di proprietà**.</span><span class="sxs-lookup"><span data-stu-id="801b8-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="801b8-126">Selezionare la proprietà **[Origine OData].[Query]** .</span><span class="sxs-lookup"><span data-stu-id="801b8-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="801b8-127">Fare clic su... pulsante (ellissi) per **espressione**.</span><span class="sxs-lookup"><span data-stu-id="801b8-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="801b8-128">Immettere l' **espressione**.</span><span class="sxs-lookup"><span data-stu-id="801b8-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="801b8-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="801b8-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="801b8-130">Si noti che quando si utilizza questo approccio, è necessario assicurarsi che i valori impostati siano URL correttamente codificati.</span><span class="sxs-lookup"><span data-stu-id="801b8-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="801b8-131">Alla ricezione di valori dall'input utente, ad esempio l'impostazione di singoli valori di opzioni query da un parametro, è necessario assicurarsi che i valori siano convalidati per evitare potenziali attacchi SQL injection.</span><span class="sxs-lookup"><span data-stu-id="801b8-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
