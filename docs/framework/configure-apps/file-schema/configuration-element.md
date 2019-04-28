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
ms.openlocfilehash: 9a7b25c74763c020c0e19c3f6099db9001acf773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705416"
---
# <a name="configuration-element"></a><span data-ttu-id="6bb60-102">\<configuration > 要素</span><span class="sxs-lookup"><span data-stu-id="6bb60-102">\<configuration> element</span></span>

<span data-ttu-id="6bb60-103">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6bb60-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="6bb60-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="6bb60-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6bb60-105">構文</span><span class="sxs-lookup"><span data-stu-id="6bb60-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="6bb60-106">属性</span><span class="sxs-lookup"><span data-stu-id="6bb60-106">Attributes</span></span>

<span data-ttu-id="6bb60-107">なし</span><span class="sxs-lookup"><span data-stu-id="6bb60-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6bb60-108">親要素</span><span class="sxs-lookup"><span data-stu-id="6bb60-108">Parent element</span></span>

<span data-ttu-id="6bb60-109">なし</span><span class="sxs-lookup"><span data-stu-id="6bb60-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="6bb60-110">子要素</span><span class="sxs-lookup"><span data-stu-id="6bb60-110">Child elements</span></span>

|     | <span data-ttu-id="6bb60-111">説明</span><span class="sxs-lookup"><span data-stu-id="6bb60-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6bb60-112">**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="6bb60-112">**\<assemblyBinding>**</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="6bb60-113">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6bb60-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="6bb60-114">**\<スタートアップ >** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-114">**\<startup>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/startup/index.md) | <span data-ttu-id="6bb60-115">スタートアップ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="6bb60-116">**\<ランタイム >** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-116">**\<runtime>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/runtime/index.md) | <span data-ttu-id="6bb60-117">ランタイム設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="6bb60-118">[**\<system.runtime.remoting >** 設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bb60-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="6bb60-119">リモート処理設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="6bb60-120">**\<system.Net >** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-120">**\<system.Net>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/network/index.md) | <span data-ttu-id="6bb60-121">ネットワーク設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="6bb60-122">**\<cryptographySettings >** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-122">**\<cryptographySettings>** Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/cryptography/index.md) | <span data-ttu-id="6bb60-123">暗号設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="6bb60-124">**\<configuration >** セクション スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-124">**\<configuration>** Sections Schema</span></span>](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) | <span data-ttu-id="6bb60-125">構成セクションの設定のスキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="6bb60-126">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-126">Trace and Debug Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) | <span data-ttu-id="6bb60-127">トレースとデバッグの設定のスキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="6bb60-128">[ASP.NET 構成設定のスキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bb60-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="6bb60-129">ASP.NET Web サイトおよびアプリケーションを構成するための要素を含む、ASP.NET 構成スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="6bb60-130">使用される*Web.config*ファイル。</span><span class="sxs-lookup"><span data-stu-id="6bb60-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="6bb60-131">[**\<webServices >** 設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6bb60-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="6bb60-132">Web サービス設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="6bb60-133">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-133">Web Settings Schema</span></span>](~/docs/framework/configure-apps/file-schema/web/index.md) | <span data-ttu-id="6bb60-134">IIS などのホスト アプリケーションと ASP.NET の連携を構成する要素も含め、Web 設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="6bb60-135">使用される*aspnet.config*ファイル。</span><span class="sxs-lookup"><span data-stu-id="6bb60-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6bb60-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="6bb60-136">Remarks</span></span>

<span data-ttu-id="6bb60-137">各構成ファイルには、1 つだけ含める必要があります**\<構成 >** 要素。</span><span class="sxs-lookup"><span data-stu-id="6bb60-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bb60-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bb60-138">See also</span></span>

- [<span data-ttu-id="6bb60-139">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6bb60-139">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
