---
title: 'Attività 4: creazione di un progetto SSIS con SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717051"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="49a14-102">Attività 4: Creazione di un progetto SSIS tramite SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="49a14-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="49a14-103">In questa attività viene creato un progetto SSIS utilizzando **SQL Server Data Tools** per automatizzare la pulizia e la corrispondenza dei dati fornitore.</span><span class="sxs-lookup"><span data-stu-id="49a14-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="49a14-104">Avviare **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="49a14-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="49a14-105">Fare clic sul pulsante Start, scegliere **tutti i programmi**, espandere **Microsoft SQL Server 2012**e fare clic su **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="49a14-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="49a14-106">Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="49a14-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="49a14-107">Espandere **Business Intelligence** nel riquadro **modelli installati** e selezionare **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="49a14-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="49a14-108">![Visual Studio - Finestra di dialogo Nuovo progetto](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - Finestra di dialogo Nuovo progetto")</span><span class="sxs-lookup"><span data-stu-id="49a14-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="49a14-109">Selezionare **Integration Services progetto** nell' **elenco dei tipi di progetto**.</span><span class="sxs-lookup"><span data-stu-id="49a14-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="49a14-110">Digitare **CleanseAndCurateSuppliers** per **nome** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49a14-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="49a14-111">Nella finestra **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Package. dtsx** e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="49a14-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="49a14-112">Se non viene visualizzata **Esplora soluzioni** finestra, fare clic su **Visualizza** nella barra dei menu e fare clic su **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="49a14-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="49a14-113">![Package.dtsx - Menu Rinomina](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Menu Rinomina")</span><span class="sxs-lookup"><span data-stu-id="49a14-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="49a14-114">Digitare **CleanseAndCurate. dtsx** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="49a14-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="49a14-115">Verificare che l' **estensione** rimanga **. dtsx**.</span><span class="sxs-lookup"><span data-stu-id="49a14-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="49a14-116">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="49a14-116">Next Step</span></span>
 [<span data-ttu-id="49a14-117">Attività 5: Aggiunta dell'attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="49a14-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


