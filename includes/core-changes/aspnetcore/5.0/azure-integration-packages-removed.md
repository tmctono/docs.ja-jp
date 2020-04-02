---
ms.openlocfilehash: d8506893f5b3eefa6f46dc9f773e43b125ee5210
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291667"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="61ed7-101">Azure: Microsoft というプレフィックスが付いた Azure 統合パッケージが削除された</span><span class="sxs-lookup"><span data-stu-id="61ed7-101">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="61ed7-102">ASP.NET Core と Azure SDK の統合を提供する次の `Microsoft.*` パッケージは、ASP.NET Core 5.0 に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="61ed7-102">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="61ed7-103">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/)。[Azure Key Vault](/azure/key-vault/) を[構成システム](/aspnet/core/fundamentals/configuration/)に統合します。</span><span class="sxs-lookup"><span data-stu-id="61ed7-103">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="61ed7-104">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/)。Azure Key Vault を [ASP.NET Core データ保護システム](/aspnet/core/security/data-protection/introduction)に統合します。</span><span class="sxs-lookup"><span data-stu-id="61ed7-104">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="61ed7-105">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/)。[Azure Blob Storage](/azure/storage/blobs/) を ASP.NET Core データ保護システムに統合します。</span><span class="sxs-lookup"><span data-stu-id="61ed7-105">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="61ed7-106">この問題に関するディスカッションについては、[dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61ed7-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="61ed7-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="61ed7-107">Version introduced</span></span>

<span data-ttu-id="61ed7-108">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="61ed7-108">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="61ed7-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="61ed7-109">Old behavior</span></span>

<span data-ttu-id="61ed7-110">`Microsoft.*` パッケージにより、Azure サービスと構成 API およびデータ保護 API が統合されていました。</span><span class="sxs-lookup"><span data-stu-id="61ed7-110">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="61ed7-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="61ed7-111">New behavior</span></span>

<span data-ttu-id="61ed7-112">新しい `Azure.*` パッケージにより、Azure サービスと構成 API およびデータ保護 API が統合されます。</span><span class="sxs-lookup"><span data-stu-id="61ed7-112">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="61ed7-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="61ed7-113">Reason for change</span></span>

<span data-ttu-id="61ed7-114">この変更は、`Microsoft.*` パッケージが以下であるために行われました。</span><span class="sxs-lookup"><span data-stu-id="61ed7-114">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="61ed7-115">古いバージョンの Azure SDK を使用していました。</span><span class="sxs-lookup"><span data-stu-id="61ed7-115">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="61ed7-116">新しいバージョンの Azure SDK には破壊的変更が含まれていたため、単純な更新はできませんでした。</span><span class="sxs-lookup"><span data-stu-id="61ed7-116">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="61ed7-117">.NET Core のリリース スケジュールに拘束されていました。</span><span class="sxs-lookup"><span data-stu-id="61ed7-117">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="61ed7-118">パッケージの所有権を Azure SDK チームに譲渡すると、Azure SDK が更新されるときにパッケージを更新できます。</span><span class="sxs-lookup"><span data-stu-id="61ed7-118">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="61ed7-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="61ed7-119">Recommended action</span></span>

<span data-ttu-id="61ed7-120">ASP.NET Core 2.1 以降のプロジェクトでは、古い `Microsoft.*` パッケージを新しい `Azure.*` パッケージに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61ed7-120">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="61ed7-121">旧</span><span class="sxs-lookup"><span data-stu-id="61ed7-121">Old</span></span> | <span data-ttu-id="61ed7-122">新規作成</span><span class="sxs-lookup"><span data-stu-id="61ed7-122">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="61ed7-123">Azure.AspNetCore.DataProtection.Keys</span><span class="sxs-lookup"><span data-stu-id="61ed7-123">Azure.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="61ed7-124">Azure.AspNetCore.DataProtection.Blobs</span><span class="sxs-lookup"><span data-stu-id="61ed7-124">Azure.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="61ed7-125">Azure.Extensions.Configuration.Secrets</span><span class="sxs-lookup"><span data-stu-id="61ed7-125">Azure.Extensions.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.Configuration.Secrets) |

<span data-ttu-id="61ed7-126">新しいパッケージでは、破壊的変更が含まれる新しいバージョンの Azure SDK が使用されています。</span><span class="sxs-lookup"><span data-stu-id="61ed7-126">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="61ed7-127">一般的な使用パターンは変更されません。</span><span class="sxs-lookup"><span data-stu-id="61ed7-127">The general usage patterns are unchanged.</span></span> <span data-ttu-id="61ed7-128">基になっている Azure SDK API での変更に対応するため、一部のオーバーロードとオプションが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="61ed7-128">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="61ed7-129">古いパッケージは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="61ed7-129">The old packages will:</span></span>

* <span data-ttu-id="61ed7-130">.NET Core 2.1 および 3.1 の有効期間中は、ASP.NET Core チームによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="61ed7-130">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="61ed7-131">.NET 5 には含まれません。</span><span class="sxs-lookup"><span data-stu-id="61ed7-131">Not be included in .NET 5.</span></span>

<span data-ttu-id="61ed7-132">プロジェクトを .NET 5 にアップグレードするときは、サポートを維持するため `Azure.*` パッケージに切り替えてください。</span><span class="sxs-lookup"><span data-stu-id="61ed7-132">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

#### <a name="category"></a><span data-ttu-id="61ed7-133">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="61ed7-133">Category</span></span>

<span data-ttu-id="61ed7-134">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="61ed7-134">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="61ed7-135">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="61ed7-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
