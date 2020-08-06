---
title: Finestra di dialogo Imposta valore parametro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ce9c2201-4e9a-4495-948f-b68deeaa7955
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 637267603c66921a566ca0d2a3f49f6142cfd203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721675"
---
# <a name="set-parameter-value-dialog-box"></a><span data-ttu-id="0588c-102">Finestra di dialogo Imposta valore parametro</span><span class="sxs-lookup"><span data-stu-id="0588c-102">Set Parameter Value Dialog Box</span></span>
  <span data-ttu-id="0588c-103">Utilizzare la finestra di dialogo **Imposta valore parametro** per impostare i valori per i parametri e le proprietà di gestione connessione per progetti e pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0588c-103">Use the **Set Parameter Value** dialog box to set values for parameters and connection manager properties, for projects and packages.</span></span>  
  
 <span data-ttu-id="0588c-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="0588c-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="0588c-105">Aprire la finestra di dialogo Imposta valore parametro</span><span class="sxs-lookup"><span data-stu-id="0588c-105">Open the Set Parameter Value dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="0588c-106">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="0588c-106">Configure the options</span></span>](#option)  
  
##  <a name="open-the-set-parameter-value-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="0588c-107">Aprire la finestra di dialogo Imposta valore parametro</span><span class="sxs-lookup"><span data-stu-id="0588c-107">Open the Set Parameter Value dialog box</span></span>  
  
1.  <span data-ttu-id="0588c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0588c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="0588c-109">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="0588c-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="0588c-110">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="0588c-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="0588c-111">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="0588c-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="0588c-112">Fare clic con il pulsante destro del mouse su un pacchetto o un progetto, scegliere **Configura**e quindi fare clic sul pulsante con i puntini di sospensione nella scheda **Parametri** o nella scheda **Gestioni connessioni** .</span><span class="sxs-lookup"><span data-stu-id="0588c-112">Right-click a package or project, click **Configure**, and then click the ellipsis button in the **Parameters** tab or in the **Connection Managers** tab.</span></span>  
  
##  <a name="configure-the-options"></a><a name="option"></a> <span data-ttu-id="0588c-113">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="0588c-113">Configure the options</span></span>  
 <span data-ttu-id="0588c-114">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="0588c-114">**Parameter**</span></span>  
 <span data-ttu-id="0588c-115">Viene elencato il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="0588c-115">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="0588c-116">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0588c-116">**Type**</span></span>  
 <span data-ttu-id="0588c-117">Elenca il tipo di dati del valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="0588c-117">Lists the data type of the parameter value.</span></span>  
  
 <span data-ttu-id="0588c-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0588c-118">**Description**</span></span>  
 <span data-ttu-id="0588c-119">Mostra una descrizione facoltativa per il parametro.</span><span class="sxs-lookup"><span data-stu-id="0588c-119">Shows an optional description for the parameter.</span></span>  
  
 <span data-ttu-id="0588c-120">**Modifica valore**</span><span class="sxs-lookup"><span data-stu-id="0588c-120">**Edit value**</span></span>  
 <span data-ttu-id="0588c-121">Selezionare questa opzione per modificare il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="0588c-121">Select this option to edit the parameter value.</span></span>  
  
 <span data-ttu-id="0588c-122">**Usa valore predefinito del pacchetto**</span><span class="sxs-lookup"><span data-stu-id="0588c-122">**Use default value from package**</span></span>  
 <span data-ttu-id="0588c-123">Selezionare questa opzione per utilizzare il valore del parametro predefinito archiviato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0588c-123">Select this option to use the default parameter value stored in the package.</span></span>  
  
 <span data-ttu-id="0588c-124">**Usa variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="0588c-124">**Use environment variable**</span></span>  
 <span data-ttu-id="0588c-125">Selezionare questa opzione per utilizzare un valore della variabile archiviato nell'ambiente, a cui fa riferimento il progetto o il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0588c-125">Select this option to use a variable value stored in the environment, which is referenced by the project or package.</span></span> <span data-ttu-id="0588c-126">Per aggiungere un riferimento all'ambiente a un progetto o a un pacchetto, utilizzare la finestra di dialogo **Configura** .</span><span class="sxs-lookup"><span data-stu-id="0588c-126">To add an environment reference to a project or package, use the **Configure** dialog box.</span></span> <span data-ttu-id="0588c-127">Per ulteriori informazioni, vedere [Configure Dialog Box](configure-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="0588c-127">For more information, see [Configure Dialog Box](configure-dialog-box.md).</span></span>  
  
  
