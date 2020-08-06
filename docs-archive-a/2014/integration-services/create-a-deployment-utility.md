---
title: Creare un'utilità di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- deploying packages [Integration Services], deployment utility
- deployment utility [Integration Services]
ms.assetid: 354322a4-ae8c-4d92-8e71-42d29dbd0614
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bdf1328d440920fed98e5fa1d16024c5fec32cbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629540"
---
# <a name="create-a-deployment-utility"></a>Creazione di un'utilità di distribuzione
  Il primo passaggio della distribuzione di pacchetti consiste nel creare un'utilità di distribuzione per un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . L'utilità di distribuzione è una cartella contenente i file necessari per la distribuzione dei pacchetti di un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in un altro server. L'utilità di distribuzione viene creata nel computer in cui è archiviato il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .  
  
 Per creare l'utilità di distribuzione di pacchetti per un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , è innanzitutto necessario configurare il processo di compilazione dell'utilità e quindi compilare il progetto. Quando si compila il progetto, tutti i pacchetti e le configurazioni di pacchetto del progetto vengono inclusi automaticamente. Per distribuire file aggiuntivi, ad esempio un file Leggimi per il progetto, è necessario inserirli nella cartella **Varie** del progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Quando si compila il progetto, vengono inclusi automaticamente anche questi file.  
  
 È possibile configurare ogni utilità di distribuzione di progetto in modo diverso. Prima di compilare il progetto e creare l'utilità di distribuzione dei pacchetti, è possibile impostare le proprietà dell'utilità in modo da personalizzare la modalità di distribuzione dei pacchetti. È possibile, ad esempio, specificare se le configurazioni di pacchetto possono essere aggiornate in fase di distribuzione del progetto. Per accedere alle proprietà di un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Proprietà**.  
  
 Nella tabella seguente vengono descritte le proprietà dell'utilità di distribuzione.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|AllowConfigurationChange|Valore che specifica se le configurazioni possono essere aggiornate durante la distribuzione.|  
|CreateDeploymentUtility|Valore che specifica se in fase di compilazione del progetto viene creata un'utilità di distribuzione di pacchetti. Per consentire la creazione di un'utilità di distribuzione, la proprietà deve essere impostata su `True`.|  
|DeploymentOutputPath|Posizione relativa al progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dell'utilità di distribuzione.|  
  
 Quando si compila un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], viene creato un file manifesto, \<project name>.SSISDeploymentManifest.xml, il quale viene aggiunto insieme a copie dei pacchetti di progetto e delle dipendenze di pacchetto nella cartella bin\Deployment del progetto o nel percorso specificato nella proprietà DeploymentOutputPath. Nel file manifesto sono elencati i pacchetti, le configurazioni di pacchetto ed eventuali altri file del progetto.  
  
 Il contenuto della cartella di distribuzione viene aggiornato ogni volta che si compila il progetto. Tutti i file eventualmente salvati in tale cartella e che non vengono nuovamente copiati nella cartella dal processo di compilazione verranno pertanto eliminati. Ad esempio, i file di configurazione del pacchetto salvati nelle cartelle di distribuzione verranno eliminati.  
  
### <a name="to-create-a-package-deployment-utility"></a>Per creare un'utilità di distribuzione di pacchetti  
  
1.  In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire la soluzione contenente il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per il quale si desidera creare un'utilità di distribuzione di pacchetti.  
  
2.  Fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Proprietà**.  
  
3.  Nella finestra di dialogo **Pagine delle proprietà di \<project name>** fare clic su **Utilità di distribuzione**.  
  
4.  Per aggiornare le configurazioni dei pacchetti durante la distribuzione dei pacchetti, impostare **AllowConfigurationChanges** su `True` .  
  
5.  Impostare `CreateDeploymentUtility` su `True`.  
  
6.  Facoltativamente, aggiornare la posizione dell'utilità di distribuzione modificando la proprietà `DeploymentOutputPath`.  
  
7.  Fare clic su **OK**.  
  
8.  In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Compila**.  
  
9. Nella finestra **Output** vengono visualizzati lo stato del processo di compilazione e gli eventuali errori di compilazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazioni di pacchetti](../../2014/integration-services/package-configurations.md)   
 [Creazione di configurazioni di pacchetto](../../2014/integration-services/create-package-configurations.md)   
 [Distribuire pacchetti con l'utilità di distribuzione](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md)   
 [Distribuzione di pacchetti &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md)  
  
  
