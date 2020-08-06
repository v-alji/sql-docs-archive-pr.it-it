---
title: Finestra di dialogo informazioni di rappresentazione (importazione guidata tabella) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712607"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a>Finestra di dialogo Impostazioni di rappresentazione (Importazione guidata tabella)
  Utilizzare la pagina **Impostazioni di rappresentazione** per specificare le credenziali che verranno utilizzate da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per la connessione all'origine dati. Per altre informazioni sulla rappresentazione delle credenziali, vedere [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).  
  
## <a name="options"></a>Opzioni  
 **Nome utente e password specifici di Windows**  
 Selezionare questa opzione per fare in modo che le credenziali di sicurezza di un account utente di Windows specificato vengano utilizzate dal modello tabulare.  
  
 **Nome utente**  
 Digitare il dominio e il nome dell'account utente da utilizzare Utilizzare il seguente formato:  
  
 *\<Domain name>* **\\** *\<User account name>*  
  
 Questa opzione è abilitata solo se si seleziona l'opzione **Usa nome utente e password specifici** .  
  
 **Password**  
 Digitare la password dell'account utente che verrà utilizzata dal modello tabulare.  
  
 Questa opzione è abilitata solo se si seleziona l'opzione **Usa nome utente e password specifici** .  
  
 **Account di servizio**  
 Selezionare questa opzione per usare le credenziali di sicurezza associate al servizio [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tramite cui viene gestito il modello.  
  
## <a name="see-also"></a>Vedere anche  
 [Rappresentazione &#40;SSAS tabulare&#41;](tabular-models/impersonation-ssas-tabular.md)  
  
  
