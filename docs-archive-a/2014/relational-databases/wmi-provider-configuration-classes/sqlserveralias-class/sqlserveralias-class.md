---
title: Classe SqlServerAlias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637680"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="13aa8-102">Classe SqlServerAlias</span><span class="sxs-lookup"><span data-stu-id="13aa8-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="13aa8-103">La [classe SqlServerAlias](sqlserveralias-class.md) rappresenta un alias di connessione al server.</span><span class="sxs-lookup"><span data-stu-id="13aa8-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="13aa8-104">È necessario un alias di connessione al server quando si verificano le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="13aa8-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="13aa8-105">Il client si connette a un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] su un trasporto di rete che non è il trasporto di rete predefinito.</span><span class="sxs-lookup"><span data-stu-id="13aa8-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="13aa8-106">L'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a cui è connesso il client è in attesa su una named pipe alternativa.</span><span class="sxs-lookup"><span data-stu-id="13aa8-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="13aa8-107">**Nota:** La [classe SqlServerAlias](sqlserveralias-class.md) eredita il `Put` Metodo dalla classe provider.</span><span class="sxs-lookup"><span data-stu-id="13aa8-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="13aa8-108">Tuttavia, non viene restituito alcun risultato come indicato dal metodo `Provider::Put`.</span><span class="sxs-lookup"><span data-stu-id="13aa8-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="13aa8-109">Per ulteriori informazioni, vedere la documentazione di WMI.</span><span class="sxs-lookup"><span data-stu-id="13aa8-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13aa8-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13aa8-110">See Also</span></span>  
 [<span data-ttu-id="13aa8-111">Configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="13aa8-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
