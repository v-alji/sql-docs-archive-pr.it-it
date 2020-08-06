---
title: Omissione di valori per gli oggetti del servizio Web facoltativi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713815"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="bd16b-102">Omissione di valori per gli oggetti del servizio Web facoltativi</span><span class="sxs-lookup"><span data-stu-id="bd16b-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="bd16b-103">Alle proprietà di diversi tipi complessi del servizio Web ReportServer è associata una proprietà nota come proprietà Specified.</span><span class="sxs-lookup"><span data-stu-id="bd16b-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="bd16b-104">Il nome della proprietà è costituito dal nome della proprietà originale con l'aggiunta della parola "Specified".</span><span class="sxs-lookup"><span data-stu-id="bd16b-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="bd16b-105">La presenza di questa proprietà indica che, a volte, è possibile omettere un valore per la proprietà originale.</span><span class="sxs-lookup"><span data-stu-id="bd16b-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="bd16b-106">Si tratta di un risultato diretto della conversione da WSDL (Web Service Description Language) a una classe proxy [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd16b-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="bd16b-107">Ad esempio, alla proprietà del servizio Web <xref:ReportService2010.DataSourceDefinition.Enabled%2A> del tipo complesso <xref:ReportService2010.DataSourceDefinition> è associata una proprietà denominata <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd16b-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="bd16b-108">Se si compila un'applicazione e non si desidera impostare un valore per la proprietà <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, non è necessario fornire un valore per <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; verrà utilizzato il valore predefinito `true`.</span><span class="sxs-lookup"><span data-stu-id="bd16b-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="bd16b-109">È tuttavia necessario impostare ancora <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="bd16b-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="bd16b-110">Se si fornisce un valore per la proprietà <xref:ReportService2010.DataSourceDefinition.Enabled%2A>, è necessario impostare <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="bd16b-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="bd16b-111">È il caso delle proprietà scrivibili.</span><span class="sxs-lookup"><span data-stu-id="bd16b-111">This is the case for writable properties.</span></span> <span data-ttu-id="bd16b-112">Per le proprietà di sola lettura, non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="bd16b-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bd16b-113">La mancata definizione di una proprietà con la tecnica indicata in precedenza può causare un comportamento imprevedibile del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="bd16b-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="bd16b-114">I tipi di dati che in genere richiedono la gestione della proprietà specificata aggiuntiva sono `Boolean` , `DateTime` e `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="bd16b-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="bd16b-115">Per un esempio, vedere il metodo <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd16b-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd16b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd16b-116">See Also</span></span>  
 <span data-ttu-id="bd16b-117">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="bd16b-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="bd16b-118">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bd16b-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
