---
title: Connetti al server (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711023"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="74b63-102">Connetti al server (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="74b63-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="74b63-103">Usare questa finestra di dialogo per visualizzare o specificare le opzioni per la connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74b63-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="74b63-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="74b63-104">Options</span></span>  
 <span data-ttu-id="74b63-105">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="74b63-105">**Server type**</span></span>  
 <span data-ttu-id="74b63-106">Per la registrazione di un server da Esplora oggetti, selezionare il tipo di server a cui connettersi, ovvero [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services.</span><span class="sxs-lookup"><span data-stu-id="74b63-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="74b63-107">Nelle altre parti della finestra di dialogo vengono visualizzate solo le opzioni applicabili al tipo di server selezionato.</span><span class="sxs-lookup"><span data-stu-id="74b63-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="74b63-108">Durante la registrazione di un server da Server registrati, la casella **Tipo server** è di sola lettura e corrisponde al tipo di server visualizzato nel componente Server registrati.</span><span class="sxs-lookup"><span data-stu-id="74b63-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="74b63-109">Per registrare un tipo diverso di server, selezionare [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services nella barra degli strumenti Server registrati prima di avviare la registrazione di un nuovo server.</span><span class="sxs-lookup"><span data-stu-id="74b63-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="74b63-110">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="74b63-110">**Server name**</span></span>  
 <span data-ttu-id="74b63-111">Consente di selezionare l'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="74b63-111">Select the server instance to connect to.</span></span> <span data-ttu-id="74b63-112">Per impostazione predefinita verrà visualizzata l'ultima istanza del server a cui è stata effettuata la connessione.</span><span class="sxs-lookup"><span data-stu-id="74b63-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="74b63-113">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="74b63-113">**Authentication**</span></span>  
 <span data-ttu-id="74b63-114">La modalità di autenticazione supportata per la connessione a un'istanza di Analysis Services è l'autenticazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="74b63-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="74b63-115">**Modalità di autenticazione di Windows (Autenticazione di Windows)**</span><span class="sxs-lookup"><span data-stu-id="74b63-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="74b63-116">La modalità di **autenticazione di Windows** consente a un utente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="74b63-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="74b63-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="74b63-117">**User name**</span></span>  
 <span data-ttu-id="74b63-118">Questa opzione non è disponibile in questa versione.</span><span class="sxs-lookup"><span data-stu-id="74b63-118">This option is not available in this release.</span></span> <span data-ttu-id="74b63-119">Immettere il nome utente da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="74b63-119">Enter the user name to connect with.</span></span> <span data-ttu-id="74b63-120">Questa opzione è disponibile solo se si è scelto di utilizzare **l'autenticazione di Windows**per la connessione.</span><span class="sxs-lookup"><span data-stu-id="74b63-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="74b63-121">**Password**</span><span class="sxs-lookup"><span data-stu-id="74b63-121">**Password**</span></span>  
 <span data-ttu-id="74b63-122">Questa opzione non è disponibile in questa versione.</span><span class="sxs-lookup"><span data-stu-id="74b63-122">This option is not available in this release.</span></span> <span data-ttu-id="74b63-123">Immettere la password per l'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="74b63-123">Enter the password for the login.</span></span> <span data-ttu-id="74b63-124">Questa opzione è modificabile solo se si è scelto di utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione.</span><span class="sxs-lookup"><span data-stu-id="74b63-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="74b63-125">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="74b63-125">**Connect**</span></span>  
 <span data-ttu-id="74b63-126">Fare clic su questo pulsante per connettersi al server selezionato.</span><span class="sxs-lookup"><span data-stu-id="74b63-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="74b63-127">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="74b63-127">**Options**</span></span>  
 <span data-ttu-id="74b63-128">Fare clic su questo pulsante per visualizzare ulteriori opzioni per la connessione al server, come le opzioni per la registrazione di un server e la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="74b63-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
