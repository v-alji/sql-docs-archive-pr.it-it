---
title: Inizializzazione di oggetti assembly personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628499"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="df0c2-102">Inizializzazione di oggetti assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="df0c2-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="df0c2-103">In alcuni casi, potrebbe essere necessario inizializzare valori di proprietà e campi nelle classi di assembly personalizzate quando si crea un'istanza di tali classi.</span><span class="sxs-lookup"><span data-stu-id="df0c2-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="df0c2-104">In genere, è necessario inizializzare le classi personalizzate con i valori disponibili nelle raccolte di oggetti globali del report.</span><span class="sxs-lookup"><span data-stu-id="df0c2-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="df0c2-105">A tale scopo, è possibile eseguire l'override del metodo **OnInit** dell'oggetto **Code** di un report.</span><span class="sxs-lookup"><span data-stu-id="df0c2-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="df0c2-106">Per accedere al metodo **OnInit**, usare l'elemento **Code** della definizione del report.</span><span class="sxs-lookup"><span data-stu-id="df0c2-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="df0c2-107">Per l'inizializzazione di valori di campo o proprietà delle classi in un assembly personalizzato da usare in un report sono disponibili due tecniche. È possibile dichiarare e creare una nuova istanza della classe tramite **OnInit** oppure è possibile chiamare un metodo disponibile pubblicamente tramite **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="df0c2-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="df0c2-108">Raccolte di oggetti globali e inizializzazione</span><span class="sxs-lookup"><span data-stu-id="df0c2-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="df0c2-109">Per l'inizializzazione delle variabili delle classi personalizzate sono disponibili diverse raccolte.</span><span class="sxs-lookup"><span data-stu-id="df0c2-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="df0c2-110">È possibile usare le raccolte **Globals** e **User**.</span><span class="sxs-lookup"><span data-stu-id="df0c2-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="df0c2-111">Le raccolte **Parameters**, **Fields** e **ReportItems** non sono disponibili nel ciclo di vita del report durante il quale viene richiamato il metodo **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="df0c2-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="df0c2-112">Per usare le raccolte condivise **Globals** o **User**, è necessario includere il riferimento all'oggetto **Report**.</span><span class="sxs-lookup"><span data-stu-id="df0c2-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="df0c2-113">Ad esempio, per inizializzare la classe personalizzata in base alla lingua corrente dell'utente che accede al report, l'elemento **Code** può essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="df0c2-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="df0c2-114">Per inizializzare valori di proprietà e campi di una classe come illustrato in precedenza, è possibile dichiarare la classe e creare una nuova istanza chiamando un costruttore sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="df0c2-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="df0c2-115">In alternativa, per inizializzare i valori di proprietà e campi delle classi negli assembly personalizzati, è possibile chiamare un metodo disponibile pubblicamente definito dal metodo **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="df0c2-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="df0c2-116">È innanzitutto necessario aggiungere un nome di istanza per la classe nel file di definizione del report.</span><span class="sxs-lookup"><span data-stu-id="df0c2-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="df0c2-117">Dopo avere aggiunto il nome di istanza e il riferimento all'assembly appropriati, è possibile chiamare il metodo di inizializzazione per inizializzare i valori di proprietà e campi per la classe.</span><span class="sxs-lookup"><span data-stu-id="df0c2-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="df0c2-118">Il metodo **OnInit** può essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="df0c2-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="df0c2-119">Per altre informazioni sull'aggiunta di un riferimento all'assembly e di un nome di istanza per la classe personalizzata, vedere [Aggiungere un riferimento a un assembly in un report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="df0c2-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="df0c2-120">Per altre informazioni sulle raccolte di oggetti globali, vedere [Raccolte predefinite nelle espressioni &#40;Generatore report e SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="df0c2-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0c2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df0c2-121">See Also</span></span>  
 [<span data-ttu-id="df0c2-122">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="df0c2-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
