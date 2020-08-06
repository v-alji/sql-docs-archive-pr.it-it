---
title: Creare un progetto Visual C# SMO in Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634975"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="6d7fb-102">Creare un progetto SMO per Visual C# in Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="6d7fb-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="6d7fb-103">In questa sezione viene descritto come compilare un'applicazione console SMO semplice.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="6d7fb-104">In questo esempio vengono importati spazi dei nomi affinché il programma faccia riferimento ai tipi SMO.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="6d7fb-105">L'importazione dello spazio dei nomi `Agent` è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="6d7fb-106">Utilizzarla quando si scrive un programma che utilizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="6d7fb-107">Lo spazio dei nomi `Common` è necessario per stabilire una connessione protetta all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d7fb-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6d7fb-108">Lo spazio dei nomi `SqlClient` viene utilizzato per elaborare gli errori di eccezione SQL.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="6d7fb-109">Creazione di un progetto Visual C# SMO in Visual Studio.NET</span><span class="sxs-lookup"><span data-stu-id="6d7fb-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="6d7fb-110">Avviare [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (o [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6d7fb-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="6d7fb-111">Scegliere **Nuovo progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="6d7fb-112">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="6d7fb-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="6d7fb-113">Nella finestra di dialogo **Tipi progetto** selezionare **Visual C#**, quindi selezionare **Windows**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="6d7fb-114">Nel [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] riquadro Modelli installati selezionare **applicazione Windows**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="6d7fb-115">Opzionale Nel campo **nome** Digitare il nome della nuova applicazione</span><span class="sxs-lookup"><span data-stu-id="6d7fb-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="6d7fb-116">Selezionare il tipo di applicazione di Visual C#.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-116">Select the Visual C# application type.</span></span> <span data-ttu-id="6d7fb-117">Per gli esempi seguenti, selezionare **applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="6d7fb-118">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="6d7fb-119">Verrà visualizzata la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="6d7fb-120">Fare clic su **Sfoglia**, individuare gli assembly SMO nella [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] cartella e selezionare i file seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="6d7fb-121">che costituiscono i file minimi necessari per compilare un'applicazione SMO:</span><span class="sxs-lookup"><span data-stu-id="6d7fb-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="6d7fb-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="6d7fb-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="6d7fb-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="6d7fb-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="6d7fb-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="6d7fb-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="6d7fb-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="6d7fb-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6d7fb-126">Per selezionare più file, utilizzare il tasto `Ctrl`.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="6d7fb-127">Aggiungere eventuali assembly SMO necessari.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="6d7fb-128">Se ad esempio si esegue la programmazione specifica di [!INCLUDE[ssSB](../../includes/sssb-md.md)], aggiungere gli assembly seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d7fb-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="6d7fb-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="6d7fb-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="6d7fb-130">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="6d7fb-131">Scegliere **codice**dal menu **Visualizza** . in alternativa, selezionare Program1.cs [Progettazione] Windows e fare doppio clic sul Windows Form per visualizzare la finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="6d7fb-132">Nel codice prima dell'istruzione dello spazio dei nomi, digitare le istruzioni `using` seguenti per qualificare i tipi nello spazio dei nomi SMO:</span><span class="sxs-lookup"><span data-stu-id="6d7fb-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="6d7fb-133">SMO dispone di vari spazi dei nomi in Microsoft.SqlServer.Management.Smo, ad esempio Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="6d7fb-134">Aggiungere questi spazi dei nomi poiché sono necessari.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="6d7fb-135">A questo punto è possibile aggiungere il codice SMO.</span><span class="sxs-lookup"><span data-stu-id="6d7fb-135">You can now add your SMO code.</span></span>  
  
  
