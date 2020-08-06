---
title: Raccolte di XML Schema di grandi dimensioni e condizioni di memoria insufficiente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726728"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="2dd18-102">Raccolte di XML Schema di grandi dimensioni e condizioni di memoria insufficiente</span><span class="sxs-lookup"><span data-stu-id="2dd18-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="2dd18-103">Durante una chiamata alla funzione incorporata XML_SCHEMA_NAMESPACE() in una raccolta XML Schema di grandi dimensioni o durante il tentativo di eliminare queste ultime, potrebbe verificarsi una condizione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="2dd18-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="2dd18-104">Per risolvere questo problema, è possibile utilizzare le soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2dd18-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="2dd18-105">Quando il carico di lavoro del sistema è ridotto, è consigliabile utilizzare il comando DROP_XML_SCHEMA_COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="2dd18-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="2dd18-106">Se tale tentativo ha esito negativo, configurare il database in modalità utente singolo mediante l'istruzione ALTER DATABASE e provare ad eseguire di nuovo il comando DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="2dd18-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="2dd18-107">Se la raccolta XML Schema è contenuta nel database **master**, **model**o **tempdb**, per attivare la modalità utente singolo è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="2dd18-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="2dd18-108">Quando si chiama la funzione XML_SCHEMA_NAMESPACE, è possibile provare a recuperare un singolo spazio dei nomi XML Schema ; provare a eseguire la chiamata quando diminuisce il carico di lavoro del sistema oppure provare ad eseguirla in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="2dd18-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd18-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dd18-109">See Also</span></span>  
 [<span data-ttu-id="2dd18-110">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="2dd18-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
