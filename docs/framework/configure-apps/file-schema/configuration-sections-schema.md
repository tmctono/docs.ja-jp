---
title: 構成セクションのスキーマ
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441662"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="20558-102">構成セクションのスキーマ</span><span class="sxs-lookup"><span data-stu-id="20558-102">Configuration sections schema</span></span>

<span data-ttu-id="20558-103">構成セクションスキーマには、構成ファイルのカスタム設定を定義する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20558-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="20558-104">構成ファイルとスキーマに関する一般的な情報については、 [.NET Framework の構成ファイルスキーマ](index.md)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20558-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="20558-105">説明</span><span class="sxs-lookup"><span data-stu-id="20558-105">Description</span></span> |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | <span data-ttu-id="20558-106">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20558-106">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="20558-107">**\<section>** およびの場合 **\<configSections>\*\*\*\*\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="20558-107">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="20558-108">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20558-108">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="20558-109">**\<sectionGroup>** の**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="20558-109">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="20558-110">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="20558-110">Defines a namespace for configuration sections.</span></span> |

<a name="dep"></a>

## <a name="unimplemented-elements"></a><span data-ttu-id="20558-111">未実装の要素</span><span class="sxs-lookup"><span data-stu-id="20558-111">Unimplemented elements</span></span>

<span data-ttu-id="20558-112">次の要素は影響を与えないため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="20558-112">The following elements have no impact and should not be used:</span></span>

* **\<clear>**
* **\<remove>**
