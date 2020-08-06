---
title: Gestione connessione di Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724055"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="949f0-102">Gestione connessioni di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="949f0-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="949f0-103">La **Gestione connessioni di Azure Data Lake Store** consente a un pacchetto SSIS di connettersi a un servizio di Azure Data Lake Store tramite due tipi di autenticazione: identità utente Azure AD e identità del servizio di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="949f0-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="949f0-104">Configurare la Gestione connessioni di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="949f0-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="949f0-105">Nella finestra di dialogo **Aggiungi gestione connessione SSIS** selezionare **AzureDataLake**e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="949f0-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="949f0-106">Nella finestra di dialogo dell'editor della Gestione connessioni di Azure Data Lake Store digitare l'URL host di Azure Data Lake Store nel campo **ADLS Host** (Host ADLS).</span><span class="sxs-lookup"><span data-stu-id="949f0-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="949f0-107">Ad esempio: https: \/ /test.azuredatalakestore.NET o test.azuredatalakestore.NET.</span><span class="sxs-lookup"><span data-stu-id="949f0-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="949f0-108">Scegliere il tipo di autenticazione corrispondente per accedere ai dati di Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="949f0-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="949f0-109">Se si seleziona l'opzione di autenticazione **Identità utente Azure AD** , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="949f0-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="949f0-110">Specificare i valori per i campi **Nome utente** e **Password** .</span><span class="sxs-lookup"><span data-stu-id="949f0-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="949f0-111">Fare clic su **Test connessione** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="949f0-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="949f0-112">Se l'utente e l'amministratore tenant non hanno mai consentito prima a SSIS di accedere ai dati di Azure Data Lake Store, è necessario fare clic sul pulsante **Accetta** per consentire a SSIS di accedere ai dati di Azure Data Lake Store nella finestra di pop up separata.</span><span class="sxs-lookup"><span data-stu-id="949f0-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="949f0-113">Per altre informazioni su questa esperienza di consenso, vedere [Integrazione di applicazioni con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="949f0-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="949f0-114">Per l'opzione di autenticazione Identità utente Azure AD, l'autenticazione a più fattori e account Microsoft NON è supportata.</span><span class="sxs-lookup"><span data-stu-id="949f0-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="949f0-115">Se si seleziona l'opzione di autenticazione **Identità del servizio di Azure AD** , eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="949f0-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="949f0-116">Creare un'applicazione e un'entità servizio di AAD che possano accedere alle risorse di Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="949f0-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="949f0-117">Assegnare le autorizzazioni corrispondenti all'applicazione AAD per accedere alle risorse di Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="949f0-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="949f0-118">Per altre informazioni su questa opzione di autenticazione, vedere [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal)(Usare il portale per creare applicazioni ed entità servizio di Active Directory che possano accedere alle risorse).</span><span class="sxs-lookup"><span data-stu-id="949f0-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="949f0-119">Specificare i valori per **ID client**, **Chiave privata** e **Nome del tenant** .</span><span class="sxs-lookup"><span data-stu-id="949f0-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="949f0-120">Fare clic su **Test connessione** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="949f0-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="949f0-121">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="949f0-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="949f0-122">È possibile visualizzare le proprietà del componente Gestione connessione create nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="949f0-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
