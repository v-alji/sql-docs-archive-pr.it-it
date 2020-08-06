---
title: Configurare un firewall per l'accesso FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- Windows Firewall [Database Engine], FILESTREAM
- FILESTREAM [SQL Server], Windows Firewall
ms.assetid: fc52007f-c26f-4f8e-b9d8-55a7978f4d56
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8b787403fefdd336dd82bf7ccb93cdf21fe5a90d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636235"
---
# <a name="configure-a-firewall-for-filestream-access"></a><span data-ttu-id="95f6a-102">Configurare un firewall per l'accesso FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="95f6a-102">Configure a Firewall for FILESTREAM Access</span></span>
  <span data-ttu-id="95f6a-103">Per utilizzare FILESTREAM in un ambiente protetto da firewall, il client e il serve devono essere entrambi in grado di risolvere nomi DNS nel server in cui sono presenti i file FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="95f6a-103">To use FILESTREAM in a firewall-protected environment, both the client and server must be able to resolve DNS names to the server that contains the FILESTREAM files.</span></span> <span data-ttu-id="95f6a-104">Per FILESTREAM è necessario che le porte 139 e 445 di condivisione file di Windows siano aperte.</span><span class="sxs-lookup"><span data-stu-id="95f6a-104">FILESTREAM requires the Windows file-sharing ports 139 and 445 to be open.</span></span>  
  
### <a name="to-open-the-windows-file-sharing-ports-on-a-computer-that-is-running-windows-7"></a><span data-ttu-id="95f6a-105">Per aprire le porte di condivisione file di Windows in un computer che esegue Windows 7</span><span class="sxs-lookup"><span data-stu-id="95f6a-105">To open the Windows file-sharing ports on a computer that is running Windows 7</span></span>  
  
1.  <span data-ttu-id="95f6a-106">Nel Pannello di controllo aprire **Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-106">In Control Panel, open **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="95f6a-107">Nel riquadro sinistro scegliere **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="95f6a-107">In the left pane, click **Advanced settings**.</span></span> <span data-ttu-id="95f6a-108">Se viene chiesto di immettere una password dell'amministratore o è richiesta una conferma, digitare la password o fornire la conferma.</span><span class="sxs-lookup"><span data-stu-id="95f6a-108">If you're prompted for an administrator password or confirmation, type the password or provide confirmation.</span></span>  
  
3.  <span data-ttu-id="95f6a-109">Nel riquadro sinistro della finestra di dialogo **Windows Firewall con sicurezza avanzata** fare clic su **Regole connessioni in entrata**, quindi scegliere **Nuova regola**nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="95f6a-109">In the **Windows Firewall with Advanced Security** dialog box, in the left pane, click **Inbound Rules**, and then, in the right pane, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="95f6a-110">Seguire le istruzioni della Creazione guidata nuova regola connessioni in entrata per aggiungere la porta TCP 139.</span><span class="sxs-lookup"><span data-stu-id="95f6a-110">Follow the instructions in the New Inbound Rule wizard to add TCP port 139.</span></span>  
  
5.  <span data-ttu-id="95f6a-111">Ripetere il passaggio precedente per aggiungere la porta TCP 445.</span><span class="sxs-lookup"><span data-stu-id="95f6a-111">Repeat the previous step to add TCP port 445.</span></span>  
  
6.  <span data-ttu-id="95f6a-112">Chiudere la finestra di dialogo **Windows Firewall con sicurezza avanzata** .</span><span class="sxs-lookup"><span data-stu-id="95f6a-112">Close the **Windows Firewall with Advanced Security** dialog box.</span></span>  
  
  
