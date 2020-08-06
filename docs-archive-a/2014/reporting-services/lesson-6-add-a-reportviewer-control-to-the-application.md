---
title: "Lesson 6: Add a ReportViewer Control to the Application (Lezione 6: Aggiungere un controllo ReportViewer all'applicazione) | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637088"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="31ac7-102">Lezione 6: Aggiungere un controllo ReportViewer all'applicazione</span><span class="sxs-lookup"><span data-stu-id="31ac7-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="31ac7-103">Dopo aver progettato il report figlio tramite la Creazione guidata report, il passaggio successivo consiste nell'aggiungere un controllo ReportViewer all'applicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="31ac7-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="31ac7-104">Per aggiungere un controllo ReportViewer all'applicazione</span><span class="sxs-lookup"><span data-stu-id="31ac7-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="31ac7-105">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Default.aspx**e quindi scegliere **Progettazione viste**.</span><span class="sxs-lookup"><span data-stu-id="31ac7-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="31ac7-106">Dal gruppo **Estensioni AJAX** nella finestra della **casella degli strumenti** trascinare un controllo **ScriptManager** nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="31ac7-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="31ac7-107">Dal gruppo **Report** trascinare un controllo **ReportViewer** nell'area di progettazione sotto il controllo **ScriptManager** .</span><span class="sxs-lookup"><span data-stu-id="31ac7-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="31ac7-108">Aprire la finestra **Attività di ReportViewer** facendo clic sulla freccia nell'angolo superiore destro del controllo **ReportViewer** .</span><span class="sxs-lookup"><span data-stu-id="31ac7-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="31ac7-109">Nella casella **Scegli report** selezionare il report padre creato.</span><span class="sxs-lookup"><span data-stu-id="31ac7-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="31ac7-110">Quando si seleziona un report, le istanze delle origini dati utilizzate nel report vengono create automaticamente.</span><span class="sxs-lookup"><span data-stu-id="31ac7-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="31ac7-111">Il codice viene generato per la creazione di un'istanza di ogni oggetto DataTable e del relativo contenitore [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="31ac7-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="31ac7-112">Un controllo [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) viene aggiunto all'area di progettazione, corrispondente a ogni origine dati usata nel report.</span><span class="sxs-lookup"><span data-stu-id="31ac7-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="31ac7-113">Questo controllo dell'origine dati viene configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="31ac7-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="31ac7-114">Se si usa Microsoft Visual Studio 2012, verificare che il controllo ObjectDataSource sia associato a DataSet1 completo con lo spazio dei nomi del progetto, se il nome completo è elencato nell'elenco a discesa **scegliere l'oggetto business** , ad esempio ProjectNamespace. DataSet1TableAdapters. ProductTableAdapter.</span><span class="sxs-lookup"><span data-stu-id="31ac7-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="31ac7-115">Accedere alla casella di riepilogo facendo clic con il pulsante destro del mouse su ObjectDataSource e scegliendo **Configura origine dati**.</span><span class="sxs-lookup"><span data-stu-id="31ac7-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="31ac7-116">Scegliere Compila sito Web dal menu Compila.</span><span class="sxs-lookup"><span data-stu-id="31ac7-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="31ac7-117">Il report viene compilato e tutti gli errori, ad esempio un errore di sintassi in un'espressione del report, vengono visualizzati nell'area **Elenco errori** .</span><span class="sxs-lookup"><span data-stu-id="31ac7-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="31ac7-118">Fare clic su **Elenco errori** nella parte inferiore della finestra di Visual Studio per visualizzare l'area **Elenco errori** .</span><span class="sxs-lookup"><span data-stu-id="31ac7-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="31ac7-119">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="31ac7-119">Next Task</span></span>  
 <span data-ttu-id="31ac7-120">È stato aggiunto correttamente un controllo ReportViewer all'applicazione del sito Web.</span><span class="sxs-lookup"><span data-stu-id="31ac7-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="31ac7-121">Successivamente, si aggiungerà un'azione drill-through nel report padre.</span><span class="sxs-lookup"><span data-stu-id="31ac7-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
