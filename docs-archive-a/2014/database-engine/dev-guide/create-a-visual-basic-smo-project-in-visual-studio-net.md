---
title: Creare un progetto Visual Basic SMO in Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726227"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="26893-102">Creare un progetto SMO per Visual Basic in Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="26893-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="26893-103">In questa sezione viene descritto come compilare un'applicazione console SMO semplice.</span><span class="sxs-lookup"><span data-stu-id="26893-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="26893-104">In questo esempio vengono importati spazi dei nomi affinché il programma faccia riferimento ai tipi SMO.</span><span class="sxs-lookup"><span data-stu-id="26893-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="26893-105">L'importazione dello spazio dei nomi `Agent` è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="26893-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="26893-106">Utilizzarla quando si scrive un programma che utilizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="26893-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="26893-107">Lo spazio dei nomi `Common` è necessario per stabilire una connessione protetta all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26893-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="26893-108">Lo spazio dei nomi `SqlClient` viene utilizzato per elaborare gli errori di eccezione SQL.</span><span class="sxs-lookup"><span data-stu-id="26893-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="26893-109">Creazione di un progetto Visual Basic SMO in Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="26893-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="26893-110">Avviare [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (o [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="26893-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="26893-111">Scegliere **Nuovo progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="26893-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="26893-112">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="26893-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="26893-113">Nella finestra di dialogo **Tipi progetto** selezionare **Visual Basic**, quindi selezionare **Windows**.</span><span class="sxs-lookup"><span data-stu-id="26893-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="26893-114">Nel [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] riquadro Modelli installati selezionare **applicazione console.**</span><span class="sxs-lookup"><span data-stu-id="26893-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="26893-115">Opzionale Nel campo **nome** Digitare il nome della nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="26893-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="26893-116">Fare clic su **OK** per caricare il [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] modello applicazione console.</span><span class="sxs-lookup"><span data-stu-id="26893-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="26893-117">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="26893-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="26893-118">Verrà visualizzata la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="26893-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="26893-119">Fare clic su **Sfoglia**, individuare gli assembly SMO nella cartella C:\Programmi\Microsoft SQL Server\120\SDK\Assemblies e selezionare i file seguenti.</span><span class="sxs-lookup"><span data-stu-id="26893-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="26893-120">che costituiscono i file minimi necessari per compilare un'applicazione SMO:</span><span class="sxs-lookup"><span data-stu-id="26893-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="26893-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="26893-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="26893-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="26893-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="26893-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="26893-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="26893-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="26893-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26893-125">Per selezionare più file, utilizzare il tasto `Ctrl`.</span><span class="sxs-lookup"><span data-stu-id="26893-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="26893-126">Aggiungere eventuali assembly SMO necessari.</span><span class="sxs-lookup"><span data-stu-id="26893-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="26893-127">Se ad esempio si esegue la programmazione specifica di [!INCLUDE[ssSB](../../includes/sssb-md.md)], aggiungere gli assembly seguenti:</span><span class="sxs-lookup"><span data-stu-id="26893-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="26893-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="26893-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="26893-129">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="26893-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="26893-130">Scegliere **codice**dal menu **Visualizza** . in alternativa, selezionare la finestra Module1. vb per visualizzare la finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="26893-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="26893-131">Nel codice, prima di qualsiasi dichiarazione, digitare le istruzioni **Imports** seguenti per qualificare i tipi nello spazio dei nomi SMO.</span><span class="sxs-lookup"><span data-stu-id="26893-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="26893-132">SMO dispone di vari spazi dei nomi in Microsoft.SqlServer.Management.Smo, ad esempio Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="26893-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="26893-133">Aggiungere questi spazi dei nomi poiché sono necessari.</span><span class="sxs-lookup"><span data-stu-id="26893-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="26893-134">A questo punto è possibile aggiungere il codice SMO.</span><span class="sxs-lookup"><span data-stu-id="26893-134">You can now add your SMO code.</span></span>  
  
  
