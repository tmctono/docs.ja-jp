---
title: <assemblyBinding>appSettings&gt;の<configuration>add&gt;要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: f5992a6085c32d37f56319cf8b2c361542c441e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674832"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="bd781-102">\<assemblyBinding > 要素の\<構成 ></span><span class="sxs-lookup"><span data-stu-id="bd781-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="bd781-103">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd781-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="bd781-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="bd781-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="bd781-105">&nbsp;&nbsp;**\<assemblyBinding >**</span><span class="sxs-lookup"><span data-stu-id="bd781-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bd781-106">構文</span><span class="sxs-lookup"><span data-stu-id="bd781-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="bd781-107">属性</span><span class="sxs-lookup"><span data-stu-id="bd781-107">Attribute</span></span>

|           | <span data-ttu-id="bd781-108">説明</span><span class="sxs-lookup"><span data-stu-id="bd781-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="bd781-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="bd781-109">**xmlns**</span></span> | <span data-ttu-id="bd781-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="bd781-110">Required attribute.</span></span><br><br><span data-ttu-id="bd781-111">アセンブリのバインディングに必要な XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd781-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="bd781-112">値として、文字列 "urn:schemas-microsoft-com:asm.v1" を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd781-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="bd781-113">親要素</span><span class="sxs-lookup"><span data-stu-id="bd781-113">Parent element</span></span>

|     | <span data-ttu-id="bd781-114">説明</span><span class="sxs-lookup"><span data-stu-id="bd781-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bd781-115">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="bd781-115">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="bd781-116">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bd781-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="bd781-117">子要素</span><span class="sxs-lookup"><span data-stu-id="bd781-117">Child element</span></span>

|     | <span data-ttu-id="bd781-118">説明</span><span class="sxs-lookup"><span data-stu-id="bd781-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bd781-119">**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="bd781-119">**\<linkedConfiguration>**</span></span>](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | <span data-ttu-id="bd781-120">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd781-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="bd781-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="bd781-121">Remarks</span></span>

<span data-ttu-id="bd781-122">[  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)要素は、構成ファイルをアプリケーション構成ファイルにアセンブリを含めるようにすることでコンポーネントのアセンブリの管理を簡略化既知の場所ではなく複製アセンブリの構成設定。</span><span class="sxs-lookup"><span data-stu-id="bd781-122">The [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="bd781-123"> *\*\<LinkedConfiguration >** Windows サイド バイ サイドでマニフェストを使用するアプリケーションの要素がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bd781-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="bd781-124">例</span><span class="sxs-lookup"><span data-stu-id="bd781-124">Example</span></span>

<span data-ttu-id="bd781-125">次の例では、ローカルのハード ディスク上の構成ファイルを含める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd781-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bd781-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd781-126">See also</span></span>

- [<span data-ttu-id="bd781-127">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="bd781-127">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
