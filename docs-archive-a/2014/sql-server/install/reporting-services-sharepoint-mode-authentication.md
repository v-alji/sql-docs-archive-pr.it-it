---
title: Autenticazione in modalità SharePoint di Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722252"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="f4d93-102">Autenticazione in modalità SharePoint di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f4d93-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="f4d93-103">Utilizzare la pagina **Autenticazione in modalità SharePoint di Reporting Services** dell'Installazione guidata di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per specificare le credenziali dell'account del servizio utilizzato nell'installazione attuale di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f4d93-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="f4d93-104">Le credenziali verranno utilizzate per creare un nuovo pool di applicazioni SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d93-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="f4d93-105">Verrà inoltre creata una nuova applicazione di servizi [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d93-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="f4d93-106">Il nome dell'applicazione conterrà il nome dell'istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="f4d93-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4d93-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f4d93-107">Options</span></span>  
  
-   <span data-ttu-id="f4d93-108">L'opzione **Nome account pool di applicazioni SSRS** è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f4d93-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="f4d93-109">Il valore viene automaticamente popolato con il valore attuale dall'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] esistente in fase di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f4d93-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="f4d93-110">L'opzione **Password account pool di applicazioni SSRS** verrà disabilitata se l'account del pool di applicazioni non richiede una password</span><span class="sxs-lookup"><span data-stu-id="f4d93-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="f4d93-111">Ad esempio, "NT Authority\NetworkService".</span><span class="sxs-lookup"><span data-stu-id="f4d93-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="f4d93-112">Se per l'account del pool di applicazioni è richiesta una password, digitare la password corretta per procedere con l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f4d93-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="f4d93-113">Per ulteriori informazioni, vedere [Upgrade and migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) ( https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="f4d93-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d93-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4d93-114">See Also</span></span>  
 [<span data-ttu-id="f4d93-115">Eseguire l'aggiornamento e la migrazione di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f4d93-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
