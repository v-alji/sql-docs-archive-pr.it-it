---
title: 'Passaggio 2: Conversione del progetto nel modello di distribuzione del progetto | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624813"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="4ea32-102">Passaggio 2: Conversione del progetto nel modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="4ea32-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="4ea32-103">In questa attività verrà usata la Conversione guidata progetto di Integration Services per convertire il progetto nel modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea32-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="4ea32-104">Conversione del progetto nel modello di distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="4ea32-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="4ea32-105">Scegliere Converti nel modello di distribuzione del progetto dal menu Progetto.</span><span class="sxs-lookup"><span data-stu-id="4ea32-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="4ea32-106">Nella pagina introduttiva della Conversione guidata progetto di Integration Services verificare i passaggi e quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="4ea32-107">Nella pagina Seleziona pacchetti deselezionare nell'elenco Pacchetti tutte le caselle di controllo, ad eccezione di Lesson 6.dtsx, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="4ea32-108">Nella pagina Specifica proprietà del progetto fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="4ea32-109">Nella pagina Aggiorna attività Esegui pacchetto fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="4ea32-110">Nella pagina Seleziona configurazioni assicurarsi che sia selezionato il pacchetto Lesson 6.dtsx nell'elenco Configurazioni e quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="4ea32-111">Nella pagina Crea parametri assicurarsi che sia selezionato il pacchetto Lesson 6.dtsx e che Ambito sia impostato su Pacchetto nell'elenco Proprietà di configurazione, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="4ea32-112">Nella pagina Configura parametri verificare che i valori per Nome e Valore corrispondano al nome e al valore specificato nella lezione 5 per i valori relativi a variabile e configurazione, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="4ea32-113">Nel riquadro Riepilogo della pagina Verifica si noti che la procedura guidata ha usato le informazioni disponibili nel file di configurazione per impostare le proprietà da convertire.</span><span class="sxs-lookup"><span data-stu-id="4ea32-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="4ea32-114">Fare clic su Converti.</span><span class="sxs-lookup"><span data-stu-id="4ea32-114">Click Convert.</span></span>  
  
     <span data-ttu-id="4ea32-115">Al termine della conversione, viene visualizzato un messaggio di avviso che indica che le modifiche verranno salvate solo dopo il salvataggio del progetto in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ea32-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="4ea32-116">Fare clic su OK nella finestra di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="4ea32-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="4ea32-117">Nella Conversione guidata progetto di Integration Services fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="4ea32-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="4ea32-118">In SQL Server Data Tools scegliere Salva dal menu File per salvare il pacchetto convertito.</span><span class="sxs-lookup"><span data-stu-id="4ea32-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="4ea32-119">Fare clic sulla scheda Parametri e verificare che il pacchetto includa un parametro per VarFolderName e che il valore corrisponda al percorso specificato per la cartella New Sample Data del file di configurazione della lezione 5.</span><span class="sxs-lookup"><span data-stu-id="4ea32-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4ea32-120">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4ea32-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4ea32-121">Passaggio 3: Test del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="4ea32-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
