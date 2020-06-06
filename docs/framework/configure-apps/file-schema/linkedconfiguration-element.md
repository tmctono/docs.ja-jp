---
title: <linkedConfiguration> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087961"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="d7c64-102">\<linkedConfiguration> 要素</span><span class="sxs-lookup"><span data-stu-id="d7c64-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="d7c64-103">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7c64-103">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="d7c64-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7c64-104">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="d7c64-105">属性</span><span class="sxs-lookup"><span data-stu-id="d7c64-105">Attribute</span></span>

|           | <span data-ttu-id="d7c64-106">[説明]</span><span class="sxs-lookup"><span data-stu-id="d7c64-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d7c64-107">**href**</span><span class="sxs-lookup"><span data-stu-id="d7c64-107">**href**</span></span>  | <span data-ttu-id="d7c64-108">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="d7c64-108">Required attribute.</span></span><br><br><span data-ttu-id="d7c64-109">含める構成ファイルの URL。</span><span class="sxs-lookup"><span data-stu-id="d7c64-109">The URL of the configuration file to include.</span></span> <span data-ttu-id="d7c64-110">**Href**属性でサポートされている形式はのみ `file://` です。</span><span class="sxs-lookup"><span data-stu-id="d7c64-110">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="d7c64-111">ローカルファイルと UNC ファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d7c64-111">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d7c64-112">親要素</span><span class="sxs-lookup"><span data-stu-id="d7c64-112">Parent element</span></span>

|     | <span data-ttu-id="d7c64-113">説明</span><span class="sxs-lookup"><span data-stu-id="d7c64-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d7c64-114">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="d7c64-114">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="d7c64-115">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7c64-115">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d7c64-116">子要素</span><span class="sxs-lookup"><span data-stu-id="d7c64-116">Child elements</span></span>

<span data-ttu-id="d7c64-117">なし</span><span class="sxs-lookup"><span data-stu-id="d7c64-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d7c64-118">解説</span><span class="sxs-lookup"><span data-stu-id="d7c64-118">Remarks</span></span>

<span data-ttu-id="d7c64-119">要素は、 **\<linkedConfiguration>** コンポーネントアセンブリのサービスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="d7c64-119">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="d7c64-120">既知の場所に構成ファイルが存在するアセンブリを1つ以上のアプリケーションが使用する場合、そのアセンブリを使用するアプリケーションの構成ファイルでは、 **\<linkedConfiguration>** 構成情報を直接含めるのではなく、要素を使用してアセンブリ構成ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-120">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="d7c64-121">コンポーネントアセンブリがサービスされている場合、共通構成ファイルを更新すると、そのアセンブリを使用するすべてのアプリケーションに対して、更新された構成情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-121">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="d7c64-122">**\<linkedConfiguration>** 要素は、Windows サイドバイサイドマニフェストを持つアプリケーションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d7c64-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="d7c64-123">次の規則は、リンクされた構成ファイルの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="d7c64-123">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="d7c64-124">インクルードされる構成ファイルの設定は、ローダーバインドポリシーにのみ影響し、ローダーによってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-124">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="d7c64-125">含まれる構成ファイルには、バインドポリシー以外の設定を含めることができますが、これらの設定は何の効果もありません。</span><span class="sxs-lookup"><span data-stu-id="d7c64-125">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="d7c64-126">属性でサポートされている形式 `href` はのみ `file://` です。</span><span class="sxs-lookup"><span data-stu-id="d7c64-126">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="d7c64-127">ローカルファイルと UNC ファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d7c64-127">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="d7c64-128">構成ファイルごとにリンクされる構成の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d7c64-128">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="d7c64-129">`#include`C/c + + のディレクティブの動作と同様に、すべてのリンクされた構成ファイルが1つのファイルに結合されます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-129">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="d7c64-130">**\<linkedConfiguration>** 要素は、アプリケーション構成ファイル内でのみ許可されます。 *machine.config*では無視されます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-130">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="d7c64-131">循環参照が検出され、終了します。</span><span class="sxs-lookup"><span data-stu-id="d7c64-131">Circular references are detected and terminated.</span></span> <span data-ttu-id="d7c64-132">つまり、 **\<linkedConfiguration>** 一連の構成ファイルの要素がループを形成すると、ループが検出され、停止されます。</span><span class="sxs-lookup"><span data-stu-id="d7c64-132">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="d7c64-133">例</span><span class="sxs-lookup"><span data-stu-id="d7c64-133">Example</span></span>

<span data-ttu-id="d7c64-134">次の例は、ローカルハードディスクの構成ファイルを含める方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7c64-134">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d7c64-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7c64-135">See also</span></span>

- [<span data-ttu-id="d7c64-136">**\<assemblyBinding>** Element</span><span class="sxs-lookup"><span data-stu-id="d7c64-136">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="d7c64-137">.NET Framework の構成ファイルスキーマ</span><span class="sxs-lookup"><span data-stu-id="d7c64-137">Configuration file schema for the .NET Framework</span></span>](index.md)
