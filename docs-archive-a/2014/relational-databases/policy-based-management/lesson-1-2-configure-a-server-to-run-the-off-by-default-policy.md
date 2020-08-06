---
title: Configurare un server per l'esecuzione di criteri Disattivata per impostazione predefinita | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624673"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="34a00-102">Configurazione di un server per l'esecuzione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="34a00-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="34a00-103">Sono stati creati criteri denominati Disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="34a00-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="34a00-104">In questa attività si verificherà se il server è conforme ai requisiti di tali criteri.</span><span class="sxs-lookup"><span data-stu-id="34a00-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="34a00-105">Per eseguire i criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="34a00-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="34a00-106">In Esplora oggetti fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], scegliere **Criteri**e fare clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="34a00-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="34a00-107">Nella finestra di dialogo \*\*Valuta criteri[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile selezionare criteri da un'altra istanza di \*\* o da un file.</span><span class="sxs-lookup"><span data-stu-id="34a00-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="34a00-108">Per questo passaggio, lasciare l'opzione \*\*Origine[!INCLUDE[ssDE](../../includes/ssde-md.md)] impostata sull'istanza del \*\*.</span><span class="sxs-lookup"><span data-stu-id="34a00-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="34a00-109">Nella sezione **Criteri** selezionare i criteri **Off By Default** (Disattivata per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="34a00-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="34a00-110">Per determinare se il server è conforme ai criteri, fare clic su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="34a00-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="34a00-111">Nell'area \*\*Risultati[!INCLUDE[ssDE](../../includes/ssde-md.md)] verrà visualizzato un cerchio verde con un segno di spunta se il \*\* è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="34a00-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="34a00-112">Verrà visualizzato un cerchio rosso con una X se il [!INCLUDE[ssDE](../../includes/ssde-md.md)] non è conforme ai criteri.</span><span class="sxs-lookup"><span data-stu-id="34a00-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="34a00-113">Se si verifica un errore, nell'area **Dettagli di destinazione** verranno visualizzate informazioni aggiuntive nella colonna **Messaggio** .</span><span class="sxs-lookup"><span data-stu-id="34a00-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="34a00-114">Nella colonna **Messaggio** fare clic su **Visualizza** per visualizzare un report contenente i risultati della verifica per ogni proprietà facet controllata.</span><span class="sxs-lookup"><span data-stu-id="34a00-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="34a00-115">La descrizione dei criteri viene visualizzata nella parte inferiore della pagina. Nella sezione **Guida aggiuntiva** è incluso il collegamento ipertestuale configurato per i criteri.</span><span class="sxs-lookup"><span data-stu-id="34a00-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="34a00-116">Fare clic sul collegamento ipertestuale del messaggio per aprire la pagina Web specificata quando sono stati creat i criteri.</span><span class="sxs-lookup"><span data-stu-id="34a00-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="34a00-117">Chiudere il browser e la finestra di dialogo **Visualizzazione dettagliata risultati** .</span><span class="sxs-lookup"><span data-stu-id="34a00-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="34a00-118">Se il server non è conforme e si vuole disabilitare Posta elettronica database, fare clic su **Applica** nella pagina **Risultati valutazione** .</span><span class="sxs-lookup"><span data-stu-id="34a00-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="34a00-119">Chiudere le due finestre di dialogo **Visualizzazione dettagliata risultati** e **Valuta criteri** .</span><span class="sxs-lookup"><span data-stu-id="34a00-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="34a00-120">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="34a00-120">Next Lesson</span></span>  
 [<span data-ttu-id="34a00-121">Lezione 2: Creare e applicare criteri per gli standard di denominazione</span><span class="sxs-lookup"><span data-stu-id="34a00-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
