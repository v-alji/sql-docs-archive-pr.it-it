---
title: Connettersi a un database Teradata (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connterradb.f1
ms.assetid: 875ad4a3-a2b3-4b68-8c1c-6507e9f25b4d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 047eed5f8625059750a67c51735c7c0d61d17853
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625716"
---
# <a name="connect-to-a-teradata-database-ssas"></a><span data-ttu-id="15870-102">Connessione a un database di Teradata (SSAS)</span><span class="sxs-lookup"><span data-stu-id="15870-102">Connect to a Teradata Database (SSAS)</span></span>
  <span data-ttu-id="15870-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database Teradata.</span><span class="sxs-lookup"><span data-stu-id="15870-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Teradata database.</span></span> <span data-ttu-id="15870-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="15870-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="15870-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="15870-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15870-106">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="15870-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="15870-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="15870-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="15870-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="15870-108">UI element list</span></span>  
 <span data-ttu-id="15870-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="15870-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="15870-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="15870-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="15870-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="15870-111">This is a required field.</span></span>  
  
 <span data-ttu-id="15870-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="15870-112">**Server name**</span></span>  
 <span data-ttu-id="15870-113">Digitare o selezionare il nome dell'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="15870-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="15870-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="15870-114">**User name**</span></span>  
 <span data-ttu-id="15870-115">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="15870-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="15870-116">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="15870-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="15870-117">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="15870-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="15870-118">Tali credenziali non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="15870-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation information page are used instead.</span></span>  
  
 <span data-ttu-id="15870-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="15870-119">**Password**</span></span>  
 <span data-ttu-id="15870-120">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="15870-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="15870-121">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="15870-121">**Save my password**</span></span>  
 <span data-ttu-id="15870-122">Specificare se la password immessa nella casella **Password** è deve essere archiviata.</span><span class="sxs-lookup"><span data-stu-id="15870-122">Specify whether the password you have entered in the **Password** box should be stored.</span></span>  
  
 <span data-ttu-id="15870-123">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="15870-123">**Advanced**</span></span>  
 <span data-ttu-id="15870-124">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="15870-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="15870-125">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="15870-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="15870-126">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="15870-126">**Test Connection**</span></span>  
 <span data-ttu-id="15870-127">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="15870-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="15870-128">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="15870-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
