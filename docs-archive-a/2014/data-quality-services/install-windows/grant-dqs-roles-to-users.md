---
title: Concedere ruoli DQS agli utenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721756"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="a965a-102">Concedere ruoli DQS agli utenti</span><span class="sxs-lookup"><span data-stu-id="a965a-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="a965a-103">In questo argomento si descrive come creare account di accesso SQL in un'entità di Windows e come assegnare i ruoli [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="a965a-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a965a-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a965a-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="a965a-105">È necessario aver completato l'installazione di [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] tramite l'esecuzione del file DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="a965a-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="a965a-106">Per altre informazioni, vedere [Eseguire DQSInstaller.exe per completare l'installazione del server DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="a965a-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="a965a-107">L'account utente di Windows deve essere un membro del ruolo predefinito del server appropriato, ad esempio securityadmin, serveradmin o sysadmin, per creare account di accesso SQL e assegnare loro ruoli DQS.</span><span class="sxs-lookup"><span data-stu-id="a965a-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="a965a-108">Per creare account di accesso SQL e concedere ruoli DQS</span><span class="sxs-lookup"><span data-stu-id="a965a-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="a965a-109">Avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a965a-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="a965a-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]espandere l'istanza di SQL Server, quindi espandere **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="a965a-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="a965a-111">Fare clic con il pulsante destro del mouse sulla cartella **Sicurezza** scegliere **Nuovo**, quindi selezionare **Account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="a965a-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="a965a-112">Nella casella **Nome account di accesso** della finestra di dialogo **Account di accesso - Nuovo** specificare il nome di un utente di Windows, il tipo di autenticazione come **Autenticazione di Windows**e fare clic su **Cerca** per convalidare l'utente.</span><span class="sxs-lookup"><span data-stu-id="a965a-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="a965a-113">Al termine della convalida dell'utente, nel riquadro sinistro fare clic su **Mapping utenti** .</span><span class="sxs-lookup"><span data-stu-id="a965a-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="a965a-114">Nel riquadro destro selezionare la casella di controllo sotto la colonna **Mappa** per il database **DQS_MAIN** , quindi selezionare la casella di controllo **dqs_administrator**, **dqs_kb_editor**o **dqs_kb_operator** nel riquadro **Appartenenza a ruoli del database per: DQS_MAIN** , a seconda del livello di accesso necessario all'utente.</span><span class="sxs-lookup"><span data-stu-id="a965a-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="a965a-115">Per informazioni su questi tre ruoli DQS, vedere [DQS Sicurezza](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="a965a-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="a965a-116">Nella finestra di dialogo **Account di accesso - Nuovo** fare clic su **OK** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a965a-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a965a-117">Se si concede il ruolo **dqs_administrator** a un utente, applicare le modifiche, quindi verificare di nuovo le autorizzazioni utente. Risulteranno selezionate anche le altre due caselle di controllo dei ruoli DQS, cioè**dq_kb_editor** e **dqs_kb_operator**.</span><span class="sxs-lookup"><span data-stu-id="a965a-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a965a-118">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a965a-118">Next Steps</span></span>  
 <span data-ttu-id="a965a-119">Provare ad accedere a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] utilizzando l'account utente di Windows per cui è stato appena creato un account di accesso SQL e a cui è stato concesso un ruolo DQS.</span><span class="sxs-lookup"><span data-stu-id="a965a-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a965a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a965a-120">See Also</span></span>  
 <span data-ttu-id="a965a-121">[Installare Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="a965a-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="a965a-122">Creare un account di accesso</span><span class="sxs-lookup"><span data-stu-id="a965a-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
