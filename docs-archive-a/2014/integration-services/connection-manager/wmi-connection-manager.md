---
title: Gestione connessione WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629568"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="3ff0e-102">Gestione connessione WMI</span><span class="sxs-lookup"><span data-stu-id="3ff0e-102">WMI Connection Manager</span></span>
  <span data-ttu-id="3ff0e-103">Una gestione connessione WMI consente a un pacchetto di utilizzare WMI (Windows Management Instrumentation, Strumentazione gestione Windows) per la gestione delle informazioni in un ambiente aziendale.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="3ff0e-104">La gestione connessione WMI viene usata dall'attività Servizio Web inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff0e-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="3ff0e-105">Quando si aggiunge una gestione connessione WMI a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione WMI, imposta le proprietà della gestione connessione e la aggiunge alla `Connections` raccolta del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="3ff0e-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `WMI`.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="3ff0e-107">Configurazione della gestione connessione WMI</span><span class="sxs-lookup"><span data-stu-id="3ff0e-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="3ff0e-108">Per configurare una gestione connessione WMI, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3ff0e-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="3ff0e-109">Specificare il nome di un server.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="3ff0e-110">Specificare uno spazio dei nomi sul server.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="3ff0e-111">Selezionare la modalità di autenticazione per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="3ff0e-112">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="3ff0e-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="3ff0e-113">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione WMI](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="3ff0e-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="3ff0e-114">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="3ff0e-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff0e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ff0e-115">See Also</span></span>  
 <span data-ttu-id="3ff0e-116">[Attività servizio Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="3ff0e-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="3ff0e-117">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3ff0e-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
