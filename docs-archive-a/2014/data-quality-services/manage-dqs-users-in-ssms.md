---
title: Gestire gli utenti DQS in SSMS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636885"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="2700d-102">Gestione di utenti DQS in SSMS</span><span class="sxs-lookup"><span data-stu-id="2700d-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="2700d-103">In questo argomento viene descritto come creare utenti aggiuntivi nell'istanza di SQL Server utilizzando SQL Server Management Studio e come assegnare loro ruoli [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="2700d-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2700d-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2700d-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2700d-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2700d-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2700d-106">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2700d-106">Permissions</span></span>  
 <span data-ttu-id="2700d-107">L'account utente di Windows deve essere un membro del ruolo predefinito del server appropriato, ad esempio securityadmin, serveradmin o sysadmin, per creare account di accesso SQL e assegnare a questi i ruoli DQS appropriati.</span><span class="sxs-lookup"><span data-stu-id="2700d-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="2700d-108">Creazione di un account di accesso SQL e concessione del ruolo DQS</span><span class="sxs-lookup"><span data-stu-id="2700d-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="2700d-109">Avviare Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="2700d-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="2700d-110">In Microsoft SQL Server Management Studio espandere l'istanza di SQL Server, quindi espandere **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="2700d-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="2700d-111">Fare clic con il pulsante destro del mouse sulla cartella **Sicurezza** scegliere **Nuovo**, quindi selezionare **Account di accesso**.</span><span class="sxs-lookup"><span data-stu-id="2700d-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="2700d-112">Nella casella **Nome account di accesso** della finestra di dialogo **Account di accesso - Nuovo** specificare il nome di un utente di Windows, il tipo di autenticazione come **Autenticazione di Windows**e fare clic su **Cerca** per convalidare l'utente.</span><span class="sxs-lookup"><span data-stu-id="2700d-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2700d-113">DQS supporta sola l'autenticazione di Windows; l'autenticazione di SQL Server non è supportata.</span><span class="sxs-lookup"><span data-stu-id="2700d-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="2700d-114">Al termine della convalida dell'utente, nel riquadro sinistro fare clic su **Mapping utenti** .</span><span class="sxs-lookup"><span data-stu-id="2700d-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="2700d-115">Nel riquadro destro selezionare la casella di controllo sotto la colonna **Mappa** per il database **DQS_MAIN** , quindi selezionare la casella di controllo **dqs_administrator**, **dqs_kb_editor**o **dqs_kb_operator** nel riquadro **Appartenenza a ruoli del database per: DQS_MAIN** , a seconda del livello di accesso necessario all'utente.</span><span class="sxs-lookup"><span data-stu-id="2700d-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="2700d-116">Nella finestra di dialogo **Account di accesso - Nuovo** fare clic su **OK** per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2700d-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2700d-117">Se si concede il ruolo **dqs_administrator** a un utente, applicare le modifiche, quindi verificare di nuovo le autorizzazioni utente. Risulteranno selezionate anche le altre due caselle di controllo dei ruoli DQS, cioè**dq_kb_editor** e **dqs_kb_operator**.</span><span class="sxs-lookup"><span data-stu-id="2700d-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
