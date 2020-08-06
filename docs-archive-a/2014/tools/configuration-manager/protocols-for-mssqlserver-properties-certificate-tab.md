---
title: Proprietà - Protocolli per MSSQLSERVER (scheda Certificato) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722095"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="05884-102">Proprietà - Protocolli per MSSQLSERVER (scheda Certificato)</span><span class="sxs-lookup"><span data-stu-id="05884-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="05884-103">Usare la scheda **Certificato** della finestra di dialogo **Proprietà - Protocolli per MSSQLSERVER** per selezionare un certificato per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o visualizzare le proprietà di un certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="05884-104">Tutti i campi sono vuoti se non è selezionato alcun certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="05884-105">I certificati per gli utenti vengono archiviati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="05884-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="05884-106">Per caricare un certificato da utilizzare con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario eseguire Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con lo stesso account utente del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05884-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="05884-107">Intestazione di pagina</span><span class="sxs-lookup"><span data-stu-id="05884-107">Page Header</span></span>  
 <span data-ttu-id="05884-108">**Visualizza**</span><span class="sxs-lookup"><span data-stu-id="05884-108">**View**</span></span>  
 <span data-ttu-id="05884-109">Consente di accedere a ulteriori dettagli sul certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="05884-110">Non è disponibile se non è selezionato alcun certificato nella casella **Certificato** .</span><span class="sxs-lookup"><span data-stu-id="05884-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="05884-111">Per ulteriori informazioni sui dettagli dei certificati, vedere la documentazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="05884-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="05884-112">**Cancella**</span><span class="sxs-lookup"><span data-stu-id="05884-112">**Clear**</span></span>  
 <span data-ttu-id="05884-113">Rimuove la selezione dalla casella **Certificato** .</span><span class="sxs-lookup"><span data-stu-id="05884-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="05884-114">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="05884-114">**Certificate**</span></span>  
 <span data-ttu-id="05884-115">Nome del certificato come stabilito dal provider di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="05884-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="05884-116">Selezionare un certificato per visualizzarne i dettagli nella griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="05884-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="05884-117">Opzioni</span><span class="sxs-lookup"><span data-stu-id="05884-117">Options</span></span>  
 <span data-ttu-id="05884-118">Data scadenza</span><span class="sxs-lookup"><span data-stu-id="05884-118">Expiration Date</span></span>  
 <span data-ttu-id="05884-119">Data finale del periodo in cui il certificato è valido.</span><span class="sxs-lookup"><span data-stu-id="05884-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="05884-120">Nome descrittivo</span><span class="sxs-lookup"><span data-stu-id="05884-120">Friendly Name</span></span>  
 <span data-ttu-id="05884-121">Nome descrittivo o comune dell'individuo o dell'autorità di certificazione a cui viene rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="05884-122">Rilasciato da</span><span class="sxs-lookup"><span data-stu-id="05884-122">Issued By</span></span>  
 <span data-ttu-id="05884-123">Informazioni sull'autorità di certificazione che ha rilasciato il certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="05884-124">Rilasciato a</span><span class="sxs-lookup"><span data-stu-id="05884-124">Issued To</span></span>  
 <span data-ttu-id="05884-125">Informazioni sul destinatario del certificato.</span><span class="sxs-lookup"><span data-stu-id="05884-125">Information regarding the recipient of the certificate.</span></span>  
  
  
