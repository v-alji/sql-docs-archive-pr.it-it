---
title: Firma di un pacchetto tramite un certificato digitale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726039"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="01c66-102">Firma di un pacchetto tramite certificato digitale</span><span class="sxs-lookup"><span data-stu-id="01c66-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="01c66-103">Questo argomento illustra come firmare un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con un certificato digitale.</span><span class="sxs-lookup"><span data-stu-id="01c66-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="01c66-104">È possibile utilizzare una firma digitale, insieme ad altre impostazioni, per evitare il caricamento e l'esecuzione di pacchetti non validi.</span><span class="sxs-lookup"><span data-stu-id="01c66-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="01c66-105">Prima di poter firmare un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , è necessario effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="01c66-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="01c66-106">Creare o ottenere una chiave privata da associare al certificato e archiviarla nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="01c66-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="01c66-107">Ottenere un certificato a scopo di firma del codice da un'autorità di certificazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="01c66-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="01c66-108">Per ottenere o creare un certificato, è possibile utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="01c66-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="01c66-109">Ottenere un certificato da un'autorità di certificazione commerciale pubblica che emette certificati.</span><span class="sxs-lookup"><span data-stu-id="01c66-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="01c66-110">Ottenere un certificato da un server dei certificati che consente alle organizzazioni di emettere certificati internamente.</span><span class="sxs-lookup"><span data-stu-id="01c66-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="01c66-111">È necessario aggiungere il certificato radice usato per firmare il certificato nell'archivio **Autorità di certificazione radice disponibili nell'elenco locale** .</span><span class="sxs-lookup"><span data-stu-id="01c66-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="01c66-112">Per aggiungere il certificato radice, è possibile utilizzare lo snap-in Certificati per [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="01c66-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="01c66-113">Per altre informazioni, vedere l'argomento "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)" (Servizi certificati) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="01c66-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="01c66-114">Creare un certificato solo a scopo di testing.</span><span class="sxs-lookup"><span data-stu-id="01c66-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="01c66-115">Lo strumento di creazione certificati (Makecert.exe) genera certificati X.509 solo a scopo di testing.</span><span class="sxs-lookup"><span data-stu-id="01c66-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="01c66-116">Per altre informazioni, vedere l'argomento "[Strumento di creazione certificati (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)" in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="01c66-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="01c66-117">Per ulteriori informazioni sui certificati, vedere la Guida relativa allo snap-in Certificati.</span><span class="sxs-lookup"><span data-stu-id="01c66-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="01c66-118">Per altre informazioni sulla firma di risorse digitali, vedere l'argomento "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)" (Firma e verifica del codice con Authenticode) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="01c66-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="01c66-119">Verificare che il certificato sia stato abilitato per la firma di codice.</span><span class="sxs-lookup"><span data-stu-id="01c66-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="01c66-120">Per determinare se un certificato è abilitato per la firma di codice, controllare le proprietà del certificato nello snap-in Certificati.</span><span class="sxs-lookup"><span data-stu-id="01c66-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="01c66-121">Archiviare il certificato nell'archivio personale.</span><span class="sxs-lookup"><span data-stu-id="01c66-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="01c66-122">Dopo avere completato le attività precedenti, è possibile utilizzare la procedura descritta di seguito per firmare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="01c66-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="01c66-123">Per firmare un pacchetto</span><span class="sxs-lookup"><span data-stu-id="01c66-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="01c66-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto da firmare.</span><span class="sxs-lookup"><span data-stu-id="01c66-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="01c66-125">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="01c66-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="01c66-126">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] scegliere **Firma digitale** dl menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="01c66-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="01c66-127">Nella finestra di dialogo **Firma digitale** fare clic su **Firma**.</span><span class="sxs-lookup"><span data-stu-id="01c66-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="01c66-128">Nella finestra di dialogo **Seleziona certificato** selezionare un certificato.</span><span class="sxs-lookup"><span data-stu-id="01c66-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="01c66-129">(Facoltativo) Fare clic su **Visualizza certificato**per visualizzare informazioni sul certificato.</span><span class="sxs-lookup"><span data-stu-id="01c66-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="01c66-130">Fare clic su **OK** per chiudere la finestra di dialogo **Seleziona certificato** .</span><span class="sxs-lookup"><span data-stu-id="01c66-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="01c66-131">Fare clic su **OK** per chiudere la finestra di dialogo **Firma digitale** .</span><span class="sxs-lookup"><span data-stu-id="01c66-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="01c66-132">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="01c66-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="01c66-133">Anche se il pacchetto è stato firmato, è necessario configurare [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per controllare o verificare la firma digitale prima del caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="01c66-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="01c66-134">Per altre informazioni, vedere [Identificazione dell'origine dei pacchetti con firme digitali](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="01c66-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c66-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01c66-135">See Also</span></span>  
 [<span data-ttu-id="01c66-136">Panoramica sulla sicurezza &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="01c66-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
