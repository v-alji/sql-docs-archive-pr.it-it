---
title: Cerca destinazione RFC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724831"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="70af1-102">Cerca destinazione RFC</span><span class="sxs-lookup"><span data-stu-id="70af1-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="70af1-103">Usare la finestra di dialogo **Cerca destinazione RFC** per cercare una destinazione RFC definita nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="70af1-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="70af1-104">Quando viene visualizzato l'elenco delle destinazioni RFC disponibili, selezionare la destinazione desiderata e le opzioni associate verranno compilate con i valori richiesti dal componente.</span><span class="sxs-lookup"><span data-stu-id="70af1-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="70af1-105">Sia l'origine che la destinazione SAP BW usano la finestra di dialogo **Cerca destinazione RFC** .</span><span class="sxs-lookup"><span data-stu-id="70af1-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="70af1-106">Per altre informazioni su questi componenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md) e [Destinazione SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="70af1-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70af1-107">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="70af1-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="70af1-108">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="70af1-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="70af1-109">**Per aprire la finestra di dialogo Cerca destinazione RFC**</span><span class="sxs-lookup"><span data-stu-id="70af1-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="70af1-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine e la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="70af1-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="70af1-111">Nella scheda **Flusso di dati** fare doppio clic sull'origine o sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="70af1-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="70af1-112">Nell' **Editor origine SAP BW** o nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="70af1-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="70af1-113">Nella pagina **Gestione connessione** , nella casella di gruppo **Destinazione RFC** fare clic su **Ricerca** per visualizzare la finestra di dialogo **Cerca destinazione RFC** .</span><span class="sxs-lookup"><span data-stu-id="70af1-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="70af1-114">Nell' **Editor origine SAP BW**, la casella di gruppo **Destinazione RFC** viene visualizzata solo se il valore di **Modalità di esecuzione** è **P - Attivazione catena processi** o **W - Attesa notifica**.</span><span class="sxs-lookup"><span data-stu-id="70af1-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="70af1-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="70af1-115">Options</span></span>  
 <span data-ttu-id="70af1-116">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="70af1-116">**Destination**</span></span>  
 <span data-ttu-id="70af1-117">Visualizzare il nome della destinazione RFC definito nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="70af1-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="70af1-118">**Host gateway**</span><span class="sxs-lookup"><span data-stu-id="70af1-118">**Gateway Host**</span></span>  
 <span data-ttu-id="70af1-119">Visualizzare il nome del server o l'indirizzo IP dell'host gateway.</span><span class="sxs-lookup"><span data-stu-id="70af1-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="70af1-120">In genere, il nome o l'indirizzo IP è uguale a quello del server applicazioni SAP.</span><span class="sxs-lookup"><span data-stu-id="70af1-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="70af1-121">**Servizio gateway**</span><span class="sxs-lookup"><span data-stu-id="70af1-121">**Gateway Service**</span></span>  
 <span data-ttu-id="70af1-122">Visualizzare il nome del servizio gateway, nel formato `sapgwNN`, dove `NN` è il numero del sistema.</span><span class="sxs-lookup"><span data-stu-id="70af1-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="70af1-123">**ID programma**</span><span class="sxs-lookup"><span data-stu-id="70af1-123">**Program ID**</span></span>  
 <span data-ttu-id="70af1-124">Visualizzare l'ID programma associato alla destinazione RFC.</span><span class="sxs-lookup"><span data-stu-id="70af1-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70af1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70af1-125">See Also</span></span>  
 <span data-ttu-id="70af1-126">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="70af1-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="70af1-127">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="70af1-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="70af1-128">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="70af1-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
