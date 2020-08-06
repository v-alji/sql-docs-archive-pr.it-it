---
title: Metodi per evitare le richieste non valide | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636553"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="228ae-102">Metodi per evitare le richieste non valide</span><span class="sxs-lookup"><span data-stu-id="228ae-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="228ae-103">È possibile impedire la generazione di alcuni tipi di eccezioni analizzando il flusso dell'applicazione e assicurandosi che le richieste inviate al server di report siano valide.</span><span class="sxs-lookup"><span data-stu-id="228ae-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="228ae-104">Nelle applicazioni che consentono agli utenti di aggiungere o aggiornare il nome di un report, un'origine dati o un altro elemento del server di report, è necessario convalidare il testo che un utente potrebbe immettere.</span><span class="sxs-lookup"><span data-stu-id="228ae-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="228ae-105">È sempre necessario verificare se sono presenti caratteri riservati prima di inviare la richiesta a un server di report.</span><span class="sxs-lookup"><span data-stu-id="228ae-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="228ae-106">Usare istruzioni **if** condizionali o altri costrutti logici nel codice per avvisare l'utente che non sono state soddisfatte le condizioni necessarie per l'invio delle richieste al server di report.</span><span class="sxs-lookup"><span data-stu-id="228ae-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="228ae-107">Nell'esempio C# semplificato seguente, gli utenti visualizzano ad esempio un messaggio di errore descrittivo quando tentano di creare un report con un nome che contiene una barra (/).</span><span class="sxs-lookup"><span data-stu-id="228ae-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="228ae-108">Per altre informazioni sui tipi di errore che è possibile prevenire prima dell'invio delle richieste al server di report, vedere [Tabella degli errori SoapException](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="228ae-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="228ae-109">Per altre informazioni su come migliorare ulteriormente l'esempio precedente usando blocchi try/catch, vedere [Uso di blocchi try e catch](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="228ae-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228ae-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="228ae-110">See Also</span></span>  
 <span data-ttu-id="228ae-111">[Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="228ae-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="228ae-112">Classe SoapException di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="228ae-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
