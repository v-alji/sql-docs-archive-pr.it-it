---
title: "Attività 10: configurazione del dominio composito per l'utilizzo del servizio dati di riferimento | Microsoft Docs"
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726387"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="e5d92-102">Attività 10: Configurazione del dominio composito per usare il servizio dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="e5d92-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="e5d92-103">In questa attività viene configurato il dominio composito **Address Validation** per usare il servizio **Melissa Data-Address Check** .</span><span class="sxs-lookup"><span data-stu-id="e5d92-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="e5d92-104">In fase di esecuzione, durante l'attività di pulizia, tramite DQS i valori del dominio Address Validation vengono passati al servizio per la pulizia.</span><span class="sxs-lookup"><span data-stu-id="e5d92-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="e5d92-105">Per altri dettagli, vedere [eseguire il mapping di dominio/dominio composito ai dati di riferimento](https://msdn.microsoft.com/library/hh213030.aspx) .</span><span class="sxs-lookup"><span data-stu-id="e5d92-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="e5d92-106">Nella pagina principale del **client DQS**fare clic su **suppliers (Domain Management)** in **Knowledge Base recenti** per avviare la pagina di **gestione del dominio** .</span><span class="sxs-lookup"><span data-stu-id="e5d92-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="e5d92-107">Selezionare il dominio composito **Address Validation** nell' **elenco dei domini**.</span><span class="sxs-lookup"><span data-stu-id="e5d92-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="e5d92-108">Nel riquadro destro passare alla scheda dati di **riferimento** .</span><span class="sxs-lookup"><span data-stu-id="e5d92-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="e5d92-109">![Scheda Dati di riferimento](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Scheda Dati di riferimento")</span><span class="sxs-lookup"><span data-stu-id="e5d92-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="e5d92-110">Fare clic sul pulsante **Sfoglia** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="e5d92-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="e5d92-111">Nella finestra di dialogo **Catalogo dei provider di dati di riferimento online** selezionare la **casella di controllo** accanto a **Melissa Data-verifica indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="e5d92-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="e5d92-112">![Selezione di Melissa Data - Controllo indirizzo](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Selezione di Melissa Data - Controllo indirizzo")</span><span class="sxs-lookup"><span data-stu-id="e5d92-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="e5d92-113">Nel riquadro destro, nella sezione **schema** , eseguire il mapping del dominio della **linea di indirizzo** all'elemento dello schema della **riga dell'indirizzo (M)** utilizzando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e5d92-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="e5d92-114">![Esecuzione del mapping della voce Schema servizio dati di riferimento al dominio](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Esecuzione del mapping della voce Schema servizio dati di riferimento al dominio")</span><span class="sxs-lookup"><span data-stu-id="e5d92-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="e5d92-115">Fare clic sul pulsante **Aggiungi voce di schema (+)** nella barra degli strumenti per creare una voce nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e5d92-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="e5d92-116">![Pulsante della barra degli strumenti Aggiungi voce di schema](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Pulsante della barra degli strumenti Aggiungi voce di schema")</span><span class="sxs-lookup"><span data-stu-id="e5d92-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="e5d92-117">Eseguire il mapping dei domini DQS utilizzando gli elenchi a discesa come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e5d92-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="e5d92-118">![Esecuzione del mapping delle voci Schema servizio dati di riferimento a domini](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Esecuzione del mapping delle voci Schema servizio dati di riferimento a domini")</span><span class="sxs-lookup"><span data-stu-id="e5d92-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="e5d92-119">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e5d92-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e5d92-120">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="e5d92-120">Next Step</span></span>  
 [<span data-ttu-id="e5d92-121">Attività 11: Pubblicazione della Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="e5d92-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
