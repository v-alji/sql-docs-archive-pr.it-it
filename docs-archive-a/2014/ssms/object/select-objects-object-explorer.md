---
title: Seleziona oggetti (Esplora oggetti) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711539"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="f15d1-102">Seleziona oggetti (Esplora oggetti)</span><span class="sxs-lookup"><span data-stu-id="f15d1-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="f15d1-103">Usare la finestra di dialogo **Seleziona oggetti** per aggiungere un oggetto a un elenco in un'altra finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f15d1-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="f15d1-104">Il titolo della finestra di dialogo e le opzioni disponibili nella finestra di dialogo dipendono dalla modalità utilizzata per la sua apertura.</span><span class="sxs-lookup"><span data-stu-id="f15d1-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="f15d1-105">Vengono visualizzate solo le opzioni disponibili. Ad esempio, quando si seleziona un proprietario per un nuovo oggetto sono disponibili solo gli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="f15d1-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f15d1-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f15d1-106">Options</span></span>  
 <span data-ttu-id="f15d1-107">**Selezionare i tipi di oggetti seguenti**</span><span class="sxs-lookup"><span data-stu-id="f15d1-107">**Select these object types**</span></span>  
 <span data-ttu-id="f15d1-108">Consente di visualizzare un elenco dei tipi ai quali appartengono gli oggetti da selezionare</span><span class="sxs-lookup"><span data-stu-id="f15d1-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="f15d1-109">I tipi includono entità ed entità a sicurezza diretta a livello di database e a livello di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f15d1-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="f15d1-110">Questa casella viene popolata con le selezioni eseguite nella finestra di dialogo **Seleziona tipi di oggetti** alla quale è possibile accedere con il pulsante **Tipi di oggetti** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="f15d1-111">**Immettere i nomi degli oggetti da selezionare**</span><span class="sxs-lookup"><span data-stu-id="f15d1-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="f15d1-112">Consente di immettere un elenco separato da punto e virgola dei nomi degli oggetti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="f15d1-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="f15d1-113">Gli oggetti da selezionare devono essere del tipo elencato nella casella **Selezionare i tipi di oggetti seguenti** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="f15d1-114">È possibile selezionare gli oggetti nell'elenco che viene visualizzato facendo clic sul pulsante **Sfoglia** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="f15d1-115">**Tipi di oggetto**</span><span class="sxs-lookup"><span data-stu-id="f15d1-115">**Object Types**</span></span>  
 <span data-ttu-id="f15d1-116">Consente di visualizzare un elenco di tipi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="f15d1-116">Displays a list of object types.</span></span> <span data-ttu-id="f15d1-117">Effettuare una o più selezioni selezionando la casella di controllo corrispondente al tipo.</span><span class="sxs-lookup"><span data-stu-id="f15d1-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="f15d1-118">**Controlla nomi**</span><span class="sxs-lookup"><span data-stu-id="f15d1-118">**Check Names**</span></span>  
 <span data-ttu-id="f15d1-119">Convalida i nomi di oggetti riportati nella casella **Immettere i nomi degli oggetti da selezionare** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="f15d1-120">Se è elencato un nome di oggetto non valido, verrà visualizzata la finestra di dialogo **Nome non trovato** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="f15d1-121">In questa finestra di dialogo sarà possibile correggere o rimuovere il nome dall'elenco di oggetti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="f15d1-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="f15d1-122">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="f15d1-122">**Browse**</span></span>  
 <span data-ttu-id="f15d1-123">Apre la finestra di dialogo **Cerca oggetti** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="f15d1-124">Questa finestra di dialogo contiene un elenco di oggetti dei tipi elencati nella casella **Selezionare i tipi di oggetti seguenti** .</span><span class="sxs-lookup"><span data-stu-id="f15d1-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="f15d1-125">Selezionare gli oggetti in questo elenco selezionando le caselle di controllo corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f15d1-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
