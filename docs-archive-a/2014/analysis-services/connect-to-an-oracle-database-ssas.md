---
title: Connettersi a un Oracle Database (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connoracledb.f1
ms.assetid: 9bd177fb-8539-46cd-bf96-189ade52c2a1
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0260983f5060ecba7f618975e805ff63c507d5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625708"
---
# <a name="connect-to-an-oracle-database-ssas"></a><span data-ttu-id="459f7-102">Connessione a un database Oracle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="459f7-102">Connect to an Oracle Database (SSAS)</span></span>
  <span data-ttu-id="459f7-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database Oracle.</span><span class="sxs-lookup"><span data-stu-id="459f7-103">This page of the **Table Import Wizard** enables you to specify settings to connect to an Oracle database.</span></span> <span data-ttu-id="459f7-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="459f7-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="459f7-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="459f7-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="459f7-106">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un database in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="459f7-106">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="459f7-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="459f7-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="459f7-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="459f7-108">UI element list</span></span>  
 <span data-ttu-id="459f7-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="459f7-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="459f7-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="459f7-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="459f7-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="459f7-111">This is a required field.</span></span>  
  
 <span data-ttu-id="459f7-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="459f7-112">**Server name**</span></span>  
 <span data-ttu-id="459f7-113">Digitare o selezionare il nome dell'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="459f7-113">Type or select the name of the server instance to connect to.</span></span>  
  
 <span data-ttu-id="459f7-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="459f7-114">**User name**</span></span>  
 <span data-ttu-id="459f7-115">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="459f7-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="459f7-116">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="459f7-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="459f7-117">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="459f7-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="459f7-118">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="459f7-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="459f7-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="459f7-119">**Password**</span></span>  
 <span data-ttu-id="459f7-120">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="459f7-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="459f7-121">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="459f7-121">**Save my password**</span></span>  
 <span data-ttu-id="459f7-122">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="459f7-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="459f7-123">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="459f7-123">**Advanced**</span></span>  
 <span data-ttu-id="459f7-124">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="459f7-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="459f7-125">Per altre informazioni, vedere [Impostazione delle proprietà avanzate &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="459f7-125">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="459f7-126">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="459f7-126">**Test Connection**</span></span>  
 <span data-ttu-id="459f7-127">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="459f7-127">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="459f7-128">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="459f7-128">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
