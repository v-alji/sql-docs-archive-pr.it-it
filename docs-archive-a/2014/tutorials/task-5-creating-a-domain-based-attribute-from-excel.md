---
title: 'Attività 5: creazione di un attributo basato su dominio da Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715883"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="d1d37-102">Attività 5: Creazione di un attributo basato su dominio di Excel</span><span class="sxs-lookup"><span data-stu-id="d1d37-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="d1d37-103">In questa attività viene convertito l'attributo **state** dell'entità **Supplier** come **attributo basato su dominio**.</span><span class="sxs-lookup"><span data-stu-id="d1d37-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="d1d37-104">Dopo aver configurato l'attributo State in modo che sia basato su dominio e pubblicato in MDS, viene creata una nuova entità denominata **state** nel server MDS con tutti i valori nella colonna e l'attributo **state** dell'entità **Supplier** verrà popolato con i valori dell'entità **state** .</span><span class="sxs-lookup"><span data-stu-id="d1d37-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="d1d37-105">A questo punto, il modello **Suppliers** deve avere due entità: **Supplier** e **state** , dove l'attributo **state** dell'entità **Supplier** è un attributo basato su dominio che dipende dall'entità **state** .</span><span class="sxs-lookup"><span data-stu-id="d1d37-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="d1d37-106">Passa alla finestra di **Excel** con **Suppliers.xlsxpuliti e corrispondenti** aperti.</span><span class="sxs-lookup"><span data-stu-id="d1d37-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="d1d37-107">Fare clic sul pulsante **Aggiorna** sulla barra multifunzione per ottenere gli aggiornamenti più recenti da MDS.</span><span class="sxs-lookup"><span data-stu-id="d1d37-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="d1d37-108">Verranno visualizzati i due record più se è stata eseguita l'attività facoltativa **4**.</span><span class="sxs-lookup"><span data-stu-id="d1d37-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="d1d37-109">Fare clic su **stato** nome colonna (cella **I1**) nella **riga di intestazione**.</span><span class="sxs-lookup"><span data-stu-id="d1d37-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="d1d37-110">![Excel - Pulsante Proprietà attributi](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Pulsante Proprietà attributi")</span><span class="sxs-lookup"><span data-stu-id="d1d37-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="d1d37-111">Fare clic su **Proprietà attributo** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="d1d37-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="d1d37-112">Nella finestra di dialogo **Proprietà attributo** selezionare **elenco vincolato (basato su dominio)** per il tipo di **attributo**.</span><span class="sxs-lookup"><span data-stu-id="d1d37-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="d1d37-113">Digitare **state** per il **nome della nuova entità** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1d37-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="d1d37-114">![Excel - Finestra di dialogo Proprietà attributi](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Finestra di dialogo Proprietà attributi")</span><span class="sxs-lookup"><span data-stu-id="d1d37-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="d1d37-115">A questo punto, in Excel dovrebbe essere visualizzata la **freccia in giù** quando si fa clic su qualsiasi valore nella colonna **stato** .</span><span class="sxs-lookup"><span data-stu-id="d1d37-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="d1d37-116">Se necessario, il valore può essere modificato utilizzando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d1d37-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="d1d37-117">![Excel - Elenco a discesa con gli Stati](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Elenco a discesa con gli Stati")</span><span class="sxs-lookup"><span data-stu-id="d1d37-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d1d37-118">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d1d37-118">Next Step</span></span>  
 [<span data-ttu-id="d1d37-119">Attività 6: Verifica della creazione dell'attributo basato su dominio tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="d1d37-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
