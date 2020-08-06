---
title: Nuova registrazione o modifica registrazione server (scheda generale) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636868"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="22b62-102">Creazione o modifica della registrazione del server (scheda Generale) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="22b62-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="22b62-103">Utilizzare questa scheda per specificare le opzioni di registrazione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22b62-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="22b62-104">Per accedere a questa pagina, in Server registrati fare clic su **Integration Services** sulla barra degli strumenti **Server registrati** , fare clic con il pulsante destro del mouse su qualsiasi gruppo di server registrati, scegliere **Nuovo**e quindi fare clic su **Registrazione server**.</span><span class="sxs-lookup"><span data-stu-id="22b62-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="22b62-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="22b62-105">Options</span></span>  
 <span data-ttu-id="22b62-106">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="22b62-106">**Server type**</span></span>  
 <span data-ttu-id="22b62-107">Quando si registra un server da Server registrati, la casella **Tipo server** è di sola lettura e corrisponde al tipo di server visualizzato in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="22b62-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="22b62-108">Per registrare un tipo diverso di server, fare clic su **Motore di database**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition** o **Integration Services** sulla barra degli strumenti **Server registrati** prima di avviare la registrazione di un nuovo server.</span><span class="sxs-lookup"><span data-stu-id="22b62-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="22b62-109">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="22b62-109">**Server name**</span></span>  
 <span data-ttu-id="22b62-110">Consente di selezionare il server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="22b62-110">Select the server to which to connect.</span></span> <span data-ttu-id="22b62-111">Viene visualizzato per impostazione predefinita l'ultimo server a cui ci si è connessi.</span><span class="sxs-lookup"><span data-stu-id="22b62-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="22b62-112">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="22b62-112">**Authentication**</span></span>  
 <span data-ttu-id="22b62-113">La modalità di autenticazione di Windows consente all'utente di utilizzare un account utente di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows per la connessione.</span><span class="sxs-lookup"><span data-stu-id="22b62-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="22b62-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="22b62-114">**User name**</span></span>  
 <span data-ttu-id="22b62-115">Questa opzione non è disponibile in questa versione.</span><span class="sxs-lookup"><span data-stu-id="22b62-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="22b62-116">**Password**</span><span class="sxs-lookup"><span data-stu-id="22b62-116">**Password**</span></span>  
 <span data-ttu-id="22b62-117">Questa opzione non è disponibile in questa versione.</span><span class="sxs-lookup"><span data-stu-id="22b62-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="22b62-118">**Memorizza password**</span><span class="sxs-lookup"><span data-stu-id="22b62-118">**Remember password**</span></span>  
 <span data-ttu-id="22b62-119">Questa opzione non è disponibile in questa versione.</span><span class="sxs-lookup"><span data-stu-id="22b62-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="22b62-120">**Nome server registrato**</span><span class="sxs-lookup"><span data-stu-id="22b62-120">**Registered server name**</span></span>  
 <span data-ttu-id="22b62-121">Nome che si vuole visualizzare nel componente **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="22b62-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="22b62-122">Non è necessario che questo nome corrisponda a quello indicato nella casella **Nome server** .</span><span class="sxs-lookup"><span data-stu-id="22b62-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="22b62-123">**Descrizione server registrato**</span><span class="sxs-lookup"><span data-stu-id="22b62-123">**Registered server description**</span></span>  
 <span data-ttu-id="22b62-124">Consente di immettere una descrizione facoltativa del server.</span><span class="sxs-lookup"><span data-stu-id="22b62-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="22b62-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="22b62-125">**Test**</span></span>  
 <span data-ttu-id="22b62-126">Consente di testare la connessione al server selezionato in **Nome server**.</span><span class="sxs-lookup"><span data-stu-id="22b62-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="22b62-127">**Salva**</span><span class="sxs-lookup"><span data-stu-id="22b62-127">**Save**</span></span>  
 <span data-ttu-id="22b62-128">Fare clic su questo pulsante per salvare le impostazioni relative ai server registrati.</span><span class="sxs-lookup"><span data-stu-id="22b62-128">Click to save the Registered Servers settings.</span></span>  
  
  
