---
title: Informazioni sulle proprietà di OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714308"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="fbb34-102">Informazioni sulle proprietà OLE DB</span><span class="sxs-lookup"><span data-stu-id="fbb34-102">About OLE DB Properties</span></span>
  <span data-ttu-id="fbb34-103">I consumer impostano i valori delle proprietà per richiedere specifici comportamenti degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="fbb34-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="fbb34-104">Utilizzano, ad esempio, proprietà per specificare le interfacce che devono essere esposte da un set di righe.</span><span class="sxs-lookup"><span data-stu-id="fbb34-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="fbb34-105">I consumer recuperano i valori delle proprietà per determinare le funzionalità di un oggetto, ad esempio un set di righe, una sessione o un oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="fbb34-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="fbb34-106">Ogni proprietà presenta un valore, un tipo, una descrizione e un attributo di lettura/scrittura e, per le proprietà del set di righe, un indicatore che specifica se la proprietà può essere applicata alle singole colonne.</span><span class="sxs-lookup"><span data-stu-id="fbb34-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="fbb34-107">Una proprietà viene identificata da un GUID e da un numero intero che rappresenta l'ID della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="fbb34-108">Un set di proprietà è un set di tutte le proprietà che condividono lo stesso GUID.</span><span class="sxs-lookup"><span data-stu-id="fbb34-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="fbb34-109">Oltre ai set di proprietà predefiniti OLE DB, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client implementa set di proprietà e proprietà specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="fbb34-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="fbb34-110">Ogni proprietà appartiene a uno o più gruppi di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="fbb34-111">Un gruppo di proprietà è il gruppo di tutte le proprietà che si applicano a un particolare oggetto.</span><span class="sxs-lookup"><span data-stu-id="fbb34-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="fbb34-112">Alcuni gruppi di proprietà includono i seguenti gruppi di proprietà: di inizializzazione, dell'origine dati, di sessione, del set di righe, di tabella e di colonna.</span><span class="sxs-lookup"><span data-stu-id="fbb34-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="fbb34-113">In ognuno di questi gruppi sono presenti proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="fbb34-114">L'impostazione dei valori delle proprietà comporta:</span><span class="sxs-lookup"><span data-stu-id="fbb34-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="fbb34-115">Determinazione delle proprietà per le quali impostare i valori.</span><span class="sxs-lookup"><span data-stu-id="fbb34-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="fbb34-116">Determinazione dei set di proprietà che contengono le proprietà identificate.</span><span class="sxs-lookup"><span data-stu-id="fbb34-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="fbb34-117">Allocazione di una matrice di strutture DBPROPSET, una per ogni set di proprietà identificato.</span><span class="sxs-lookup"><span data-stu-id="fbb34-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="fbb34-118">Allocazione di una matrice di strutture DBPROP, una per ogni set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="fbb34-119">Il numero di elementi di ogni matrice è il numero di proprietà (identificate nel passaggio 1) che appartengono al set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="fbb34-120">Inserimento di dati nella struttura DBPROP per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="fbb34-121">Inserimento di informazioni (GUID del set di proprietà, conteggio del numero di elementi e un puntatore alla matrice DBPROP corrispondente) nella struttura DBPROPSET per ogni set di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fbb34-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="fbb34-122">Chiamata a un metodo per impostare proprietà e passaggio del conteggio e della matrice delle strutture DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="fbb34-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb34-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbb34-123">See Also</span></span>  
 <span data-ttu-id="fbb34-124">[Creazione di un'applicazione provider OLE DB SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="fbb34-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="fbb34-125">Proprietà (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="fbb34-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
