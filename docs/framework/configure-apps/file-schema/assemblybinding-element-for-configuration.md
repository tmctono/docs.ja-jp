---
title: <configuration> の <assemblyBinding> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155480"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="104bd-102">\<configuration> の \<assemblyBinding> 要素</span><span class="sxs-lookup"><span data-stu-id="104bd-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="104bd-103">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="104bd-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="104bd-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="104bd-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="104bd-105">構文</span><span class="sxs-lookup"><span data-stu-id="104bd-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="104bd-106">属性</span><span class="sxs-lookup"><span data-stu-id="104bd-106">Attribute</span></span>

|           | <span data-ttu-id="104bd-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="104bd-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="104bd-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="104bd-108">**xmlns**</span></span> | <span data-ttu-id="104bd-109">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="104bd-109">Required attribute.</span></span><br><br><span data-ttu-id="104bd-110">アセンブリのバインディングに必要な XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="104bd-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="104bd-111">値として、文字列 "urn:schemas-microsoft-com:asm.v1" を使用します。</span><span class="sxs-lookup"><span data-stu-id="104bd-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="104bd-112">親要素</span><span class="sxs-lookup"><span data-stu-id="104bd-112">Parent element</span></span>

|     | <span data-ttu-id="104bd-113">Description</span><span class="sxs-lookup"><span data-stu-id="104bd-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="104bd-114">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="104bd-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="104bd-115">子要素</span><span class="sxs-lookup"><span data-stu-id="104bd-115">Child element</span></span>

|     | <span data-ttu-id="104bd-116">説明</span><span class="sxs-lookup"><span data-stu-id="104bd-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="104bd-117">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="104bd-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="104bd-118">解説</span><span class="sxs-lookup"><span data-stu-id="104bd-118">Remarks</span></span>

<span data-ttu-id="104bd-119">要素は、 [**\<linkedConfiguration>**](linkedconfiguration-element.md) アセンブリ構成設定を複製するのではなく、アプリケーション構成ファイルに既知の場所にアセンブリ構成ファイルを含めることができるようにすることで、コンポーネントアセンブリの管理を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="104bd-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="104bd-120">**\<linkedConfiguration>** 要素は、Windows サイドバイサイドマニフェストを持つアプリケーションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="104bd-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="104bd-121">例</span><span class="sxs-lookup"><span data-stu-id="104bd-121">Example</span></span>

<span data-ttu-id="104bd-122">次の例は、ローカルのハードディスクに構成ファイルを含める方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="104bd-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="104bd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="104bd-123">See also</span></span>

- [<span data-ttu-id="104bd-124">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="104bd-124">Configuration file schema for the .NET Framework</span></span>](index.md)
