---
title: Acquisire i dati degli eventi per i trigger di accesso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
author: rothja
ms.author: jroth
ms.openlocfilehash: b11323702d7468d07783b4d1c763dba691479d9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637161"
---
# <a name="capture-logon-trigger-event-data"></a><span data-ttu-id="798ec-102">Acquisizione dei dati degli eventi per i trigger di accesso</span><span class="sxs-lookup"><span data-stu-id="798ec-102">Capture Logon Trigger Event Data</span></span>
  <span data-ttu-id="798ec-103">Per acquisire dati XML per gli eventi LOGON da utilizzare in trigger LOGON, è possibile utilizzare la funzione [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="798ec-103">To capture XML data about LOGON events for use inside logon triggers, use the [EVENTDATA](/sql/t-sql/functions/eventdata-transact-sql) function.</span></span> <span data-ttu-id="798ec-104">L'evento LOGON restituisce lo schema di dati di evento seguente:</span><span class="sxs-lookup"><span data-stu-id="798ec-104">The LOGON event returns the following event data schema:</span></span>  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 <span data-ttu-id="798ec-105">Contiene `LOGON`.</span><span class="sxs-lookup"><span data-stu-id="798ec-105">Contains `LOGON`.</span></span>  
  
 `<PostTime>`  
 <span data-ttu-id="798ec-106">Contiene l'ora in cui viene richiesta l'attivazione di una sessione.</span><span class="sxs-lookup"><span data-stu-id="798ec-106">Contains the time when a session is requested to be established.</span></span>  
  
 `<SID>`  
 <span data-ttu-id="798ec-107">Contiene il flusso binario codificato in base 64 dell'ID di sicurezza (SID) per il nome di account di accesso specificato.</span><span class="sxs-lookup"><span data-stu-id="798ec-107">Contains the base 64-encoded binary stream of the security identification number (SID) for the specified login name.</span></span>  
  
 `<ClientHost>`  
 <span data-ttu-id="798ec-108">Contiene il nome host del client da cui viene attivata la connessione.</span><span class="sxs-lookup"><span data-stu-id="798ec-108">Contains the host name of the client from where the connection is made.</span></span> <span data-ttu-id="798ec-109">Il valore è '`<local_machine>`' se il nome del client e del server coincidono.</span><span class="sxs-lookup"><span data-stu-id="798ec-109">The value is '`<local_machine>`' if the client and server name are the same.</span></span> <span data-ttu-id="798ec-110">In caso contrario, il valore corrisponde all'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="798ec-110">Otherwise, the value is the IP address of the client.</span></span>  
  
 `<IsPooled>`  
 <span data-ttu-id="798ec-111">Il valore è `1` se la connessione viene riutilizzata tramite pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="798ec-111">Is `1` if the connection is reused by using connection pooling.</span></span> <span data-ttu-id="798ec-112">In caso contrario, il valore è `0`.</span><span class="sxs-lookup"><span data-stu-id="798ec-112">Otherwise, the value is `0`.</span></span>  
  
  
