---
title: Impostare i valori dei parametri dopo la distribuzione del progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726072"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="c9171-102">Impostazione dei valori di parametri dopo la distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="c9171-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="c9171-103">La Distribuzione guidata consente di impostare i valori dei parametri predefiniti quando si distribuisce il progetto nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="c9171-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="c9171-104">Quando il progetto si trova nel catalogo, è possibile utilizzare Transact-SQL o Esplora oggetti di SQL Server Management Studio (SSMS) per impostare i valori predefiniti del server.</span><span class="sxs-lookup"><span data-stu-id="c9171-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="c9171-105">Per impostare i valori predefiniti del server con Esplora oggetti di SSMS:</span><span class="sxs-lookup"><span data-stu-id="c9171-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="c9171-106">Selezionare e fare clic con il pulsante destro del mouse sul progetto nel nodo **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="c9171-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="c9171-107">Per aprire la finestra di dialogo **Proprietà progetto** fare clic su **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="c9171-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="c9171-108">Aprire la pagina dei parametri facendo clic su **Parametri** in **Selezione pagina**.</span><span class="sxs-lookup"><span data-stu-id="c9171-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="c9171-109">Selezionare il parametro desiderato nell'elenco **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="c9171-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="c9171-110">Nota: la colonna **Contenitore** consente di distinguere tra i parametri del progetto e i parametri del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c9171-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="c9171-111">Nella colonna **Valore** specificare il valore del parametro predefinito del server desiderato.</span><span class="sxs-lookup"><span data-stu-id="c9171-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="c9171-112">Per impostare valori predefiniti del server con Transact-SQL, usare la stored procedure [catalog.set_object_parameter_value &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c9171-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="c9171-113">Per visualizzare i valori predefiniti del server corrente, eseguire una query nella vista [catalog.object_parameters &#40;database SSISDB&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c9171-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="c9171-114">Per cancellare un valore predefinito del server, usare la stored procedure [catalog.clear_object_parameter_value &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="c9171-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9171-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9171-115">See Also</span></span>  
 [<span data-ttu-id="c9171-116">Integration Services &#40;parametri di&#41; SSIS</span><span class="sxs-lookup"><span data-stu-id="c9171-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
