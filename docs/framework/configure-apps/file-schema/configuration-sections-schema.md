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
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155324"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="db13e-102">構成セクションのスキーマ</span><span class="sxs-lookup"><span data-stu-id="db13e-102">Configuration sections schema</span></span>

<span data-ttu-id="db13e-103">構成セクション スキーマには、構成ファイルのカスタム設定を定義する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db13e-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="db13e-104">構成ファイルとスキーマの一般情報については、「 [.NET Framework の構成ファイル スキーマ](index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db13e-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="db13e-105">[**\<構成>**](configuration-element.md)

[**セクションを削除>>セクション>グループ>>クリアする\<セクション**](configsections-element-for-configuration.md)[**\<**](clear-element-for-configsections.md)
[**\<**](section-element.md)

[**\<**](sectiongroup-element-for-configsections.md)[**\<**](remove-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="db13e-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="db13e-106">説明</span><span class="sxs-lookup"><span data-stu-id="db13e-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="db13e-107">構成の>を**\<\*\*\*\*\<クリアするセクション>**</span><span class="sxs-lookup"><span data-stu-id="db13e-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="db13e-108">以前に定義したすべてのセクションおよびセクション グループをクリアします。</span><span class="sxs-lookup"><span data-stu-id="db13e-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="db13e-109">**\<クリア>**</span><span class="sxs-lookup"><span data-stu-id="db13e-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="db13e-110">以前に定義したすべてのセクションおよびセクション グループをクリアします。</span><span class="sxs-lookup"><span data-stu-id="db13e-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="db13e-111">**\<構成セクション>**</span><span class="sxs-lookup"><span data-stu-id="db13e-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="db13e-112">構成セクションと名前空間の宣言が含まれます。</span><span class="sxs-lookup"><span data-stu-id="db13e-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="db13e-113">構成の>を**\<\*\*\*\*\<削除するセクション>**</span><span class="sxs-lookup"><span data-stu-id="db13e-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="db13e-114">定義済みのセクションまたはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="db13e-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="db13e-115">セクション>セクション>および**\<\*\*\*\*\<セクショングループ>** \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="db13e-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="db13e-116">構成セクションの宣言を含みます。</span><span class="sxs-lookup"><span data-stu-id="db13e-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="db13e-117">**\<セクション構成**の**\<グループ>セクション>**</span><span class="sxs-lookup"><span data-stu-id="db13e-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="db13e-118">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="db13e-118">Defines a namespace for configuration sections.</span></span> |
