---
title: Editor gestione connessione SMTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726028"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="5028a-102">Editor gestione connessione SMTP</span><span class="sxs-lookup"><span data-stu-id="5028a-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="5028a-103">Usare la finestra di dialogo **Editor gestione connessioni SMTP** per specificare un server SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="5028a-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="5028a-104">Per ulteriori informazioni sulla gestione connessioni SMTP, vedere [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5028a-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5028a-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5028a-105">Options</span></span>  
 <span data-ttu-id="5028a-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5028a-106">**Name**</span></span>  
 <span data-ttu-id="5028a-107">Consente di specificare un nome univoco per la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="5028a-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="5028a-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5028a-108">**Description**</span></span>  
 <span data-ttu-id="5028a-109">Consente di aggiungere una descrizione per la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="5028a-109">Describe the connection manager.</span></span> <span data-ttu-id="5028a-110">È consigliabile includere nella descrizione informazioni sugli scopi della gestione connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="5028a-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="5028a-111">**Server SMTP**</span><span class="sxs-lookup"><span data-stu-id="5028a-111">**SMTP server**</span></span>  
 <span data-ttu-id="5028a-112">Consente di specificare il nome del server SMTP.</span><span class="sxs-lookup"><span data-stu-id="5028a-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="5028a-113">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="5028a-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="5028a-114">Selezionare questa opzione per inviare la posta elettronica mediante un server SMTM che utilizza l'autenticazione di Windows per consentire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5028a-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5028a-115">La gestione connessione SMTP supporta solo l'autenticazione anonima e l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5028a-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="5028a-116">Non supporta l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="5028a-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5028a-117">Quando si utilizza Microsoft Exchange come server SMTP, potrebbe essere necessario impostare **utilizza autenticazione di Windows** su `True` .</span><span class="sxs-lookup"><span data-stu-id="5028a-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="5028a-118">È possibile configurare i server Exchange in modo da impedire le connessioni SMTP non autenticate.</span><span class="sxs-lookup"><span data-stu-id="5028a-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="5028a-119">**Attiva SSL (Secure Sockets Layer)**</span><span class="sxs-lookup"><span data-stu-id="5028a-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="5028a-120">Selezionare questa opzione per crittografare le comunicazioni mediante SSL (Secure Sockets Layer) durante l'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5028a-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5028a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5028a-121">See Also</span></span>  
 [<span data-ttu-id="5028a-122">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="5028a-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
