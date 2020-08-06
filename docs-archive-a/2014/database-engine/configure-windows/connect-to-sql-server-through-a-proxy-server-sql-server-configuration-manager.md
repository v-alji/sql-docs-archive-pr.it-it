---
title: Connettersi a SQL Server tramite un server proxy (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Remote WinSock
- RWS
- LATs
- proxy servers [SQL Server]
- connections [SQL Server], proxy server
- Microsoft Proxy Server [SQL Server]
- local address tables [SQL Server]
ms.assetid: 39714de0-2a1f-4179-9091-5c3fa4612545
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: de22ad6043c509f08471a6bea40c0efa18d76842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630032"
---
# <a name="connect-to-sql-server-through-a-proxy-server-sql-server-configuration-manager"></a><span data-ttu-id="4e23d-102">Connessione a SQL Server tramite un server proxy (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4e23d-102">Connect to SQL Server Through a Proxy Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="4e23d-103">In questo argomento viene illustrato come connettersi a SQL Server tramite un server proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e23d-103">This topic describes how to connect to SQL Server through a proxy server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="4e23d-104">Per l'attesa da postazioni remote tramite Remote WinSock (RWS), definire la tabella di indirizzi locali (LAT, Local Address Table) per il server proxy, in modo che l'indirizzo del nodo di attesa non sia compreso nell'intervallo degli indirizzi della tabella LAT.</span><span class="sxs-lookup"><span data-stu-id="4e23d-104">To listen remotely by way of Remote WinSock (RWS), define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4e23d-105">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e23d-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-connections-to-sql-server-through-microsoft-proxy-server"></a><span data-ttu-id="4e23d-106">Per consentire le connessioni a SQL Server tramite Microsoft Proxy Server</span><span class="sxs-lookup"><span data-stu-id="4e23d-106">To enable connections to SQL Server through Microsoft Proxy Server</span></span>  
  
1.  <span data-ttu-id="4e23d-107">Seguire i passaggi in [Configurazione di un server per l'attesa su una porta TCP specifica &#40;Gestione configurazione SQL Server&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) per determinare le porte TCP/IP usate dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] o per configurare il [!INCLUDE[ssDE](../../includes/ssde-md.md)] per l'uso della porta desiderata.</span><span class="sxs-lookup"><span data-stu-id="4e23d-107">Follow the steps in [Configure a Server to Listen on a Specific TCP Port &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) to determine which TCP/IP ports are used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to use a desired port.</span></span>  
  
2.  <span data-ttu-id="4e23d-108">Nel server proxy definire la tabella di indirizzi locali (LAT) per il server proxy, affinché l'indirizzo del nodo di attesa non sia compreso nell'intervallo delle voci della tabella LAT.</span><span class="sxs-lookup"><span data-stu-id="4e23d-108">In your proxy server define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span> <span data-ttu-id="4e23d-109">Per ulteriori informazioni, vedere la documentazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="4e23d-109">For more information, see your proxy server documentation.</span></span>  
  
  
