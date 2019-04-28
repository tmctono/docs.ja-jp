---
title: SQL Server の CLR 統合セキュリティ
ms.date: 03/30/2017
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
ms.openlocfilehash: 946401211d515df9ba5b9e38d7cfd10730973b64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878489"
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="6fe2e-102">SQL Server の CLR 統合セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6fe2e-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="6fe2e-103">Microsoft SQL Server で新たに導入された機能の 1 つに、.NET Framework の共通言語ランタイム (CLR) コンポーネントの統合があります。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="6fe2e-104">CLR の統合により、Microsoft Visual Basic .NET や Microsoft Visual C# を含む任意の .NET Framework 言語を使用して、ストアド プロシージャ、トリガー、ユーザー定義型、ユーザー定義関数、ユーザー定義集計、およびストリーミング テーブル値関数を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="6fe2e-105">CLR は、コード アクセス セキュリティ (CAS) と呼ばれるマネージド コード用のセキュリティ モデルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="6fe2e-106">このモデルでは、コードのメタデータに指定された証拠に基づいてアセンブリに権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="6fe2e-107">SQL Server のユーザーベースのセキュリティ モデルは、SQL Server により CLR のコード アクセスベースのセキュリティ モデルと統合されます。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="6fe2e-108">外部リソース</span><span class="sxs-lookup"><span data-stu-id="6fe2e-108">External Resources</span></span>  
 <span data-ttu-id="6fe2e-109">SQL Server と CLR の統合の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="6fe2e-110">リソース</span><span class="sxs-lookup"><span data-stu-id="6fe2e-110">Resource</span></span>|<span data-ttu-id="6fe2e-111">説明</span><span class="sxs-lookup"><span data-stu-id="6fe2e-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="6fe2e-112">コード アクセス セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6fe2e-112">Code Access Security</span></span>](../../../../../docs/framework/misc/code-access-security.md)|<span data-ttu-id="6fe2e-113">.NET Framework の CAS について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="6fe2e-114">CLR 統合のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="6fe2e-114">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)|<span data-ttu-id="6fe2e-115">SQL Server の内部で実行されるマネージド コードのセキュリティ モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6fe2e-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6fe2e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fe2e-116">See also</span></span>

- [<span data-ttu-id="6fe2e-117">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6fe2e-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="6fe2e-118">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="6fe2e-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="6fe2e-119">SQL Server の共通言語ランタイム統合</span><span class="sxs-lookup"><span data-stu-id="6fe2e-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)
- [<span data-ttu-id="6fe2e-120">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6fe2e-120">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)
