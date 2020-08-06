---
title: Aggiungere rientri | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630209"
---
# <a name="adding-indentation"></a><span data-ttu-id="a994b-102">Aggiunta dei rientri</span><span class="sxs-lookup"><span data-stu-id="a994b-102">Adding Indentation</span></span>
  <span data-ttu-id="a994b-103">L'editor di query consente di impostare un rientro per sezioni estese di codice con un singolo passaggio e di modificare l'ampiezza del rientro.</span><span class="sxs-lookup"><span data-stu-id="a994b-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="a994b-104">Aggiunta di un rientro al codice</span><span class="sxs-lookup"><span data-stu-id="a994b-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="a994b-105">Per aggiungere un rientro a più righe di codice</span><span class="sxs-lookup"><span data-stu-id="a994b-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="a994b-106">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a994b-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="a994b-107">Creare una seconda query per selezionare le colonne **BusinessEntityID**, FirstName, **MiddleName**e **LastName** dalla tabella **Person** dello schema **Person** .</span><span class="sxs-lookup"><span data-stu-id="a994b-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="a994b-108">Posizionare ogni colonna su una riga separata in modo che il codice abbia l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="a994b-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="a994b-109">Selezionare tutto il testo compreso tra `BusinessEntityID` e `LastName`.</span><span class="sxs-lookup"><span data-stu-id="a994b-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="a994b-110">Sulla barra degli strumenti **Editor SQL** fare clic su **Aumenta rientro** per aggiungere un rientro a tutte le righe contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a994b-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="a994b-111">Per modificare il rientro predefinito</span><span class="sxs-lookup"><span data-stu-id="a994b-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="a994b-112">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="a994b-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="a994b-113">Espandere **Editor di testo**, espandere **Tutti i linguaggi**e fare clic su **Tabulazioni** per impostare i valori del rientro nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="a994b-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="a994b-114">Si noti che è possibile modificare le dimensioni del rientro e delle tabulazioni e specificare se le tabulazioni vengono convertite in spazi.</span><span class="sxs-lookup"><span data-stu-id="a994b-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="a994b-115">![Aspetto della finestra di dialogo Schede](media/tabsdialog.gif "Aspetto della finestra di dialogo Schede")</span><span class="sxs-lookup"><span data-stu-id="a994b-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="a994b-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a994b-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a994b-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="a994b-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a994b-118">Ingrandimento dell'editor di query</span><span class="sxs-lookup"><span data-stu-id="a994b-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
