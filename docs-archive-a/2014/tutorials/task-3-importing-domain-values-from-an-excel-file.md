---
title: 'Attività 3: importazione di valori di dominio da un file di Excel | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 242e8309-1195-495b-9cd5-aa127748c185
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 707a3925bb6d0014e2a1248f904123b076024e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625096"
---
# <a name="task-3-importing-domain-values-from-an-excel-file"></a><span data-ttu-id="bef8e-102">Attività 3: Importazione dei valori di dominio da un file di Excel</span><span class="sxs-lookup"><span data-stu-id="bef8e-102">Task 3: Importing Domain Values from an Excel File</span></span>

  <span data-ttu-id="bef8e-103">In questa attività vengono importati i valori per il dominio di **stato** da un foglio di lavoro di un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="bef8e-103">In this task, you import values for the **State** domain from a worksheet of an Excel file.</span></span>

1.  <span data-ttu-id="bef8e-104">Fare clic su dominio **stato** nell' **elenco domini**.</span><span class="sxs-lookup"><span data-stu-id="bef8e-104">Click **State** domain in the **Domain list**.</span></span>

2.  <span data-ttu-id="bef8e-105">Verificare che la scheda **valori di dominio** sia attiva nel riquadro di destra.</span><span class="sxs-lookup"><span data-stu-id="bef8e-105">Ensure that the **Domain Values** tab is active in the right pane.</span></span>

3.  <span data-ttu-id="bef8e-106">Nel riquadro destro, sulla barra degli strumenti, fare clic sulla **freccia in giù** accanto al pulsante **Importa valori** , quindi fare clic su **Importa valori validi da Excel**.</span><span class="sxs-lookup"><span data-stu-id="bef8e-106">In the right pane, from the toolbar, click **down arrow** next to the **Import Values** button, and click **Import Valid Values from Excel**.</span></span>

     <span data-ttu-id="bef8e-107">![Importa valori validi dal menu Excel](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Importa valori validi dal menu Excel")</span><span class="sxs-lookup"><span data-stu-id="bef8e-107">![Import Valid Values from Excel Menu](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-01.jpg "Import Valid Values from Excel Menu")</span></span>

4.  <span data-ttu-id="bef8e-108">Fare clic su **Sfoglia**, selezionare **Suppliers.xls**e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="bef8e-108">Click **Browse**, select **Suppliers.xls**, and click **Open**.</span></span>

5.  <span data-ttu-id="bef8e-109">Selezionare **StatesToImport $** per il **foglio di foglio**.</span><span class="sxs-lookup"><span data-stu-id="bef8e-109">Select **StatesToImport$** for the **Worksheet**.</span></span>

     <span data-ttu-id="bef8e-110">![Finestra di dialogo Importa valori di dominio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Finestra di dialogo Importa valori di dominio")</span><span class="sxs-lookup"><span data-stu-id="bef8e-110">![Import Domain Values Dialog Box](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-02.jpg "Import Domain Values Dialog Box")</span></span>

6.  <span data-ttu-id="bef8e-111">Fare clic su **OK** per chiudere la finestra di dialogo **Importa valori di dominio** .</span><span class="sxs-lookup"><span data-stu-id="bef8e-111">Click **OK** to close the **Import Domain Values** dialog box.</span></span> <span data-ttu-id="bef8e-112">Verranno visualizzati tutti i nomi degli stati importati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bef8e-112">You should see all the names of states you imported in the list.</span></span> <span data-ttu-id="bef8e-113">Si noti che l'opzione **Mostra solo nuovi** viene selezionata automaticamente dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="bef8e-113">Notice that **Show Only New** option is automatically selected after importing.</span></span> <span data-ttu-id="bef8e-114">Quando si importano i valori e i valori precedenti non vengono visualizzati nell'elenco, questo è dovuto al fatto che questa opzione viene abilitata automaticamente dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="bef8e-114">When you import values and you don't see the old values in the list, it is because this option is automatically enabled after importing.</span></span> <span data-ttu-id="bef8e-115">Per visualizzare tutti i valori, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="bef8e-115">To see all the values, clear the check box.</span></span> <span data-ttu-id="bef8e-116">Se viene di nuovo importato lo stesso set di valori, nessuno di questi ultimi viene importato come se fosse già presente nel dominio.</span><span class="sxs-lookup"><span data-stu-id="bef8e-116">If you import the same set of values again, none of the values are imported as they already exist in the domain.</span></span>

     <span data-ttu-id="bef8e-117">![Casella di controllo Mostra solo nuovi in Valori di dominio](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Casella di controllo Mostra solo nuovi in Valori di dominio")</span><span class="sxs-lookup"><span data-stu-id="bef8e-117">![Show Only New Checkbox on Domain Values](../../2014/tutorials/media/et-importingdomainvaluesfromanexcelfile-03.jpg "Show Only New Checkbox on Domain Values")</span></span>

## <a name="next-step"></a><span data-ttu-id="bef8e-118">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="bef8e-118">Next Step</span></span>
 [<span data-ttu-id="bef8e-119">Attività 4: Impostazione delle regole di dominio</span><span class="sxs-lookup"><span data-stu-id="bef8e-119">Task 4: Setting Domain Rules</span></span>](../../2014/tutorials/task-4-setting-domain-rules.md)


