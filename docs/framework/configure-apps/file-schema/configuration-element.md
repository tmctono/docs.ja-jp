---
title: <configuration> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921245"
---
# <a name="configuration-element"></a><span data-ttu-id="f5b23-102">\<構成 > 要素</span><span class="sxs-lookup"><span data-stu-id="f5b23-102">\<configuration> element</span></span>

<span data-ttu-id="f5b23-103">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f5b23-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="f5b23-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="f5b23-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f5b23-105">構文</span><span class="sxs-lookup"><span data-stu-id="f5b23-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="f5b23-106">属性</span><span class="sxs-lookup"><span data-stu-id="f5b23-106">Attributes</span></span>

<span data-ttu-id="f5b23-107">なし</span><span class="sxs-lookup"><span data-stu-id="f5b23-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="f5b23-108">親要素</span><span class="sxs-lookup"><span data-stu-id="f5b23-108">Parent element</span></span>

<span data-ttu-id="f5b23-109">なし</span><span class="sxs-lookup"><span data-stu-id="f5b23-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="f5b23-110">子要素</span><span class="sxs-lookup"><span data-stu-id="f5b23-110">Child elements</span></span>

|     | <span data-ttu-id="f5b23-111">説明</span><span class="sxs-lookup"><span data-stu-id="f5b23-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f5b23-112"> **\<assemblyBinding >** </span><span class="sxs-lookup"><span data-stu-id="f5b23-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="f5b23-113">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b23-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="f5b23-114">スタートアップ > 設定スキーマ **\<** </span><span class="sxs-lookup"><span data-stu-id="f5b23-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="f5b23-115">スタートアップ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="f5b23-116">ランタイム > 設定スキーマ **\<** </span><span class="sxs-lookup"><span data-stu-id="f5b23-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="f5b23-117">ランタイム設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="f5b23-118">[system.string > 設定スキーマ **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5b23-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="f5b23-119">リモート処理設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="f5b23-120">システム .net > 設定スキーマ **\<** </span><span class="sxs-lookup"><span data-stu-id="f5b23-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="f5b23-121">ネットワーク設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="f5b23-122">cryptographysettings > 設定スキーマ **\<** </span><span class="sxs-lookup"><span data-stu-id="f5b23-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="f5b23-123">暗号化設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="f5b23-124">構成 > セクションスキーマ **\<** </span><span class="sxs-lookup"><span data-stu-id="f5b23-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="f5b23-125">構成セクション設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="f5b23-126">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="f5b23-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="f5b23-127">トレースおよびデバッグ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="f5b23-128">[ASP.NET 構成設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5b23-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="f5b23-129">ASP.NET 構成スキーマのすべての要素。 ASP.NET Web サイトおよびアプリケーションを構成するための要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5b23-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="f5b23-130">Web.config ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b23-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="f5b23-131">[の > 設定スキーマの構成 **\<** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f5b23-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="f5b23-132">Web サービス設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="f5b23-133">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f5b23-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="f5b23-134">IIS などのホスト アプリケーションと ASP.NET の連携を構成する要素も含め、Web 設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="f5b23-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="f5b23-135">*Aspnet*ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b23-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f5b23-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5b23-136">Remarks</span></span>

<span data-ttu-id="f5b23-137">各構成ファイルには、  **\<構成 >** 要素が1つだけ含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b23-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5b23-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5b23-138">See also</span></span>

- [<span data-ttu-id="f5b23-139">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="f5b23-139">Configuration file schema for the .NET Framework</span></span>](index.md)
