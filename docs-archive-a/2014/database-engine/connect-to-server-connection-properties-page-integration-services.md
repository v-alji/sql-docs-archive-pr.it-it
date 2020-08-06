---
title: Connetti al server (pagina Proprietà connessione) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724147"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="8ae18-102">Integration Services - Connetti al server (pagina Proprietà connessione)</span><span class="sxs-lookup"><span data-stu-id="8ae18-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="8ae18-103">Usare questa scheda per visualizzare o specificare le opzioni relative alla connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o alla registrazione di [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="8ae18-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="8ae18-104">Le opzioni**Connetti** e **Opzioni** vengono visualizzate in questa finestra di dialogo solamente durante la connessione.</span><span class="sxs-lookup"><span data-stu-id="8ae18-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="8ae18-105">Le opzioni**Test** e **Salva** vengono visualizzate in questa finestra di dialogo solamente durante la registrazione del [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ae18-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ae18-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8ae18-106">Options</span></span>  
 <span data-ttu-id="8ae18-107">**Numero della porta**</span><span class="sxs-lookup"><span data-stu-id="8ae18-107">**Port number**</span></span>  
 <span data-ttu-id="8ae18-108">Immettere il numero di porta utilizzata da [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ae18-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="8ae18-109">**Timeout della connessione**</span><span class="sxs-lookup"><span data-stu-id="8ae18-109">**Connection time-out**</span></span>  
 <span data-ttu-id="8ae18-110">Immettere il numero di secondi di attesa prima che venga stabilita una connessione prima del timeout. Il valore predefinito è 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="8ae18-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="8ae18-111">**Timeout esecuzione**</span><span class="sxs-lookup"><span data-stu-id="8ae18-111">**Execution time-out**</span></span>  
 <span data-ttu-id="8ae18-112">Immettere il numero massimo di secondi di attesa del completamento dell'esecuzione di un'attività nel server.</span><span class="sxs-lookup"><span data-stu-id="8ae18-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="8ae18-113">Il valore predefinito è zero secondi, che indica l'assenza di un timeout.</span><span class="sxs-lookup"><span data-stu-id="8ae18-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="8ae18-114">**Reimposta tutto**</span><span class="sxs-lookup"><span data-stu-id="8ae18-114">**Reset All**</span></span>  
 <span data-ttu-id="8ae18-115">Consente di sostituire i valori delle proprietà di connessione immessi manualmente con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8ae18-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="8ae18-116">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="8ae18-116">**Connect**</span></span>  
 <span data-ttu-id="8ae18-117">Consente di eseguire un tentativo di connessione con i valori elencati.</span><span class="sxs-lookup"><span data-stu-id="8ae18-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="8ae18-118">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="8ae18-118">**Options**</span></span>  
 <span data-ttu-id="8ae18-119">Fare clic su questo pulsante per modificare la finestra di dialogo e nascondere le opzioni aggiuntive per la connessione al server, ad esempio le opzioni per la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="8ae18-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="8ae18-120">**Test**</span><span class="sxs-lookup"><span data-stu-id="8ae18-120">**Test**</span></span>  
 <span data-ttu-id="8ae18-121">Durante la registrazione del [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Server registrati**, scegliere questa opzione per verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8ae18-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="8ae18-122">**Salva**</span><span class="sxs-lookup"><span data-stu-id="8ae18-122">**Save**</span></span>  
 <span data-ttu-id="8ae18-123">Consente di salvare le impostazioni in **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="8ae18-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
