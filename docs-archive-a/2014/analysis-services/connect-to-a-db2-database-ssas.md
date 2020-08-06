---
title: Connettersi a un database DB2 (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625733"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="6fdcb-102">Connettersi a un database di DB2 (SSAS)</span><span class="sxs-lookup"><span data-stu-id="6fdcb-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="6fdcb-103">Questa pagina dell' **Importazione guidata tabella** consente di specificare le impostazioni per connettersi a un database di DB2.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="6fdcb-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="6fdcb-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6fdcb-106">In caso di selezione di un database in questa pagina, vengono utilizzate le credenziali dell'utente specificate.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="6fdcb-107">Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6fdcb-108">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6fdcb-108">UI element list</span></span>  
 <span data-ttu-id="6fdcb-109">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="6fdcb-110">Digitare un nome univoco per questa connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="6fdcb-111">Questo campo è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-111">This is a required field.</span></span>  
  
 <span data-ttu-id="6fdcb-112">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-112">**Server name**</span></span>  
 <span data-ttu-id="6fdcb-113">Digitare o selezionare l'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="6fdcb-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-114">**User name**</span></span>  
 <span data-ttu-id="6fdcb-115">Specificare un nome utente per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="6fdcb-116">Questo nome utente viene utilizzato quando si crea la stringa di connessione per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="6fdcb-117">Queste credenziali vengono utilizzate anche in caso di visualizzazione in anteprima e filtro dei dati nella finestra Proprietà tabella e nell'Importazione guidata.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="6fdcb-118">Non vengono utilizzate per importare o aggiornare dati; in tal caso vengono infatti utilizzate le credenziali di Windows specificate nella pagina Impostazioni di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="6fdcb-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-119">**Password**</span></span>  
 <span data-ttu-id="6fdcb-120">Specificare una password per la connessione al database.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="6fdcb-121">**Salva password**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-121">**Save my password**</span></span>  
 <span data-ttu-id="6fdcb-122">Specificare se la password immessa nella casella **Password** è stata archiviata.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="6fdcb-123">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-123">**Database name**</span></span>  
 <span data-ttu-id="6fdcb-124">Selezionare un database dall'elenco di database.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="6fdcb-125">**Raccolta pacchetti**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-125">**Package Collection**</span></span>  
 <span data-ttu-id="6fdcb-126">Specificare il nome della raccolta per i pacchetti di DB2.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="6fdcb-127">Un provider utilizza i pacchetti per creare istruzioni SQL e chiamare stored procedure.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="6fdcb-128">**Schema predefinito**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-128">**Default Schema**</span></span>  
 <span data-ttu-id="6fdcb-129">Specificare il nome dello schema predefinito per il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="6fdcb-130">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-130">**Advanced**</span></span>  
 <span data-ttu-id="6fdcb-131">Impostare altre proprietà relative alla connessione tramite la finestra di dialogo **Impostazione delle proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="6fdcb-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="6fdcb-132">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="6fdcb-132">**Test Connection**</span></span>  
 <span data-ttu-id="6fdcb-133">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="6fdcb-134">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="6fdcb-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
