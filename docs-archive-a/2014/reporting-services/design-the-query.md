---
title: Progettare la query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719679"
---
# <a name="design-the-query"></a>Progettazione query
  Utilizzare questa pagina della Creazione guidata report per creare una query immettendola manualmente, utilizzando Generatore query per compilare una query in modo interattivo o importando la query da un altro report.  
  
 Il tipo di origine dati selezionato nella pagina Selezione origine dati, una pagina precedente della Creazione guidata report, determina la query che è possibile immettere in questa pagina. Se, ad esempio, il tipo di origine dati è [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è possibile immettere [!INCLUDE[tsql](../includes/tsql-md.md)] istruzioni o nomi di stored procedure. Se il tipo di origine dati è [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , il riquadro query è disabilitato e non è possibile immettere una query direttamente. È possibile specificare la query utilizzando Generatore di query.  
  
## <a name="options"></a>Opzioni  
 **Stringa di query**  
 Consente di digitare una query che recupera i dati da utilizzare nel report.  
  
 **Generatore di query**  
 Fare clic su **Generatore di query** per aprire una finestra Progettazione query per l'origine dati o importare una query da un altro report.  
  
 Per ulteriori informazioni sugli strumenti di progettazione query, vedere [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Esempio  
 Per il tipo di origine dati **Microsoft SQL Server**, la query seguente recupera un elenco di cognomi dalla [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tabella di database `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 Per il tipo di origine dati **Microsoft SQL Server**, la query seguente esegue il [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` per il dipendente con numero di identificazione 1:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Guida della creazione guidata report](../../2014/reporting-services/report-wizard-help.md)   
 [Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
