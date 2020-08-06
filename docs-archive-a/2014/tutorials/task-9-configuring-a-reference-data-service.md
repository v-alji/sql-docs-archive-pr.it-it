---
title: 'Attività 9: configurazione di un servizio dati di riferimento | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726324"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="dc0f7-102">Attività 9: Configurazione di un servizio dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="dc0f7-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="dc0f7-103">In questa attività viene configurato DQS per l'utilizzo di un servizio dati di riferimento in Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="dc0f7-104">Nell'attività successiva verrà configurato il dominio di **convalida degli indirizzi** per l'utilizzo di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="dc0f7-105">In fase di esecuzione, durante l'attività di pulizia, DQS passa i valori dei domini nel dominio di **convalida degli indirizzi** al servizio per la pulizia.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="dc0f7-106">Per altri dettagli, vedere [configurare DQS per l'uso dei dati di riferimento](https://msdn.microsoft.com/library/hh213070.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc0f7-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="dc0f7-107">Nella pagina principale del **client DQS**, nel riquadro **Amministrazione** , fare clic su **configurazione**.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="dc0f7-108">Verificare che la scheda **dati di riferimento** sia attiva.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="dc0f7-109">Nell'area **impostazioni di rete** Digitare i valori appropriati nei campi **server proxy** e **porta** se è necessario usare un server proxy per la connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="dc0f7-110">Digitare la **chiave dell'account di Azure Marketplace** per il campo **ID account DataMarket** .</span><span class="sxs-lookup"><span data-stu-id="dc0f7-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="dc0f7-111">![Account di servizio dei dati di riferimento di Azure DataMarket](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Account di servizio dei dati di riferimento di Azure DataMarket")</span><span class="sxs-lookup"><span data-stu-id="dc0f7-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="dc0f7-112">Fare clic sul pulsante **convalida** accanto alla casella di testo per convalidare l'ID account.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="dc0f7-113">Fare clic su **OK** nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="dc0f7-114">Fare clic su **Chiudi** nella parte inferiore della pagina per passare alla pagina principale del client DQS.</span><span class="sxs-lookup"><span data-stu-id="dc0f7-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="dc0f7-115">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="dc0f7-115">Next Task</span></span>  
 [<span data-ttu-id="dc0f7-116">Attività 10: Configurazione del dominio composito per usare il servizio dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="dc0f7-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
