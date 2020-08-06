---
title: Uso dell'accesso con URL in un'applicazione Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719728"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="0c8aa-102">Utilizzo dell'accesso con URL in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="0c8aa-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="0c8aa-103">Sebbene l'accesso con URL a un server di report sia ottimizzato per un ambiente Web, è possibile utilizzarlo anche per incorporare i report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un'applicazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="0c8aa-104">Per l'accesso con URL che comporta l'utilizzo di Windows Form è tuttavia necessario utilizzare comunque la tecnologia del browser Web.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="0c8aa-105">È possibile utilizzare gli scenari di integrazione seguenti con l'accesso con URL e Windows Form:</span><span class="sxs-lookup"><span data-stu-id="0c8aa-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="0c8aa-106">Visualizzazione di un report da un'applicazione Windows Form avviando un browser a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="0c8aa-107">Utilizzo del controllo <xref:System.Windows.Forms.WebBrowser> in un Windows Form per visualizzare un report.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="0c8aa-108">Avvio di Internet Explorer da un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c8aa-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="0c8aa-109">È possibile utilizzare la classe <xref:System.Diagnostics.Process> per accedere a un processo in esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="0c8aa-110">La <xref:System.Diagnostics.Process> classe è un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] costrutto utile per avviare, arrestare, controllare e monitorare le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="0c8aa-111">Per visualizzare un report specifico nel database del server di report, è possibile avviare il processo **IExplore**, passando in URL al report.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="0c8aa-112">L'esempio di codice seguente può essere utilizzato per avviare [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer e passare un URL del report specifico quando l'utente fa clic su un pulsante in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="0c8aa-113">Incorporamento di un controllo browser in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c8aa-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="0c8aa-114">Se non si desidera visualizzare il report in un browser esterno, è possibile incorporare in modo semplice un browser come parte di un Windows Form utilizzando il controllo <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="0c8aa-115">Per aggiungere il controllo WebBrowser al Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c8aa-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="0c8aa-116">Creare una nuova applicazione Windows in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c8aa-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c8aa-117">Individuare il controllo <xref:System.Windows.Forms.WebBrowser> nella finestra di dialogo **Casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="0c8aa-118">Se la **casella degli strumenti** non è visibile, è possibile accedervi scegliendo **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="0c8aa-119">Trascinare il controllo <xref:System.Windows.Forms.WebBrowser> nell'area di progettazione di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="0c8aa-120">Il controllo <xref:System.Windows.Forms.WebBrowser> denominato webBrowser1 verrà aggiunto al modulo</span><span class="sxs-lookup"><span data-stu-id="0c8aa-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="0c8aa-121">Indirizzare il controllo <xref:System.Windows.Forms.WebBrowser> a un URL chiamando il relativo metodo **Navigate**.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="0c8aa-122">È possibile assegnare una stringa di accesso con URL specifica al controllo <xref:System.Windows.Forms.WebBrowser> in fase di esecuzione come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0c8aa-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c8aa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c8aa-123">See Also</span></span>  
 <span data-ttu-id="0c8aa-124">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0c8aa-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="0c8aa-125">[Integrazione di Reporting Services tramite l'accesso con URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="0c8aa-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="0c8aa-126">[Integrazione di Reporting Services tramite SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="0c8aa-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="0c8aa-127">[Integrazione di Reporting Services tramite i controlli ReportViewer](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="0c8aa-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="0c8aa-128">Accesso con URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0c8aa-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
