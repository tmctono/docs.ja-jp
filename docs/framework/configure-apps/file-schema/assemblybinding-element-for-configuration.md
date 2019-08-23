---
title: <assemblyBinding>appSettings&gt;の<configuration>add&gt;要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921275"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="958d2-102">\<構成 > の\<assemblybinding > 要素</span><span class="sxs-lookup"><span data-stu-id="958d2-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="958d2-103">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="958d2-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="958d2-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="958d2-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="958d2-105">&nbsp;&nbsp; **\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="958d2-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="958d2-106">構文</span><span class="sxs-lookup"><span data-stu-id="958d2-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="958d2-107">属性</span><span class="sxs-lookup"><span data-stu-id="958d2-107">Attribute</span></span>

|           | <span data-ttu-id="958d2-108">説明</span><span class="sxs-lookup"><span data-stu-id="958d2-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="958d2-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="958d2-109">**xmlns**</span></span> | <span data-ttu-id="958d2-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="958d2-110">Required attribute.</span></span><br><br><span data-ttu-id="958d2-111">アセンブリのバインディングに必要な XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="958d2-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="958d2-112">値として、文字列 "urn:schemas-microsoft-com:asm.v1" を使用します。</span><span class="sxs-lookup"><span data-stu-id="958d2-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="958d2-113">親要素</span><span class="sxs-lookup"><span data-stu-id="958d2-113">Parent element</span></span>

|     | <span data-ttu-id="958d2-114">説明</span><span class="sxs-lookup"><span data-stu-id="958d2-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="958d2-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="958d2-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="958d2-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="958d2-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="958d2-117">子要素</span><span class="sxs-lookup"><span data-stu-id="958d2-117">Child element</span></span>

|     | <span data-ttu-id="958d2-118">説明</span><span class="sxs-lookup"><span data-stu-id="958d2-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="958d2-119"> **\<linkedConfiguration >** </span><span class="sxs-lookup"><span data-stu-id="958d2-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="958d2-120">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="958d2-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="958d2-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="958d2-121">Remarks</span></span>

<span data-ttu-id="958d2-122">[ **\<Linkedconfiguration >** ](linkedconfiguration-element.md)要素は、アセンブリを複製するのではなく、既知の場所にアセンブリ構成ファイルを含めることをアプリケーション構成ファイルに許可することで、コンポーネントアセンブリの管理を簡略化します。構成設定。</span><span class="sxs-lookup"><span data-stu-id="958d2-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="958d2-123">**\<Linkedconfiguration >** 要素は、Windows サイドバイサイドマニフェストを持つアプリケーションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="958d2-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="958d2-124">例</span><span class="sxs-lookup"><span data-stu-id="958d2-124">Example</span></span>

<span data-ttu-id="958d2-125">次の例は、ローカルのハードディスクに構成ファイルを含める方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="958d2-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="958d2-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="958d2-126">See also</span></span>

- [<span data-ttu-id="958d2-127">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="958d2-127">Configuration file schema for the .NET Framework</span></span>](index.md)
