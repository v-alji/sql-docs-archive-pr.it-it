---
title: Rappresentazione di una connessione (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 4b410b16-d36e-4185-bb20-922e66e5e2b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 60f3fdc10baf5dc3be9cd1b0ee6196d2a8da3d2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626937"
---
# <a name="connection-representation-tabular"></a><span data-ttu-id="2e8e9-102">Rappresentazione di una connessione (tabulare)</span><span class="sxs-lookup"><span data-stu-id="2e8e9-102">Connection Representation (Tabular)</span></span>
  <span data-ttu-id="2e8e9-103">L'oggetto connessione definisce l'origine dei dati che popolano il modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-103">The connection object defines the source of the data that populates the tabular model.</span></span>  
  
## <a name="connection-representation"></a><span data-ttu-id="2e8e9-104">Rappresentazione di una connessione</span><span class="sxs-lookup"><span data-stu-id="2e8e9-104">Connection Representation</span></span>  
 <span data-ttu-id="2e8e9-105">La specifica dell'oggetto connessione segue le regole dei provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-105">The specification for the connection object follows the rules of OLE DB providers.</span></span>  
  
### <a name="connection-in-amo"></a><span data-ttu-id="2e8e9-106">Connessione in AMO</span><span class="sxs-lookup"><span data-stu-id="2e8e9-106">Connection in AMO</span></span>  
 <span data-ttu-id="2e8e9-107">Quando si utilizza AMO (Analysis Management Objects) per gestire un database modello tabulare, l'oggetto <xref:Microsoft.AnalysisServices.DataSource> ha una corrispondenza uno-a-uno in AMO (Analysis Management Objects) con l'oggetto logico di connessione.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-107">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.DataSource> object in AMO matches one-to-one to the connection logical object.</span></span>  
  
 <span data-ttu-id="2e8e9-108">Nel frammento di codice seguente viene mostrato come creare un'origine dati AMO o un oggetto Connection in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-108">The following code snippet shows how to create an AMO data source, or Connection object in a tabular model.</span></span>  
  
```  
  
//Create an OLEDB connection string  
StringBuilder SqlCnxStr = new StringBuilder();  
SqlCnxStr.Append(String.Format("Data Source={0};" ,SQLServer.Text));  
SqlCnxStr.Append(String.Format("Initial Catalog={0};", SQLDatabase.Text));  
SqlCnxStr.Append(String.Format("Persist Security Info={0};", false));  
SqlCnxStr.Append(String.Format("Integrated Security={0};", "SSPI"));  
SqlCnxStr.Append(String.Format("Provider={0}", "SQLNCLI11"));  
String DatasourceCnxString = SqlCnxStr.ToString();  
  
//Verify connection string and connectivity  
System.Data.OleDb.OleDbConnection OleDbCnx = new System.Data.OleDb.OleDbConnection(DatasourceCnxString);  
try  
{  
    OleDbCnx.Open();  
}  
catch ()  
{  
    throw;  
}  
String newDataSourceName = (string.IsNullOrEmpty(DataSourceName.Text) || string.IsNullOrWhiteSpace(DataSourceName.Text)) ? SQLDatabase.Text : DataSourceName.Text;  
AMO.DataSource newDatasource = newDatabase.DataSources.Add(newDataSourceName, newDataSourceName);  
newDatasource.ConnectionString = DatasourceCnxString.Text;  
if (impersonateServiceAccount.Checked)  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateServiceAccount);  
else  
{  
    if (String.IsNullOrEmpty(impersonateAccountUserName.Text))  
    {  
        MessageBox.Show(String.Format("Account User Name cannot be blank when using 'ImpersonateAccount' mode"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        return;  
    }  
    newDatasource.ImpersonationInfo = new AMO.ImpersonationInfo(AMO.ImpersonationMode.ImpersonateAccount, impersonateAccountUserName.Text, impersonateAccountPassword.Text);  
}  
newDatasource.Update();  
  
```  
  
## <a name="tabular-amo-2012-sample"></a><span data-ttu-id="2e8e9-109">Esempio Tabular AMO 2012</span><span class="sxs-lookup"><span data-stu-id="2e8e9-109">Tabular AMO 2012 sample</span></span>  
 <span data-ttu-id="2e8e9-110">Per comprendere meglio le modalità di utilizzo di AMO per creare e gestire le rappresentazioni di connessioni, vedere il codice sorgente nell'esempio Tabular AMO 2012; in particolare effettuare un controllo nel seguente file di origine: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-110">To have a better understanding on how to use AMO to create and manipulate connection representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="2e8e9-111">L'esempio è disponibile in Codeplex.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="2e8e9-112">Il codice di esempio viene fornito solo come supporto ai concetti logici illustrati in questo argomento e non deve essere utilizzato in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="2e8e9-112">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
