---
title: Creazione di un ruolo definito dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627318"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="6282f-102">Creazione di un ruolo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="6282f-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="6282f-103">Per creare un ruolo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="6282f-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="6282f-104">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6282f-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="6282f-105">Scegliere **Esplora oggetti** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="6282f-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="6282f-106">Nella barra degli strumenti di Esplora oggetti fare clic su **Connetti**e quindi su **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="6282f-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="6282f-107">Nella finestra di dialogo **Connetti al server** specificare un nome di server e selezionare una modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="6282f-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="6282f-108">Per specificare il server locale, è possibile digitare un punto (.), (locale) o `localhost`.</span><span class="sxs-lookup"><span data-stu-id="6282f-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="6282f-109">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="6282f-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="6282f-110">Espandere i nodi Database, Database di sistema, msdb, Sicurezza e Ruoli.</span><span class="sxs-lookup"><span data-stu-id="6282f-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="6282f-111">Nel nodo Ruoli fare clic con il pulsante destro del mouse su Ruoli del database e quindi scegliere **Nuovo ruolo del database**.</span><span class="sxs-lookup"><span data-stu-id="6282f-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="6282f-112">Nella pagina Generale specificare un nome. Facoltativamente specificare un proprietario e gli schemi di proprietà e aggiungere i membri del ruoli.</span><span class="sxs-lookup"><span data-stu-id="6282f-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="6282f-113">Facoltativamente, fare clic su **Autorizzazioni** e configurare le autorizzazioni per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6282f-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="6282f-114">Facoltativamente, fare clic su **Proprietà estese** e configurare le proprietà estese.</span><span class="sxs-lookup"><span data-stu-id="6282f-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="6282f-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6282f-115">Click **OK**.</span></span>  
  
  
