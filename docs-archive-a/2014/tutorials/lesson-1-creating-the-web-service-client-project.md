---
title: 'Lezione 1: creazione del progetto client del servizio Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719103"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="00474-102">Lezione 1: Creazione del progetto client per il servizio Web</span><span class="sxs-lookup"><span data-stu-id="00474-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="00474-103">Per questa esercitazione verrà creata una semplice applicazione console che accede al servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="00474-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="00474-104">Nelle procedure si presuppone che l'ambiente di sviluppo utilizzato sia [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00474-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="00474-105">Per creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="00474-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="00474-106">Scegliere **nuovo**dal menu **file** , quindi fare clic su **progetto** per aprire la finestra di dialogo **nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="00474-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="00474-107">Nel riquadro sinistro, in **modelli installati**, fare clic su **Visual Basic** o sul nodo **Visual C#** e selezionare una categoria di tipi di progetto dall'elenco espanso.</span><span class="sxs-lookup"><span data-stu-id="00474-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="00474-108">Scegliere il tipo di progetto **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="00474-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="00474-109">Nella casella **nome** immettere un nome per il progetto.</span><span class="sxs-lookup"><span data-stu-id="00474-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="00474-110">Digitare il nome `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="00474-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="00474-111">Nella casella **percorso** immettere il percorso in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare alla cartella.</span><span class="sxs-lookup"><span data-stu-id="00474-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="00474-112">Una visualizzazione compressa del progetto viene visualizzata in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="00474-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="00474-113">Espandere il nodo del progetto in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="00474-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="00474-114">[!INCLUDE[msCoName](../includes/msconame-md.md)]Al progetto è stato aggiunto un file con il nome predefinito Program.cs (Module1. vb per [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="00474-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00474-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00474-115">See Also</span></span>  
 <span data-ttu-id="00474-116">[Lezione 2: aggiunta di un riferimento Web](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="00474-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="00474-117">Accesso al servizio Web ReportServer utilizzando Visual Basic o Visual C&#35; &#40;SSRS tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="00474-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
