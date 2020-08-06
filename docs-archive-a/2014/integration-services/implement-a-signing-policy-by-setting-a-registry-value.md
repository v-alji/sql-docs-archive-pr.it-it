---
title: Implementare i criteri di firma impostando un valore del registro di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624828"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="5c4ea-102">Implementazione di criteri per le firme impostando un valore del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="5c4ea-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="5c4ea-103">È possibile utilizzare un valore facoltativo del Registro di sistema per gestire i criteri dell'organizzazione per il caricamento dei pacchetti firmati o non firmati.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="5c4ea-104">Se si utilizza questo valore del Registro di sistema, è necessario crearlo in ogni computer in cui verranno eseguiti i pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e in cui si desidera applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="5c4ea-105">Dopo l'impostazione del valore del Registro di sistema, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] controllerà o verificherà le firme prima di caricare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="5c4ea-106">Nella procedura di questo argomento viene descritto come aggiungere il valore facoltativo DWORD `BlockedSignatureStates` alla chiave del Registro di sistema HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="5c4ea-107">Il valore di dati di `BlockedSignatureStates` determina se un pacchetto deve essere bloccato se è dotato di firma non attendibile o non valida oppure non è firmato.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="5c4ea-108">In relazione allo stato delle firme utilizzate per firmare pacchetti, il valore del Registro di sistema `BlockedSignatureStates` utilizza le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c4ea-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="5c4ea-109">Per *firma valida* si intende una firma che può essere letta.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="5c4ea-110">Per *firma non valida* si intende una firma il cui checksum decrittografato, ovvero l'hash unidirezionale del codice del pacchetto crittografato mediante una chiave privata, non corrisponde al checksum decrittografato calcolato nell'ambito del processo di caricamento dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c4ea-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="5c4ea-111">Per *firma attendibile* si intende una firma creata tramite un certificato digitale firmato da un'autorità di certificazione radice attendibile.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="5c4ea-112">Con questa impostazione non è necessario che il firmatario sia contenuto nell'elenco degli autori attendibili.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="5c4ea-113">Per *firma non attendibile* si intende una firma che non può essere verificata in riferimento al rilascio da parte di un'autorità di certificazione radice attendibile o una firma non corrente.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="5c4ea-114">Nella tabella seguente sono elencati i valori validi dei dati DWORD e i criteri associati.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="5c4ea-115">Valore</span><span class="sxs-lookup"><span data-stu-id="5c4ea-115">Value</span></span>|<span data-ttu-id="5c4ea-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c4ea-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c4ea-117">0</span><span class="sxs-lookup"><span data-stu-id="5c4ea-117">0</span></span>|<span data-ttu-id="5c4ea-118">Nessuna restrizione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="5c4ea-119">1</span><span class="sxs-lookup"><span data-stu-id="5c4ea-119">1</span></span>|<span data-ttu-id="5c4ea-120">Blocco delle firme non valide.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="5c4ea-121">Con questa impostazione non vengono bloccati i pacchetti non firmati.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="5c4ea-122">2</span><span class="sxs-lookup"><span data-stu-id="5c4ea-122">2</span></span>|<span data-ttu-id="5c4ea-123">Blocco delle firme non valide e non attendibili.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="5c4ea-124">Con questa impostazione non vengono bloccati i pacchetti non firmati, ma vengono bloccate le firme a generazione automatica.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="5c4ea-125">3</span><span class="sxs-lookup"><span data-stu-id="5c4ea-125">3</span></span>|<span data-ttu-id="5c4ea-126">Blocco delle firme non valide e non attendibili e dei pacchetti non firmati</span><span class="sxs-lookup"><span data-stu-id="5c4ea-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="5c4ea-127">Con questa impostazione vengono bloccate anche le firme a generazione automatica.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5c4ea-128">L'impostazione consigliata per `BlockedSignatureStates` è 3.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="5c4ea-129">Questa impostazione garantisce la massima protezione da pacchetti non firmati o firme non valide o non attendibili,</span><span class="sxs-lookup"><span data-stu-id="5c4ea-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="5c4ea-130">ma potrebbe non essere appropriata per tutte le circostanze.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="5c4ea-131">Per altre informazioni su come firmare elementi digitali, vedere l'argomento "[Introduzione alla firma di codice](https://go.microsoft.com/fwlink/?LinkId=51414)" in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="5c4ea-132">Per implementare criteri per le firme per i pacchetti</span><span class="sxs-lookup"><span data-stu-id="5c4ea-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="5c4ea-133">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5c4ea-134">Nella finestra di dialogo Esegui digitare `Regedit` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5c4ea-135">Individuare la chiave del Registro di sistema: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS</span><span class="sxs-lookup"><span data-stu-id="5c4ea-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="5c4ea-136">Fare clic con il pulsante destro del mouse su **MSDTS**, scegliere **Nuovo**e quindi **Valore DWORD**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="5c4ea-137">Aggiornare il nome del nuovo valore impostandolo su `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="5c4ea-138">Fare clic con il pulsante destro del mouse `BlockedSignatureStates` e scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="5c4ea-139">Nella finestra di dialogo **Modifica valore DWORD** digitare il valore 0, 1, 2 o 3.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="5c4ea-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="5c4ea-141">Scegliere **Esci** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="5c4ea-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4ea-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c4ea-142">See Also</span></span>  
 <span data-ttu-id="5c4ea-143">[Panoramica della sicurezza &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="5c4ea-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="5c4ea-144">Identificazione dell'origine dei pacchetti con firme digitali</span><span class="sxs-lookup"><span data-stu-id="5c4ea-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
