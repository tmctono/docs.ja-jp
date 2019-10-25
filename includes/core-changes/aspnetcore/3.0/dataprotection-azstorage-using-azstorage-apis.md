---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394088"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="3ea36-101">データの保護: DataProtection.AzureStorage で新しい Azure Storage API が使用されるようになる</span><span class="sxs-lookup"><span data-stu-id="3ea36-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="3ea36-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> は [Azure Storage ライブラリ](https://github.com/Azure/azure-storage-net)に依存します。</span><span class="sxs-lookup"><span data-stu-id="3ea36-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="3ea36-103">これらのライブラリで、アセンブリ、パッケージ、名前空間の名前が変更されました。</span><span class="sxs-lookup"><span data-stu-id="3ea36-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="3ea36-104">ASP.NET Core 3.0 以降、`Microsoft.AspNetCore.DataProtection.AzureStorage` では `Microsoft.Azure.Storage.` というプレフィックスが付いた新しい API およびパッケージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ea36-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="3ea36-105">Azure Storage API に関する質問については、<https://github.com/Azure/azure-storage-net> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3ea36-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="3ea36-106">この問題に関するディスカッションについては、[aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea36-106">For discussion on this issue, see [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ea36-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="3ea36-107">Version introduced</span></span>

<span data-ttu-id="3ea36-108">3.0</span><span class="sxs-lookup"><span data-stu-id="3ea36-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3ea36-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="3ea36-109">Old behavior</span></span>

<span data-ttu-id="3ea36-110">パッケージでは `WindowsAzure.Storage` NuGet パッケージが参照されていました。</span><span class="sxs-lookup"><span data-stu-id="3ea36-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3ea36-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="3ea36-111">New behavior</span></span>

<span data-ttu-id="3ea36-112">パッケージでは `Microsoft.Azure.Storage.Blob` NuGet パッケージが参照されています。</span><span class="sxs-lookup"><span data-stu-id="3ea36-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3ea36-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="3ea36-113">Reason for change</span></span>

<span data-ttu-id="3ea36-114">この変更により、`Microsoft.AspNetCore.DataProtection.AzureStorage` は推奨される Azure Storage パッケージに移行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3ea36-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ea36-115">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="3ea36-115">Recommended action</span></span>

<span data-ttu-id="3ea36-116">ASP.NET Core 3.0 で古い Azure Storage API をまだ使用する必要がある場合は、[Windowsazure.servicebus](https://www.nuget.org/packages/WindowsAzure.Storage/) パッケージに対する直接的な依存関係を追加してください。</span><span class="sxs-lookup"><span data-stu-id="3ea36-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="3ea36-117">このパッケージは、新しい `Microsoft.Azure.Storage` API と共にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ea36-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="3ea36-118">多くの場合、アップグレードで必要なのは、新しい名前空間を使用するように `using` ステートメントを変更することだけです。</span><span class="sxs-lookup"><span data-stu-id="3ea36-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="3ea36-119">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3ea36-119">Category</span></span>

<span data-ttu-id="3ea36-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ea36-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ea36-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3ea36-121">Affected APIs</span></span>

<span data-ttu-id="3ea36-122">なし</span><span class="sxs-lookup"><span data-stu-id="3ea36-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
