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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "69921245"
---
# <a name="configuration-element"></a><span data-ttu-id="9289e-102">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="9289e-102">\<configuration> element</span></span>

<span data-ttu-id="9289e-103">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9289e-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="9289e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9289e-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="9289e-105">属性</span><span class="sxs-lookup"><span data-stu-id="9289e-105">Attributes</span></span>

<span data-ttu-id="9289e-106">なし</span><span class="sxs-lookup"><span data-stu-id="9289e-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9289e-107">親要素</span><span class="sxs-lookup"><span data-stu-id="9289e-107">Parent element</span></span>

<span data-ttu-id="9289e-108">なし</span><span class="sxs-lookup"><span data-stu-id="9289e-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="9289e-109">子要素</span><span class="sxs-lookup"><span data-stu-id="9289e-109">Child elements</span></span>

|     | <span data-ttu-id="9289e-110">Description</span><span class="sxs-lookup"><span data-stu-id="9289e-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="9289e-111">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9289e-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="9289e-112">**\<startup>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="9289e-113">スタートアップ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="9289e-114">**\<runtime>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="9289e-115">ランタイム設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="9289e-116">[**\<system.runtime.remoting>** 設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9289e-116">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="9289e-117">リモート処理設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="9289e-118">**\<system.Net>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="9289e-119">ネットワーク設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="9289e-120">**\<cryptographySettings>** 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="9289e-121">暗号化設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="9289e-122">**\<configuration>** セクションスキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="9289e-123">構成セクション設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="9289e-124">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="9289e-125">トレースおよびデバッグ設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="9289e-126">[ASP.NET 構成設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9289e-126">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="9289e-127">ASP.NET 構成スキーマのすべての要素。 ASP.NET Web サイトおよびアプリケーションを構成するための要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9289e-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="9289e-128">*Web.config ファイルで*使用されます。</span><span class="sxs-lookup"><span data-stu-id="9289e-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="9289e-129">[**\<webServices>** 設定スキーマ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9289e-129">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="9289e-130">Web サービス設定スキーマ内のすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="9289e-131">Web 設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="9289e-132">IIS などのホスト アプリケーションと ASP.NET の連携を構成する要素も含め、Web 設定スキーマのすべての要素。</span><span class="sxs-lookup"><span data-stu-id="9289e-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="9289e-133">*Aspnet*ファイルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="9289e-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9289e-134">解説</span><span class="sxs-lookup"><span data-stu-id="9289e-134">Remarks</span></span>

<span data-ttu-id="9289e-135">各構成ファイルには、要素が1つだけ含まれている必要があり **\<configuration>** ます。</span><span class="sxs-lookup"><span data-stu-id="9289e-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="9289e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="9289e-136">See also</span></span>

- [<span data-ttu-id="9289e-137">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="9289e-137">Configuration file schema for the .NET Framework</span></span>](index.md)
