---
title: Ripristinare da PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723115"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="e360f-102">Ripristina da PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e360f-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="e360f-103">È possibile utilizzare la funzionalità Ripristina da PowerPivot in SQL Server Management Studio per creare un nuovo database modello tabulare in un'istanza di Analysis Services (in esecuzione in modalità tabulare) o eseguire il ripristino in un database esistente da una cartella di lavoro di PowerPivot (con estensione xlsx).</span><span class="sxs-lookup"><span data-stu-id="e360f-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e360f-104">Il modello di progetto Importa da PowerPivot in SQL Server Data Tools offre funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="e360f-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="e360f-105">Per ulteriori informazioni, vedere [importazione da PowerPivot &#40;SSAS tabulare&#41;](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e360f-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="e360f-106">Quando si utilizza Ripristina da PowerPivot, si tenga in considerazione quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e360f-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="e360f-107">Per poter utilizzare Ripristina da PowerPivot, è necessario aver eseguito l'accesso come membro del ruolo di amministratori del server per l'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e360f-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="e360f-108">L'account del servizio dell'istanza di Analysis Services deve disporre di autorizzazioni di lettura per il file della cartella di lavoro da cui eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="e360f-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="e360f-109">Per impostazione predefinita, quando si ripristina un database da PowerPivot, la proprietà Impostazioni di rappresentazione origine dati del database modello tabulare è impostata sul valore predefinito, tramite cui viene specificato l'account del servizio dell'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e360f-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="e360f-110">Si consiglia di impostare le credenziali di rappresentazione su un account utente di Windows nelle proprietà del database.</span><span class="sxs-lookup"><span data-stu-id="e360f-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="e360f-111">Per altre informazioni, vedere [Rappresentazione &#40;SSAS tabulare&#41;](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="e360f-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="e360f-112">I dati nel modello di dati PowerPivot verranno copiati in un nuovo database modello tabulare o in uno esistente nell'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e360f-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="e360f-113">Se nella cartella di lavoro di PowerPivot sono contenute tabelle collegate, queste verranno ricreate come tabelle senza un'origine dati, simili a tabelle create utilizzando Incolla in nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="e360f-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="e360f-114">Per ripristinare da PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e360f-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="e360f-115">In SSMS, nell'istanza Active Directory che si desidera ripristinare, fare clic con il pulsante destro del mouse su **database**, quindi scegliere **Ripristina da PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="e360f-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="e360f-116">Nella finestra di dialogo **Ripristina da PowerPivot** , in **origine ripristino**, in **file di backup**fare clic su **Sfoglia**, quindi selezionare un file con estensione abf o xslx da cui eseguire il ripristino.</span><span class="sxs-lookup"><span data-stu-id="e360f-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="e360f-117">In **Destinazione ripristino**in **Ripristina database**digitare un nome per un nuovo database o per uno esistente.</span><span class="sxs-lookup"><span data-stu-id="e360f-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="e360f-118">Se non si specifica un nome, viene utilizzato quello della cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e360f-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="e360f-119">In **Percorso di archiviazione**fare clic su **Sfoglia**, quindi selezionare un percorso per l'archiviazione del database.</span><span class="sxs-lookup"><span data-stu-id="e360f-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="e360f-120">Nella casella **Opzioni**lasciare **Includi informazioni di sicurezza** selezionato.</span><span class="sxs-lookup"><span data-stu-id="e360f-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="e360f-121">Quando si esegue il ripristino da una cartella di lavoro di PowerPivot, questa impostazione non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="e360f-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e360f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e360f-122">See Also</span></span>  
 <span data-ttu-id="e360f-123">[Database modello tabulare &#40;SSAS tabulare&#41;](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="e360f-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="e360f-124">Importazione da PowerPivot &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="e360f-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
