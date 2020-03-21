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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155480"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="5d636-102">\<コンフィギュレーション>の>要素\<の組み合て</span><span class="sxs-lookup"><span data-stu-id="5d636-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="5d636-103">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d636-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="5d636-104">&nbsp;[**\<アセンブリ>**](configuration-element.md)&nbsp;**構成>\<**</span><span class="sxs-lookup"><span data-stu-id="5d636-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5d636-105">構文</span><span class="sxs-lookup"><span data-stu-id="5d636-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="5d636-106">属性</span><span class="sxs-lookup"><span data-stu-id="5d636-106">Attribute</span></span>

|           | <span data-ttu-id="5d636-107">説明</span><span class="sxs-lookup"><span data-stu-id="5d636-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5d636-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="5d636-108">**xmlns**</span></span> | <span data-ttu-id="5d636-109">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5d636-109">Required attribute.</span></span><br><br><span data-ttu-id="5d636-110">アセンブリのバインディングに必要な XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d636-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="5d636-111">値として、文字列 "urn:schemas-microsoft-com:asm.v1" を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d636-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5d636-112">親要素</span><span class="sxs-lookup"><span data-stu-id="5d636-112">Parent element</span></span>

|     | <span data-ttu-id="5d636-113">説明</span><span class="sxs-lookup"><span data-stu-id="5d636-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5d636-114">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="5d636-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="5d636-115">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5d636-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="5d636-116">子要素</span><span class="sxs-lookup"><span data-stu-id="5d636-116">Child element</span></span>

|     | <span data-ttu-id="5d636-117">説明</span><span class="sxs-lookup"><span data-stu-id="5d636-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5d636-118">**\<リンクされた構成>**</span><span class="sxs-lookup"><span data-stu-id="5d636-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="5d636-119">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d636-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5d636-120">解説</span><span class="sxs-lookup"><span data-stu-id="5d636-120">Remarks</span></span>

<span data-ttu-id="5d636-121">[\*\* \<linkedConfiguration>\*\*](linkedconfiguration-element.md)要素は、アセンブリ構成設定を複製するのではなく、既知の場所にアセンブリ構成ファイルを含めることで、コンポーネント アセンブリの管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="5d636-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="5d636-122">リンクされた構成>要素は、Windows のサイド バイ サイド マニフェストを持つアプリケーションではサポートされていません。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="5d636-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="5d636-123">例</span><span class="sxs-lookup"><span data-stu-id="5d636-123">Example</span></span>

<span data-ttu-id="5d636-124">次の例は、ローカル ハード ディスクに構成ファイルを含める方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d636-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5d636-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d636-125">See also</span></span>

- [<span data-ttu-id="5d636-126">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5d636-126">Configuration file schema for the .NET Framework</span></span>](index.md)
