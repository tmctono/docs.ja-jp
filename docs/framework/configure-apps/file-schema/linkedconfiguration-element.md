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
ms.openlocfilehash: 909ee7cbb7cd31cf213f305b23237cb69e295882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674650"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="f1d6d-102">\<linkedConfiguration > 要素</span><span class="sxs-lookup"><span data-stu-id="f1d6d-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="f1d6d-103">インクルードする構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="f1d6d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f1d6d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f1d6d-105">&nbsp;&nbsp;[**\<assemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f1d6d-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="f1d6d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="f1d6d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f1d6d-107">構文</span><span class="sxs-lookup"><span data-stu-id="f1d6d-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="f1d6d-108">属性</span><span class="sxs-lookup"><span data-stu-id="f1d6d-108">Attribute</span></span>

|           | <span data-ttu-id="f1d6d-109">説明</span><span class="sxs-lookup"><span data-stu-id="f1d6d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f1d6d-110">**href**</span><span class="sxs-lookup"><span data-stu-id="f1d6d-110">**href**</span></span>  | <span data-ttu-id="f1d6d-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-111">Required attribute.</span></span><br><br><span data-ttu-id="f1d6d-112">含める構成ファイルの URL。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="f1d6d-113">唯一の形式のサポート、 **href**属性が`file://`します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="f1d6d-114">ローカル ファイルと UNC ファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f1d6d-115">親要素</span><span class="sxs-lookup"><span data-stu-id="f1d6d-115">Parent element</span></span>

|     | <span data-ttu-id="f1d6d-116">説明</span><span class="sxs-lookup"><span data-stu-id="f1d6d-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f1d6d-117">**\<assemblyBinding >** 要素</span><span class="sxs-lookup"><span data-stu-id="f1d6d-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="f1d6d-118">構成レベルでのアセンブリ バインディング ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f1d6d-119">子要素</span><span class="sxs-lookup"><span data-stu-id="f1d6d-119">Child elements</span></span>

<span data-ttu-id="f1d6d-120">なし</span><span class="sxs-lookup"><span data-stu-id="f1d6d-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f1d6d-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1d6d-121">Remarks</span></span>

<span data-ttu-id="f1d6d-122"> *\*\<LinkedConfiguration >** 要素は、サービス コンポーネントのアセンブリを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="f1d6d-123">1 つまたは複数のアプリケーションでは、既知の場所に存在する構成ファイルを持つアセンブリを使用する場合、アセンブリを使用するアプリケーションの構成ファイルを使用できます、  **\<linkedConfiguration >** 構成情報を直接含むのではなく、アセンブリの構成ファイルを含める要素。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="f1d6d-124">コンポーネント アセンブリが処理されるときに一般的な構成ファイルの更新、アセンブリを使用するすべてのアプリケーションに最新の構成情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d6d-125"> *\*\<LinkedConfiguration >** Windows サイド バイ サイドでマニフェストを使用するアプリケーションの要素がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="f1d6d-126">次の規則は、リンクされた構成ファイルの使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="f1d6d-127">含まれる構成ファイルの設定は、ローダーのバインディング ポリシーの影響を与えるし、のみローダーでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="f1d6d-128">含まれる構成ファイルではバインディング ポリシー以外の設定を使用できますが、これらの設定は、影響はありません。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="f1d6d-129">唯一の形式のサポート、`href`属性が`file://`します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="f1d6d-130">ローカル ファイルと UNC ファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="f1d6d-131">構成ファイルごとにリンクされている構成の数に制約はありません。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="f1d6d-132">すべてのリンクされた構成ファイルを結合し、1 つのファイルの動作と同様に、 `#include` C と C++ のディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="f1d6d-133"> *\*\<LinkedConfiguration >** 要素がアプリケーション構成ファイルにのみ使用できます。 以外では無視されます\*Machine.config\*します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="f1d6d-134">循環参照が検出され、終了します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="f1d6d-135">つまり場合、  **\<linkedConfiguration >** ループを形成する一連の構成ファイルの要素、ループが検出され、停止します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="f1d6d-136">例</span><span class="sxs-lookup"><span data-stu-id="f1d6d-136">Example</span></span>

<span data-ttu-id="f1d6d-137">次の例では、ローカルのハード ディスクから構成ファイルをインクルードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1d6d-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f1d6d-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1d6d-138">See also</span></span>

- [<span data-ttu-id="f1d6d-139">**\<assemblyBinding >** 要素</span><span class="sxs-lookup"><span data-stu-id="f1d6d-139">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="f1d6d-140">.NET Framework の構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f1d6d-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
