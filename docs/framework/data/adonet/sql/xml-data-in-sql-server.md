---
title: SQL Server における XML データ
ms.date: 03/30/2017
ms.assetid: 9849d319-f518-4e3d-a7cd-f8fdcaaa1d4d
ms.openlocfilehash: 8ad92334a2afd4791bb0b40378c49a0efa14fefd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147607"
---
# <a name="xml-data-in-sql-server"></a><span data-ttu-id="0165d-102">SQL Server における XML データ</span><span class="sxs-lookup"><span data-stu-id="0165d-102">XML Data in SQL Server</span></span>

<span data-ttu-id="0165d-103">SQL Server は、.NET Framework 内部の SQLXML の機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="0165d-103">SQL Server exposes the functionality of SQLXML inside the .NET Framework.</span></span> <span data-ttu-id="0165d-104">開発者は、SQL Server のインスタンスから XML データにアクセスし、データを .NET Framework 環境に持ち込んで処理し、更新を SQL Server に送り返すアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0165d-104">Developers can write applications that access XML data from an instance of SQL Server, bring the data into the .NET Framework environment, process the data, and send the updates back to SQL Server.</span></span> <span data-ttu-id="0165d-105">SQL Server では、XML データをデータ ストレージなどの目的に、あるいはデータを取得するときのパラメーター値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="0165d-105">XML data can be used in several ways in SQL Server, including data storage, and as parameter values for retrieving data.</span></span> <span data-ttu-id="0165d-106">.NET Framework の **SqlXml** クラスは、SQL Server 内の XML 列に格納されたデータのクライアント側の操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0165d-106">The **SqlXml** class in the .NET Framework provides the client-side support for working with data stored in an XML column within SQL Server.</span></span> <span data-ttu-id="0165d-107">詳細については、SQL Server オンライン ブックの「SQLXML マネージド クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0165d-107">For more information, see "SQLXML Managed Classes" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0165d-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0165d-108">In This Section</span></span>  

 [<span data-ttu-id="0165d-109">SQL XML 列値</span><span class="sxs-lookup"><span data-stu-id="0165d-109">SQL XML Column Values</span></span>](sql-xml-column-values.md)  
 <span data-ttu-id="0165d-110">SQL Server から XML データを取得し、使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0165d-110">Demonstrates how to retrieve and work with XML data retrieved from SQL Server.</span></span>  
  
 [<span data-ttu-id="0165d-111">パラメーターとしての XML 値の指定</span><span class="sxs-lookup"><span data-stu-id="0165d-111">Specifying XML Values as Parameters</span></span>](specifying-xml-values-as-parameters.md)  
 <span data-ttu-id="0165d-112">コマンドに XML データをパラメーターとして渡す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0165d-112">Demonstrates how to pass XML data as a parameter to a command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0165d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0165d-113">See also</span></span>

- [<span data-ttu-id="0165d-114">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0165d-114">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="0165d-115">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="0165d-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
