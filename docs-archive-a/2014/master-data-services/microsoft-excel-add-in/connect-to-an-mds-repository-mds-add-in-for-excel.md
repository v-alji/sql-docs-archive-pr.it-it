---
title: Connettersi a un repository MDS (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 8f427312-4c09-4c8b-b9f9-8b235557a74b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c1db0594f07da7ff8a78642e4b2de0eb9e507164
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714475"
---
# <a name="connect-to-an-mds-repository-mds-add-in-for-excel"></a><span data-ttu-id="4228f-102">Connettersi a un repository MDS (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="4228f-102">Connect to an MDS Repository (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="4228f-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]è necessario connettersi a un repository MDS prima che sia possibile caricare o pubblicare dati.</span><span class="sxs-lookup"><span data-stu-id="4228f-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must connect to an MDS repository before you can load or publish data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4228f-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4228f-104">Prerequisites</span></span>  
 <span data-ttu-id="4228f-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4228f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="4228f-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="4228f-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-connect-to-an-mds-repository"></a><span data-ttu-id="4228f-107">Per connettersi a un repository MDS</span><span class="sxs-lookup"><span data-stu-id="4228f-107">To connect to an MDS repository</span></span>  
  
1.  <span data-ttu-id="4228f-108">In MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]nella scheda **Dati master** nel gruppo **Connetti e carica** fare clic sulla freccia sotto il pulsante **Connetti** e fare clic su **Gestisci connessioni**.</span><span class="sxs-lookup"><span data-stu-id="4228f-108">In the MDS [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], on the **Master Data** tab, in the **Connect and Load** group, click the arrow under the **Connect** button and click **Manage Connections**.</span></span>  
  
2.  <span data-ttu-id="4228f-109">Nella finestra di dialogo **Gestisci connessioni** nella sezione **Nuova connessione** fare clic su **Crea una nuova connessione**.</span><span class="sxs-lookup"><span data-stu-id="4228f-109">On the **Manage Connections** dialog box, in the **New connection** section, click **Create a new connection**.</span></span>  
  
3.  <span data-ttu-id="4228f-110">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4228f-110">Click **New**.</span></span>  
  
4.  <span data-ttu-id="4228f-111">Nella finestra di dialogo **Aggiungi nuova connessione** nel campo **Descrizione** , digitare una descrizione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="4228f-111">On the **Add New Connection** dialog box, in the **Description** field, type a description for your connection.</span></span> <span data-ttu-id="4228f-112">Questa connessione sarà visualizzata quando si fa clic sulla freccia sotto il pulsante **Connetti** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="4228f-112">This connection will be displayed when you click the arrow under the **Connect** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="4228f-113">Nella casella **Indirizzo server MDS** immettere l'URL dell'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], ad esempio http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="4228f-113">In the **MDS server address** box, type the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4228f-114">Assicurarsi che venga usato il nome del computer e non "localhost".</span><span class="sxs-lookup"><span data-stu-id="4228f-114">Ensure that you use the computer name; do not use "localhost".</span></span>  
  
6.  <span data-ttu-id="4228f-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4228f-115">Click **OK**.</span></span> <span data-ttu-id="4228f-116">Il nome viene visualizzato nella sezione **Connessioni esistenti** .</span><span class="sxs-lookup"><span data-stu-id="4228f-116">The name is displayed in the **Existing Connections** section.</span></span>  
  
7.  <span data-ttu-id="4228f-117">Facoltativamente, fare clic su **Test** per verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="4228f-117">Optionally, click **Test** to test the connection.</span></span> <span data-ttu-id="4228f-118">Una conferma o un finestra di dialogo di errore viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="4228f-118">A confirmation or error dialog is displayed.</span></span> <span data-ttu-id="4228f-119">Fare clic su **OK** per chiuderla.</span><span class="sxs-lookup"><span data-stu-id="4228f-119">Click **OK** to close it.</span></span>  
  
8.  <span data-ttu-id="4228f-120">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="4228f-120">Click **Connect**.</span></span> <span data-ttu-id="4228f-121">Viene visualizzato il riquadro **Master Data Services** .</span><span class="sxs-lookup"><span data-stu-id="4228f-121">The **Master Data Services** pane is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4228f-122">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4228f-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="4228f-123">Caricare i dati da MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="4228f-123">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)  
  
-   [<span data-ttu-id="4228f-124">Filtrare i dati prima di caricare &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4228f-124">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="4228f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4228f-125">See Also</span></span>  
 [<span data-ttu-id="4228f-126">Connessioni &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4228f-126">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
  
