---
title: Testare le autorizzazioni di un utente (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629453"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="30a5e-102">Testare le autorizzazioni di un utente (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="30a5e-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="30a5e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile creare un utente test e accedere all'applicazione Web per testare le autorizzazioni, Quando un utente tenta di accedere all'URL di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , le credenziali dell'utente vengono autenticate.</span><span class="sxs-lookup"><span data-stu-id="30a5e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="30a5e-104">In Internet Explorer le impostazioni di sicurezza controllano se l'autenticazione viene eseguita automaticamente o se l'utente deve immettere nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="30a5e-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="30a5e-105">Per modificare queste impostazioni, effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a5e-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="30a5e-106">Per testare la sicurezza di un utente</span><span class="sxs-lookup"><span data-stu-id="30a5e-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="30a5e-107">In Internet Explorer 7 o versione successiva scegliere **Opzioni Internet**dal menu **Strumenti**, quindi fare clic sulla scheda **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="30a5e-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="30a5e-108">Fare clic su **Intranet locale** e quindi sul pulsante **Livello personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="30a5e-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="30a5e-109">Nella sezione **Autenticazione utente** scegliere **Richiedi nome utente e password**.</span><span class="sxs-lookup"><span data-stu-id="30a5e-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="30a5e-110">Alla successiva apertura della finestra del browser, verrà richiesto di immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="30a5e-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a5e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30a5e-111">See Also</span></span>  
 [<span data-ttu-id="30a5e-112">Sicurezza &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="30a5e-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
