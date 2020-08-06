---
title: Pianificare l'aggiornamento dei dati e le origini dati che non supportano l'autenticazione di Windows (PowerPivot per SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629025"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="3d437-102">Pianificazione dell'aggiornamento dati e origini dati che non supportano l'autenticazione di Windows (PowerPivot per SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3d437-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="3d437-103">Questo argomento descrive un flusso di lavoro della pianificazione di un aggiornamento dati di PowerPivot per SharePoint in cui è possibile usare origini dati che **NON** supportano l'autenticazione di Windows,</span><span class="sxs-lookup"><span data-stu-id="3d437-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="3d437-104">ad esempio origini dati Oracle o IDM DB2.</span><span class="sxs-lookup"><span data-stu-id="3d437-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="3d437-105">Le illustrazioni e i passaggi presenti in questo argomento fanno riferimento alle origini dati Oracle ma lo stesso flusso di lavoro è valido anche per altre origini dati.</span><span class="sxs-lookup"><span data-stu-id="3d437-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3d437-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="3d437-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="3d437-107">**Panoramica:** creare due applicazioni di destinazione dell'archiviazione sicura.</span><span class="sxs-lookup"><span data-stu-id="3d437-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="3d437-108">Configurare la prima applicazione di destinazione (PowerPivotDataRefresh) per l'utilizzo delle credenziali Windows.</span><span class="sxs-lookup"><span data-stu-id="3d437-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="3d437-109">Configurare la seconda applicazione di destinazione con le credenziali di un'origine dati che non supporta l'autenticazione di Windows, ad esempio un database Oracle.</span><span class="sxs-lookup"><span data-stu-id="3d437-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="3d437-110">La seconda applicazione di destinazione utilizza anche la prima applicazione di destinazione per l'account di aggiornamento dati automatico.</span><span class="sxs-lookup"><span data-stu-id="3d437-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="3d437-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="3d437-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="3d437-112">**(1) PowerPivotDatarefresh:** ID dell'applicazione di destinazione di archiviazione sicura impostato con l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3d437-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="3d437-113">**(2) OracleAuthentication:** ID dell'applicazione di destinazione di archiviazione sicura impostato con le credenziali Oracle.</span><span class="sxs-lookup"><span data-stu-id="3d437-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="3d437-114">**(3)** l'applicazione del servizio PowerPivot viene configurata per l'utilizzo dell'applicazione di destinazione "PowerPivotDataRefresh" per l' **account di aggiornamento dati automatico**.</span><span class="sxs-lookup"><span data-stu-id="3d437-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="3d437-115">**(4)** Cartella di lavoro PowerePivot con dati Oracle.</span><span class="sxs-lookup"><span data-stu-id="3d437-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="3d437-116">Le impostazioni di aggiornamento della cartella di lavoro specificano la connessione all'origine dati in modo da usare l'applicazione di destinazione **(2)** per le credenziali.</span><span class="sxs-lookup"><span data-stu-id="3d437-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d437-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3d437-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="3d437-118">Applicazione di servizio PowerPivot esistente</span><span class="sxs-lookup"><span data-stu-id="3d437-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="3d437-119">Applicazione del servizio di archiviazione sicura esistente</span><span class="sxs-lookup"><span data-stu-id="3d437-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="3d437-120">Cartella di lavoro di Excel con modello di dati PowerPivot esistente</span><span class="sxs-lookup"><span data-stu-id="3d437-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="3d437-121">Per creare un ID applicazione di destinazione che utilizza l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="3d437-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="3d437-122">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="3d437-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="3d437-123">Fare clic sul nome dell'applicazione del servizio di archiviazione sicura.</span><span class="sxs-lookup"><span data-stu-id="3d437-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="3d437-124">Nella pagina **Gestione** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3d437-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="3d437-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="3d437-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="3d437-126">Nella pagina **Crea nuova applicazione di destinazione dell'archiviazione sicura** configurare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d437-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="3d437-127">**ID applicazione di destinazione:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="3d437-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="3d437-128">**Nome visualizzato:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="3d437-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="3d437-129">**Posta elettronica contatto:** ?</span><span class="sxs-lookup"><span data-stu-id="3d437-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="3d437-130">**Tipo di applicazione di destinazione:** Gruppo.</span><span class="sxs-lookup"><span data-stu-id="3d437-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="3d437-131">**URL della pagina dell'applicazione di destinazione:** Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d437-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="3d437-132">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3d437-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3d437-133">Nella pagina Credenziali lasciare i due nomi di campo e tipi di campo predefiniti per **Nome utente Windows** e **Password Windows**.</span><span class="sxs-lookup"><span data-stu-id="3d437-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="3d437-134">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3d437-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="3d437-135">Nella pagina **Impostazioni di appartenenza** aggiungere almeno un **Amministratore dell'applicazione di destinazione** e quindi aggiungere i membri che richiedono l'accesso all'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d437-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="3d437-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3d437-137">Il nuovo ID applicazione di destinazione verrà aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="3d437-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="3d437-138">Selezionare l'ID applicazione di destinazione e fare clic su **Imposta credenziali**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="3d437-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="3d437-139">Digitare il Nome utente Windows e la Password Windows e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="3d437-140">Per creare un ID applicazione di destinazione che utilizza le credenziali Oracle</span><span class="sxs-lookup"><span data-stu-id="3d437-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="3d437-141">In Amministrazione centrale SharePoint fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="3d437-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="3d437-142">Fare clic sul nome dell'applicazione del servizio di archiviazione sicura.</span><span class="sxs-lookup"><span data-stu-id="3d437-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="3d437-143">Nella pagina **Gestisci** fare clic su **nuovo**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="3d437-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="3d437-144">Nella pagina **Crea nuova applicazione di destinazione dell'archiviazione sicura** configurare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d437-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="3d437-145">**ID applicazione di destinazione:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="3d437-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="3d437-146">**Nome visualizzato:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="3d437-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="3d437-147">**Posta elettronica contatto:** ?</span><span class="sxs-lookup"><span data-stu-id="3d437-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="3d437-148">**Tipo di applicazione di destinazione:** Gruppo.</span><span class="sxs-lookup"><span data-stu-id="3d437-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="3d437-149">**URL della pagina dell'applicazione di destinazione:** Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3d437-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="3d437-150">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3d437-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3d437-151">Nella pagina **credenziali** modificare il nome del primo campo in `Oracle User ID` e modificare il **tipo di campo** in `User Name` .</span><span class="sxs-lookup"><span data-stu-id="3d437-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="3d437-152">Modificare il secondo nome di campo in `Oracle Password` e il **tipo di campo** in `Password` .</span><span class="sxs-lookup"><span data-stu-id="3d437-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="3d437-153">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3d437-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="3d437-154">Nella pagina **Impostazioni di appartenenza** aggiungere almeno un **Amministratore dell'applicazione di destinazione** e quindi aggiungere i membri che richiedono l'accesso all'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d437-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="3d437-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3d437-156">Il nuovo ID applicazione di destinazione verrà aggiunto all'elenco.</span><span class="sxs-lookup"><span data-stu-id="3d437-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="3d437-157">Selezionare l'ID applicazione di destinazione e fare clic su **Imposta credenziali**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="3d437-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="3d437-158">Digitare l'ID utente Oracle e la Password Oracle e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="3d437-159">Per ulteriori informazioni, vedere la sezione "per creare un'applicazione di destinazione per l'autenticazione SQL Server" in [utilizzare l'archiviazione sicura con autenticazione SQL Server (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3d437-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="3d437-160">Per configurare l'applicazione di servizio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="3d437-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="3d437-161">In Amministrazione centrale SharePoint fare clic su Gestisci applicazioni di servizio.</span><span class="sxs-lookup"><span data-stu-id="3d437-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="3d437-162">Fare clic sul nome dell'applicazione di servizio PowerPivot, ad esempio "applicazione di servizio PowerPivot predefinita".</span><span class="sxs-lookup"><span data-stu-id="3d437-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="3d437-163">Fare clic su **Configura impostazioni dell'applicazione di servizio** nella sezione Azioni.</span><span class="sxs-lookup"><span data-stu-id="3d437-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="3d437-164">Nella sezione **aggiornamento dati** impostare **account di aggiornamento dati automatico PowerPivot**su `PowerPivotDataRefresh` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="3d437-165">![as_powerpivot_refresh_new_refresh_account](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_account")</span><span class="sxs-lookup"><span data-stu-id="3d437-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="3d437-166">Per configurare la cartella di lavoro</span><span class="sxs-lookup"><span data-stu-id="3d437-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="3d437-167">Individuare la cartella di lavoro nella raccolta PowerPivot e fare clic su **Gestisci aggiornamento dati**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span><span class="sxs-lookup"><span data-stu-id="3d437-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="3d437-168">Se viene visualizzata la pagina **Cronologia aggiornamento dati** , fare clic su **Configura pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="3d437-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="3d437-169">Fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="3d437-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="3d437-170">Fare clic su **Aggiorna anche appena possibile**.</span><span class="sxs-lookup"><span data-stu-id="3d437-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="3d437-171">Nella sezione **Credenziali** fare clic su **Utilizza l'account di aggiornamento dati configurato dall'amministratore**.</span><span class="sxs-lookup"><span data-stu-id="3d437-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="3d437-172">Deselezionare **Tutte le origini dati**.</span><span class="sxs-lookup"><span data-stu-id="3d437-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="3d437-173">Selezionare **Aggiorna** per l'origine dati che utilizza i dati Oracle.</span><span class="sxs-lookup"><span data-stu-id="3d437-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="3d437-174">Il nome dell'origine dati può essere modificato in Microsoft Excel nel menu **Dati**, **Connessioni**, **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="3d437-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="3d437-175">Nell'origine dati selezionare **Utilizza pianificazione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="3d437-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="3d437-176">Selezionare **Effettua la connessione utilizzando le credenziali salvate nel servizio di archiviazione sicura per accedere all'origine dati. Immettere l'ID usato per cercare le credenziali nella casella ID servizio di archiviazione sicura**.</span><span class="sxs-lookup"><span data-stu-id="3d437-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="3d437-177">Nella casella **ID:** Digitare `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="3d437-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="3d437-178">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d437-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="3d437-179">Se viene visualizzato un messaggio di errore simile al seguente: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span><span class="sxs-lookup"><span data-stu-id="3d437-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="3d437-180">Le due soluzioni comuni sono:</span><span class="sxs-lookup"><span data-stu-id="3d437-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="3d437-181">Verificare che l'ID applicazione di destinazione sia corretto.</span><span class="sxs-lookup"><span data-stu-id="3d437-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="3d437-182">Verificare di aver impostato le credenziali per l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d437-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="3d437-183">Per verificare l'aggiornamento dati con la nuova autenticazione</span><span class="sxs-lookup"><span data-stu-id="3d437-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="3d437-184">Quando si fa clic su **OK**, viene visualizzata la pagina **Cronologia aggiornamento** .</span><span class="sxs-lookup"><span data-stu-id="3d437-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="3d437-185">Nell'arco di pochi minuti verrà visualizzato un nuovo elemento nella cronologia di aggiornamento perché nei passaggi precedenti è stato selezionato **Aggiorna anche appena possibile**.</span><span class="sxs-lookup"><span data-stu-id="3d437-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="3d437-186">Il valore predefinito per il processo timer **Processo timer di aggiornamento dati PowerPivot** è di 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="3d437-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="3d437-187">Se non viene visualizzato un nuovo elemento nella cronologia di aggiornamento, attendere qualche minuto e aggiornare il browser.</span><span class="sxs-lookup"><span data-stu-id="3d437-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="3d437-188">Se il nuovo elemento continua a non essere visualizzato, verificare il valore corrente del processo timer.</span><span class="sxs-lookup"><span data-stu-id="3d437-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="3d437-189">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="3d437-189">More Information</span></span>  
  
-   <span data-ttu-id="3d437-190">[Configurare il servizio di archiviazione sicura in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="3d437-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="3d437-191">Vedere la sezione "aggiornamento dati pianificato" dell' [aggiornamento dati PowerPivot con SharePoint 2013 e SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="3d437-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
