---
title: Accesso agli assembly personalizzati tramite espressioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623047"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="f1870-102">Accesso agli assembly personalizzati tramite espressioni</span><span class="sxs-lookup"><span data-stu-id="f1870-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="f1870-103">Dopo aver creato un assembly personalizzato, averlo reso disponibile in Progettazione report o nel server di report, aver aggiunto i criteri di sicurezza appropriati e aver aggiunto un riferimento all'assembly personalizzato nella definizione del report, è possibile accedere ai membri delle classi nell'assembly utilizzando le espressioni di report.</span><span class="sxs-lookup"><span data-stu-id="f1870-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="f1870-104">Per fare riferimento al codice personalizzato in un'espressione, è necessario chiamare il membro di una classe nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f1870-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="f1870-105">La modalità di esecuzione di tale operazione dipende dal tipo di metodo, ovvero statico o basato su istanze.</span><span class="sxs-lookup"><span data-stu-id="f1870-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="f1870-106">Chiamata a membri statici da un file di definizione del report</span><span class="sxs-lookup"><span data-stu-id="f1870-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="f1870-107">I membri statici appartengono alla classe o al tipo e non a un oggetto per il quale è stata creata un'istanza.</span><span class="sxs-lookup"><span data-stu-id="f1870-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="f1870-108">È possibile accedere a questi membri chiamandoli direttamente dalla classe.</span><span class="sxs-lookup"><span data-stu-id="f1870-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="f1870-109">È consigliabile utilizzare i membri statici per chiamare le funzioni personalizzate in un report ogni qualvolta è possibile, perché i membri statici offrono prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="f1870-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="f1870-110">Per chiamare un membro statico, è necessario farvi riferimento come espressione nel formato =*SpazioDeiNomi.Classe.Metodo*.</span><span class="sxs-lookup"><span data-stu-id="f1870-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="f1870-111">Per chiamare i membri statici</span><span class="sxs-lookup"><span data-stu-id="f1870-111">To call static members</span></span>  
  
-   <span data-ttu-id="f1870-112">Per chiamare un membro statico, impostare l'espressione in modo che corrisponda al nome completo del membro che include lo spazio dei nomi, il nome della classe e il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="f1870-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="f1870-113">Nell'esempio seguente viene chiamato il metodo **ToGBP**, che consente di convertire il valore del campo **StandardCost** da dollari a sterline e di visualizzarlo in un report:</span><span class="sxs-lookup"><span data-stu-id="f1870-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="f1870-114">Informazioni importanti relative alle proprietà e ai campi statici</span><span class="sxs-lookup"><span data-stu-id="f1870-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="f1870-115">Attualmente, tutti i report vengono eseguiti nello stesso dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1870-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="f1870-116">Questo significa che i report con dati statici specifici dell'utente espongono questi dati alle altre istanze dello stesso report.</span><span class="sxs-lookup"><span data-stu-id="f1870-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="f1870-117">In questo modo, i dati statici di un utente possono essere resi disponibili per tutti gli utenti che attualmente eseguono un report specifico.</span><span class="sxs-lookup"><span data-stu-id="f1870-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="f1870-118">Per questo motivo, è consigliabile non usare proprietà o campi statici negli assembly personalizzati o nell'elemento **Code**, ma usare invece proprietà o campi di istanza nei report.</span><span class="sxs-lookup"><span data-stu-id="f1870-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="f1870-119">I metodi statici possono comunque essere utilizzati, perché non comportano l'archiviazione dello stato o dei dati.</span><span class="sxs-lookup"><span data-stu-id="f1870-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="f1870-120">Chiamata a membri di istanza da un file di definizione del report</span><span class="sxs-lookup"><span data-stu-id="f1870-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="f1870-121">Se l'assembly personalizzato contiene membri di istanza a cui è necessario accedere in una definizione del report, è necessario aggiungere al report un nome di istanza per la classe.</span><span class="sxs-lookup"><span data-stu-id="f1870-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="f1870-122">È possibile aggiungere un nome di istanza per una classe usando la scheda **Codice** della finestra di dialogo **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="f1870-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="f1870-123">Per altre informazioni sull'aggiunta di istanze di classi a un report, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f1870-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="f1870-124">Per chiamare un membro statico, è necessario farvi riferimento come espressione che assume il formato = codice *. Nomeistanza. Method*.</span><span class="sxs-lookup"><span data-stu-id="f1870-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="f1870-125">Per chiamare i membri dell'istanza</span><span class="sxs-lookup"><span data-stu-id="f1870-125">To call instance members</span></span>  
  
-   <span data-ttu-id="f1870-126">Per chiamare un membro di istanza di un assembly personalizzato, è necessario fare riferimento alla parola chiave **Code** seguita dal nome dell'istanza e dal metodo.</span><span class="sxs-lookup"><span data-stu-id="f1870-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="f1870-127">Nell'esempio seguente viene chiamato il metodo di istanza **ToEUR**, che consente di convertire il valore del campo **StandardCost** da dollari a euro e di visualizzarlo in un report:</span><span class="sxs-lookup"><span data-stu-id="f1870-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f1870-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1870-128">See Also</span></span>  
 [<span data-ttu-id="f1870-129">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="f1870-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
