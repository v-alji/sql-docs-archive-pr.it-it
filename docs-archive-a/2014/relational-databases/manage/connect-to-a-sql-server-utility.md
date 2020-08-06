---
title: Effettuare la connessione a Utilità SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: b9b90b8d-241f-4b74-ac14-de7b10ea1821
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8e59a28e083fc302faebbcba932c18a04e73a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625392"
---
# <a name="connect-to-a-sql-server-utility"></a><span data-ttu-id="2bee0-102">Effettuare la connessione a Utilità SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2bee0-102">Connect to a SQL Server Utility</span></span>
  <span data-ttu-id="2bee0-103">Prima di connettersi a Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario creare un punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="2bee0-103">Before you can connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, you must create a utility control point (UCP).</span></span> <span data-ttu-id="2bee0-104">Per altre informazioni, vedere [Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="2bee0-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>

 <span data-ttu-id="2bee0-105">Per visualizzare e gestire l'integrità delle risorse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , usare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) per connettersi a Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2bee0-105">To view and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resource health, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] (SSMS) to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>

 <span data-ttu-id="2bee0-106">Per connettersi a Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite SSMS:</span><span class="sxs-lookup"><span data-stu-id="2bee0-106">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility through SSMS:</span></span>

1.  <span data-ttu-id="2bee0-107">Avviare SSMS.</span><span class="sxs-lookup"><span data-stu-id="2bee0-107">Launch SSMS.</span></span>

2.  <span data-ttu-id="2bee0-108">In SSMS connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bee0-108">In SSMS, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

3.  <span data-ttu-id="2bee0-109">Fare clic su **Visualizza** e quindi su **Esplora utilità**.</span><span class="sxs-lookup"><span data-stu-id="2bee0-109">Click **View** and then **Utility Explorer**.</span></span>

4.  <span data-ttu-id="2bee0-110">Nel riquadro di spostamento di Esplora utilità fare clic su ![](../../database-engine/media/connect-to-utility.gif "Connetti a utilità")**Connetti a utilità**.</span><span class="sxs-lookup"><span data-stu-id="2bee0-110">In the Utility Explorer navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span>

5.  <span data-ttu-id="2bee0-111">Nella finestra di dialogo **Connetti al server** specificare il nome dell'istanza del punto di controllo dell'utilità, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="2bee0-111">In the **Connect to Server** dialog box, specify the UCP instance name, then click **Connect**.</span></span>

6.  <span data-ttu-id="2bee0-112">Visualizzare il riquadro di spostamento di Esplora utilità per passare a una visualizzazione albero delle risorse di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="2bee0-112">View the Utility Explorer Navigation Pane to see a tree view of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources in the UCP.</span></span>

 <span data-ttu-id="2bee0-113">La creazione di un nuovo punto di controllo dell'utilità consente anche di connettersi a Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2bee0-113">Creating a new UCP also connects you to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="2bee0-114">Per altre informazioni, vedere [Creare un punto di controllo dell'Utilità SQL Server &#40;Utilità SQL Server&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2bee0-114">For more information, see [Create a SQL Server Utility Control Point &#40;SQL Server Utility&#41;](create-a-sql-server-utility-control-point-sql-server-utility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2bee0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bee0-115">See Also</span></span>
 <span data-ttu-id="2bee0-116">Visualizzazione delle [funzionalità e delle attività Utilità SQL Server](sql-server-utility-features-and-tasks.md) [integrità risorse risultati dei criteri &#40;utilità SQL Server&#41;](view-resource-health-policy-results-sql-server-utility.md)</span><span class="sxs-lookup"><span data-stu-id="2bee0-116">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) [View Resource Health Policy Results &#40;SQL Server Utility&#41;](view-resource-health-policy-results-sql-server-utility.md)</span></span>


