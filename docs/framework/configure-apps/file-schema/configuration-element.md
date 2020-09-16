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
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544691"
---
# <a name="configuration-element"></a><span data-ttu-id="58c95-102">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="58c95-102">\<configuration> element</span></span>

<span data-ttu-id="58c95-103">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="58c95-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="58c95-104">構文</span><span class="sxs-lookup"><span data-stu-id="58c95-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="58c95-105">属性</span><span class="sxs-lookup"><span data-stu-id="58c95-105">Attributes</span></span>

<span data-ttu-id="58c95-106">なし</span><span class="sxs-lookup"><span data-stu-id="58c95-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="58c95-107">親要素</span><span class="sxs-lookup"><span data-stu-id="58c95-107">Parent element</span></span>

<span data-ttu-id="58c95-108">なし</span><span class="sxs-lookup"><span data-stu-id="58c95-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="58c95-109">子要素</span><span class="sxs-lookup"><span data-stu-id="58c95-109">Child elements</span></span>

|     | <span data-ttu-id="58c95-110">説明</span><span class="sxs-lookup"><span data-stu-id="58c95-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="58c95-111">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="58c95-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="58c95-112">**\<startup>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="58c95-113">スタートアップ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="58c95-114">**\<runtime>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="58c95-115">ランタイム設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="58c95-116">[**\<system.runtime.remoting>** 設定スキーマ](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="58c95-116">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="58c95-117">リモート処理設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="58c95-118">**\<system.Net>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="58c95-119">ネットワーク設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="58c95-120">**\<cryptographySettings>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="58c95-121">暗号化設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="58c95-122">**\<configuration>** セクションスキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="58c95-123">構成セクション設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="58c95-124">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="58c95-125">トレースおよびデバッグ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="58c95-126">[ASP.NET 構成設定スキーマ](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="58c95-126">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="58c95-127">ASP.NET 構成スキーマのすべての要素。 ASP.NET Web サイトおよびアプリケーションを構成するための要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58c95-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="58c95-128">*Web.config*ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="58c95-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="58c95-129">[**\<webServices>** 設定スキーマ](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="58c95-129">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="58c95-130">Web サービス設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="58c95-131">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="58c95-132">IIS などのホスト アプリケーションと ASP.NET の連携を構成する要素も含め、Web 設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="58c95-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="58c95-133">*aspnet.config*ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="58c95-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="58c95-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="58c95-134">Remarks</span></span>

<span data-ttu-id="58c95-135">各構成ファイルには、要素が1つだけ含まれている必要があり **\<configuration>** ます。</span><span class="sxs-lookup"><span data-stu-id="58c95-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="58c95-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="58c95-136">See also</span></span>

- [<span data-ttu-id="58c95-137">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="58c95-137">Configuration file schema for the .NET Framework</span></span>](index.md)
