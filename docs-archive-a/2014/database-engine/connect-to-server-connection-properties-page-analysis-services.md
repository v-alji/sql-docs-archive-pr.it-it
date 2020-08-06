---
title: Connetti al server (pagina Proprietà connessione) - Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711019"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="58d6a-102">Connetti al server (pagina Proprietà connessione) - Analysis Services</span><span class="sxs-lookup"><span data-stu-id="58d6a-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="58d6a-103">Usare questa scheda per visualizzare o specificare le opzioni relative alla connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o alla registrazione di [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="58d6a-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="58d6a-104">Le opzioni**Connetti** e **Opzioni** vengono visualizzate in questa finestra di dialogo solamente durante la connessione.</span><span class="sxs-lookup"><span data-stu-id="58d6a-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="58d6a-105">Le opzioni**Test** e **Salva** vengono visualizzate in questa finestra di dialogo solamente durante la registrazione del [!INCLUDE[ssAS](../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58d6a-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="58d6a-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="58d6a-106">Options</span></span>  
 <span data-ttu-id="58d6a-107">**Connettersi al database**</span><span class="sxs-lookup"><span data-stu-id="58d6a-107">**Connect to database**</span></span>  
 <span data-ttu-id="58d6a-108">Selezionare dall'elenco un database al quale connettersi.</span><span class="sxs-lookup"><span data-stu-id="58d6a-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="58d6a-109">Se si seleziona **\<default>** , verrà stabilita la connessione al database predefinito per il server.</span><span class="sxs-lookup"><span data-stu-id="58d6a-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="58d6a-110">Se si seleziona **\<Browse server>** , è possibile esplorare il server per il database a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="58d6a-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="58d6a-111">**Timeout connessione**</span><span class="sxs-lookup"><span data-stu-id="58d6a-111">**Connection timeout**</span></span>  
 <span data-ttu-id="58d6a-112">Immettere il numero di secondi di attesa prima che venga stabilita una connessione prima del timeout. Il valore predefinito è 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="58d6a-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="58d6a-113">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="58d6a-113">**Execution timeout**</span></span>  
 <span data-ttu-id="58d6a-114">Immettere il numero massimo di secondi di attesa del completamento dell'esecuzione di un'attività nel server.</span><span class="sxs-lookup"><span data-stu-id="58d6a-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="58d6a-115">Il valore predefinito è zero secondi, che indica l'assenza di un timeout.</span><span class="sxs-lookup"><span data-stu-id="58d6a-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="58d6a-116">**Crittografa connessione**</span><span class="sxs-lookup"><span data-stu-id="58d6a-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="58d6a-117">Consente di forzare la crittografia della connessione.</span><span class="sxs-lookup"><span data-stu-id="58d6a-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="58d6a-118">**Reimposta tutto**</span><span class="sxs-lookup"><span data-stu-id="58d6a-118">**Reset All**</span></span>  
 <span data-ttu-id="58d6a-119">Consente di sostituire i valori delle proprietà di connessione immessi manualmente con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="58d6a-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="58d6a-120">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="58d6a-120">**Connect**</span></span>  
 <span data-ttu-id="58d6a-121">Consente di eseguire un tentativo di connessione con i valori elencati.</span><span class="sxs-lookup"><span data-stu-id="58d6a-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="58d6a-122">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="58d6a-122">**Options**</span></span>  
 <span data-ttu-id="58d6a-123">Fare clic su questo pulsante per modificare la finestra di dialogo e nascondere le opzioni aggiuntive per la connessione al server, ad esempio le opzioni per la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="58d6a-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="58d6a-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="58d6a-124">**Test**</span></span>  
 <span data-ttu-id="58d6a-125">Durante la registrazione del [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Server registrati**, scegliere questa opzione per verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="58d6a-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="58d6a-126">**Salva**</span><span class="sxs-lookup"><span data-stu-id="58d6a-126">**Save**</span></span>  
 <span data-ttu-id="58d6a-127">Consente di salvare le impostazioni in **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="58d6a-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
