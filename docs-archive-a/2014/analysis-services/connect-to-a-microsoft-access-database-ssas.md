---
title: Connettersi a un database di Microsoft Access (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connaccessdb.f1
ms.assetid: 9fa81839-dd8b-41d3-915e-c774a707ed53
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb180a754b6bc276d588997117eb84fd1a5a873
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625728"
---
# <a name="connect-to-a-microsoft-access-database-ssas"></a><span data-ttu-id="7fe32-102">Connessione a un database di Microsoft Access (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7fe32-102">Connect to a Microsoft Access Database (SSAS)</span></span>
  <span data-ttu-id="7fe32-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="7fe32-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft Access database.</span></span> <span data-ttu-id="7fe32-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="7fe32-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="7fe32-105">Per connettersi a un database di Microsoft Access, è necessario che nel computer sia installato il provider ACE appropriato.</span><span class="sxs-lookup"><span data-stu-id="7fe32-105">To connect to a Microsoft Access database, you must have the appropriate ACE provider installed on your computer.</span></span> <span data-ttu-id="7fe32-106">Per altre informazioni, vedere [Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7fe32-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7fe32-107">Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un file in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="7fe32-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="7fe32-108">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal file selezionato.</span><span class="sxs-lookup"><span data-stu-id="7fe32-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7fe32-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="7fe32-109">UI element list</span></span>  
 <span data-ttu-id="7fe32-110">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="7fe32-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="7fe32-111">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="7fe32-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="7fe32-112">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7fe32-112">This is a required field.</span></span>  
  
 <span data-ttu-id="7fe32-113">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="7fe32-113">**Database name**</span></span>  
 <span data-ttu-id="7fe32-114">Specificare il percorso completo per un file di database di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="7fe32-114">Specify the full path for a Microsoft Access database file.</span></span>  
  
 <span data-ttu-id="7fe32-115">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="7fe32-115">**Browse**</span></span>  
 <span data-ttu-id="7fe32-116">Selezionare il percorso in cui è disponibile un file di database di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="7fe32-116">Navigate to a location where a Microsoft Access database file is available.</span></span>  
  
 <span data-ttu-id="7fe32-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="7fe32-117">**User name**</span></span>  
 <span data-ttu-id="7fe32-118">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="7fe32-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="7fe32-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="7fe32-119">**Password**</span></span>  
 <span data-ttu-id="7fe32-120">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="7fe32-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="7fe32-121">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="7fe32-121">**Save my password**</span></span>  
 <span data-ttu-id="7fe32-122">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="7fe32-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="7fe32-123">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="7fe32-123">**Advanced**</span></span>  
 <span data-ttu-id="7fe32-124">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="7fe32-124">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="7fe32-125">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="7fe32-125">**Test Connection**</span></span>  
 <span data-ttu-id="7fe32-126">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="7fe32-126">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7fe32-127">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="7fe32-127">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
