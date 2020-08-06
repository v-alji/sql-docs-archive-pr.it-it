---
title: 'Passaggio 1: Creazione di un nuovo progetto di Integration Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628852"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="4d58d-102">Passaggio 1: Creazione di un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="4d58d-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="4d58d-103">Il primo passaggio nella creazione di un pacchetto in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] consiste nel creare un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d58d-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="4d58d-104">Questo progetto include i modelli per gli oggetti, ovvero origini dati, viste origini dati e pacchetti usati in una soluzione di trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="4d58d-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="4d58d-105">I pacchetti che verranno creati in questa esercitazione relativa a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] interpretano i valori dei dati dipendenti dalle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="4d58d-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="4d58d-106">Se il computer non è configurato per l'utilizzo dell'opzione Inglese (Stati Uniti) per le impostazioni locali, è necessario impostare proprietà aggiuntive nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4d58d-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="4d58d-107">I pacchetti utilizzati nelle lezioni 2-5 vengono copiati dal pacchetto creato nella lezione 1 e non è necessario aggiornare le proprietà dipendenti dalle impostazioni locali nei pacchetti copiati.</span><span class="sxs-lookup"><span data-stu-id="4d58d-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d58d-108">Per questa esercitazione è richiesto Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="4d58d-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="4d58d-109">Per altre informazioni sull'installazione di SQL Server Data Tools, vedere [Scaricare SQL Server Data Tools](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="4d58d-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="4d58d-110">Per creare un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="4d58d-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="4d58d-111">Fare clic sul menu **Start** , scegliere **Programmi**, **Microsoft SQL Server**, quindi **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="4d58d-112">Scegliere **Nuovo** dal menu **File**e fare clic su **Progetto** per creare un nuovo progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d58d-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="4d58d-113">Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Business Intelligence** in **Modelli installati**e selezionare **Progetto di Integration Services** nel riquadro **Modelli** .</span><span class="sxs-lookup"><span data-stu-id="4d58d-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="4d58d-114">Nella casella **Nome** impostare il nome predefinito su **SSIS Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="4d58d-115">Facoltativamente, deselezionare la casella di controllo **Crea directory per soluzione** .</span><span class="sxs-lookup"><span data-stu-id="4d58d-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="4d58d-116">Accettare il percorso predefinito o fare clic su **Sfoglia** per individuare la cartella che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="4d58d-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="4d58d-117">Nella finestra di dialogo **Percorso progetto** fare clic sulla cartella, quindi scegliere **Seleziona cartella**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="4d58d-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="4d58d-119">Per impostazione predefinita viene creato e aggiunto al progetto un pacchetto vuoto in Pacchetti SSIS, denominato **Package.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="4d58d-120">Nella barra degli strumenti **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Package.dtsx**, fare clic su **Rinomina**e rinominare il pacchetto predefinito in **Lesson 1.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="4d58d-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4d58d-121">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4d58d-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4d58d-122">Passaggio 2: Aggiunta e configurazione di una gestione connessione file flat</span><span class="sxs-lookup"><span data-stu-id="4d58d-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
