---
title: Connettersi a un database di Informix (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conninformixdb.f1
ms.assetid: b01d537c-1c04-4d7d-9146-051c249b08e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 35c7263ce9b0432802cd24b6df9165151b279d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625721"
---
# <a name="connect-to-an-informix-database-ssas"></a><span data-ttu-id="e5f5e-102">Connessione a un database di Informix (SSAS)</span><span class="sxs-lookup"><span data-stu-id="e5f5e-102">Connect to an Informix Database (SSAS)</span></span>
  <span data-ttu-id="e5f5e-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database di Informix.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Informix database.</span></span> <span data-ttu-id="e5f5e-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="e5f5e-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5f5e-106">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="e5f5e-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e5f5e-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e5f5e-108">UI element list</span></span>  
 <span data-ttu-id="e5f5e-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="e5f5e-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="e5f5e-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-111">This is a required field.</span></span>  
  
 <span data-ttu-id="e5f5e-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-112">**Server name**</span></span>  
 <span data-ttu-id="e5f5e-113">Digitare o selezionare il nome dell'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="e5f5e-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-114">**User name**</span></span>  
 <span data-ttu-id="e5f5e-115">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="e5f5e-116">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="e5f5e-117">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="e5f5e-118">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="e5f5e-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-119">**Password**</span></span>  
 <span data-ttu-id="e5f5e-120">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="e5f5e-121">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-121">**Save my password**</span></span>  
 <span data-ttu-id="e5f5e-122">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="e5f5e-123">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-123">**Advanced**</span></span>  
 <span data-ttu-id="e5f5e-124">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="e5f5e-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="e5f5e-125">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="e5f5e-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="e5f5e-126">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="e5f5e-126">**Test Connection**</span></span>  
 <span data-ttu-id="e5f5e-127">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="e5f5e-128">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="e5f5e-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
