---
title: Dipendenze tra oggetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725219"
---
# <a name="object-dependencies"></a><span data-ttu-id="ab7cb-102">Dipendenze tra oggetti</span><span class="sxs-lookup"><span data-stu-id="ab7cb-102">Object Dependencies</span></span>
  <span data-ttu-id="ab7cb-103">Alcuni oggetti di database hanno dipendenze con altri oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="ab7cb-104">Le viste e le stored procedure dipendono ad esempio dall'esistenza di tabelle che contengono i dati restituiti dalla vista o dalla procedura.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="ab7cb-105">Nella finestra di dialogo **Dipendenze oggetto** della pagina Generale relativa all'oggetto corrente sono elencati sia gli oggetti di database necessari per il corretto funzionamento dell'oggetto in questione, sia gli oggetti che dipendono da tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="ab7cb-106">Un oggetto che fa riferimento a un altro oggetto nella propria definizione archiviata nel catalogo del sistema è definito *entità di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="ab7cb-107">Un oggetto a cui fa riferimento un altro oggetto è denominato *entità con riferimenti*.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="ab7cb-108">Nella finestra di dialogo **Dipendenze oggetto (pagina Avanzate)** per l'oggetto corrente sono elencati gli oggetti di database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e gli oggetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che dipendono dall'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="ab7cb-109">È possibile che gli oggetti vengano archiviati in server diversi.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="ab7cb-110">Utilizzare questa finestra di dialogo per individuare le dipendenze prima di modificare o eliminare l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="ab7cb-111">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="ab7cb-111">UI element list</span></span>  
 <span data-ttu-id="ab7cb-112">**Oggetti che dipendono da**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="ab7cb-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="ab7cb-113">Fare clic su questo pulsante per visualizzare un elenco di tutti gli oggetti registrati nelle dipendenze che dipendono dall'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="ab7cb-114">**Oggetti sui quali** _\<selected object>_ **dipende da**    </span><span class="sxs-lookup"><span data-stu-id="ab7cb-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="ab7cb-115">Fare clic su questo pulsante per visualizzare un elenco di tutti gli oggetti registrati nelle dipendenze da cui dipende l'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="ab7cb-116">**Dipendenze**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-116">**Dependencies**</span></span>  
 <span data-ttu-id="ab7cb-117">Se si fa clic su **Oggetti che dipendono da** _\<selected object>_ , vengono visualizzati in ordine gerarchico gli oggetti che dipendono dall'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="ab7cb-118">Se si fa clic su **Oggetti da cui** **dipende** _\<selected object>_ , vengono visualizzati in ordine gerarchico gli oggetti da cui l'oggetto selezionato dipende.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="ab7cb-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-119">**Name**</span></span>  
 <span data-ttu-id="ab7cb-120">Consente di visualizzare il nome dell'oggetto selezionato nella visualizzazione albero **Dipendenze** precedente.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="ab7cb-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-121">**Type**</span></span>  
 <span data-ttu-id="ab7cb-122">Consente di visualizzare il tipo dell'oggetto selezionato nella visualizzazione albero **Dipendenze** precedente.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="ab7cb-123">**Ora ultima sincronizzazione**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="ab7cb-124">Questa opzione è disponibile solo nella pagina **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="ab7cb-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="ab7cb-125">Specifica l'ora e la data dell'ultimo aggiornamento delle informazioni relative alle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="ab7cb-126">**Tipo di dipendenza**</span><span class="sxs-lookup"><span data-stu-id="ab7cb-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="ab7cb-127">Questa opzione è disponibile solo nella pagina **Generale** .</span><span class="sxs-lookup"><span data-stu-id="ab7cb-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="ab7cb-128">Consente di visualizzare il tipo di dipendenza tra due oggetti.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="ab7cb-129">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab7cb-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="ab7cb-130">Dipendenza associata a schema</span><span class="sxs-lookup"><span data-stu-id="ab7cb-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="ab7cb-131">È una relazione tra due oggetti che impedisce l'eliminazione o la modifica dell'oggetto a cui si fa riferimento finché esiste l'oggetto di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="ab7cb-132">Una dipendenza associata a schema si ottiene quando viene creata una vista o una funzione definita dall'utente utilizzando la clausola WITH SCHEMABINDING, o quando una tabella fa riferimento a un altro oggetto tramite un vincolo CHECK o DEFAULT o nella definizione di una colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="ab7cb-133">Dipendenza non associata a schema</span><span class="sxs-lookup"><span data-stu-id="ab7cb-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="ab7cb-134">È una relazione tra due oggetti che non impedisce l'eliminazione o la modifica dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="ab7cb-135">Entità non disponibile o non risolta</span><span class="sxs-lookup"><span data-stu-id="ab7cb-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="ab7cb-136">Indica l'impossibilità di determinare il tipo di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="ab7cb-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="ab7cb-137">Si verifica solo quando l'oggetto selezionato si trova in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedente a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab7cb-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
