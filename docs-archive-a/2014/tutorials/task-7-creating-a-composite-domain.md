---
title: 'Attività 7: creazione di un dominio composito | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ae778647-1df0-4952-9a69-0ef6177eea9c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42936d25e267bcad5ba8ae512750f9e12f041579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623637"
---
# <a name="task-7-creating-a-composite-domain"></a><span data-ttu-id="73c3a-102">Attività 7: Creazione di un dominio composito</span><span class="sxs-lookup"><span data-stu-id="73c3a-102">Task 7: Creating a Composite Domain</span></span>
  <span data-ttu-id="73c3a-103">In questa attività viene creato un dominio composito, la **convalida dell'indirizzo**, che include i domini della riga dell' **Indirizzo**, **della città**, **dello stato**e del file **zip** .</span><span class="sxs-lookup"><span data-stu-id="73c3a-103">In this task, you create a composite domain, **Address Validation**, which comprises **Address Line**, **City**, **State**, and **Zip** domains.</span></span> <span data-ttu-id="73c3a-104">Un dominio composito consente di definire una regola tra domini che interessa più domini di una regola.</span><span class="sxs-lookup"><span data-stu-id="73c3a-104">A composite domain lets you define a cross-domain rule that involves multiple domains in a rule.</span></span> <span data-ttu-id="73c3a-105">Vi sono altri vantaggi correlati a un dominio composito, quale la possibilità di analizzare un valore di campo in più domini.</span><span class="sxs-lookup"><span data-stu-id="73c3a-105">There are other advantages to a composite domain such as being able to parse a field value into multiple domains.</span></span>  <span data-ttu-id="73c3a-106">Ad esempio, un valore per un campo Nome completo può essere analizzato in domini diversi First Name, Middle Name e Last Name.</span><span class="sxs-lookup"><span data-stu-id="73c3a-106">For example, a value for a Full Name field can be parsed into separate First Name, Middle Name, and Last Name domains.</span></span> <span data-ttu-id="73c3a-107">In questa esercitazione viene definita solo una regola tra domini.</span><span class="sxs-lookup"><span data-stu-id="73c3a-107">In this tutorial, you only define a cross-domain rule.</span></span> <span data-ttu-id="73c3a-108">Per altri dettagli, vedere [gestione di un dominio composito](https://msdn.microsoft.com/library/hh510399.aspx) .</span><span class="sxs-lookup"><span data-stu-id="73c3a-108">See [Managing a Composite Domain](https://msdn.microsoft.com/library/hh510399.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="73c3a-109">Nel riquadro sinistro fare clic sul pulsante **Crea un dominio composito** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="73c3a-109">In the left pane, click **Create a composite domain** button on the toolbar.</span></span>  
  
     <span data-ttu-id="73c3a-110">![Pulsante della barra degli strumenti Crea un dominio composito](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Pulsante della barra degli strumenti Crea un dominio composito")</span><span class="sxs-lookup"><span data-stu-id="73c3a-110">![Create a Composite Domain Toolbar Button](../../2014/tutorials/media/et-creatingacompositedomain-01.jpg "Create a Composite Domain Toolbar Button")</span></span>  
  
2.  <span data-ttu-id="73c3a-111">Immettere la **convalida degli indirizzi** per il nome di **dominio composito**.</span><span class="sxs-lookup"><span data-stu-id="73c3a-111">Enter **Address Validation** for the **Composite Domain Name**.</span></span>  
  
     <span data-ttu-id="73c3a-112">![Dominio composito di convalida indirizzi](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Dominio composito di convalida indirizzi")</span><span class="sxs-lookup"><span data-stu-id="73c3a-112">![Address Validation Composite Domain](../../2014/tutorials/media/et-creatingacompositedomain-02.jpg "Address Validation Composite Domain")</span></span>  
  
3.  <span data-ttu-id="73c3a-113">Dall'elenco di domini selezionare **Indirizzo riga**, **città**, **stato**e **Cap** , quindi fare clic sulla **freccia destra** per aggiungerli all'elenco **domini in domini compositi** .</span><span class="sxs-lookup"><span data-stu-id="73c3a-113">From the domain list select **Address Line**, **City**, **State**, and **Zip** and click **right arrow** to add them to the **Domains in Composite Domain** list.</span></span>  
  
4.  <span data-ttu-id="73c3a-114">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="73c3a-114">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="73c3a-115">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="73c3a-115">Next Step</span></span>  
 [<span data-ttu-id="73c3a-116">Attività 8: Creazione di una regola per un dominio composito</span><span class="sxs-lookup"><span data-stu-id="73c3a-116">Task 8: Creating a Composite Domain Rule</span></span>](../../2014/tutorials/task-8-creating-a-composite-domain-rule.md)  
  
  
