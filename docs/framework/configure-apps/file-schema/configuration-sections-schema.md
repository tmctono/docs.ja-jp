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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 120733873a7ea29303fe7f82c4c324d411532897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921208"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="f6d65-102">構成セクションのスキーマ</span><span class="sxs-lookup"><span data-stu-id="f6d65-102">Configuration sections schema</span></span>

<span data-ttu-id="f6d65-103">構成セクションスキーマには、構成ファイルのカスタム設定を定義する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6d65-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="f6d65-104">構成ファイルとスキーマに関する一般的な情報については、 [.NET Framework の構成ファイルスキーマ](index.md)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d65-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="f6d65-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f6d65-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="f6d65-106">[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f6d65-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="f6d65-107">[ **\<clear>** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="f6d65-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="f6d65-108">[ **\<remove>** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="f6d65-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="f6d65-109">[ **\<section>** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="f6d65-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="f6d65-110"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="f6d65-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="f6d65-111">説明</span><span class="sxs-lookup"><span data-stu-id="f6d65-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f6d65-112"> **\<configSections >** の **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="f6d65-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="f6d65-113">以前に定義されたセクションおよびセクション グループのすべてをクリアします。</span><span class="sxs-lookup"><span data-stu-id="f6d65-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="f6d65-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="f6d65-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="f6d65-115">以前に定義されたセクションおよびセクション グループのすべてをクリアします。</span><span class="sxs-lookup"><span data-stu-id="f6d65-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="f6d65-116"> **\<configSections >** </span><span class="sxs-lookup"><span data-stu-id="f6d65-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="f6d65-117">構成セクションと名前空間の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6d65-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="f6d65-118"> **\<remove>** の **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="f6d65-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="f6d65-119">定義済みのセクション、またはセクション グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="f6d65-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="f6d65-120"> **\<section>** の **\<configSections >** と **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="f6d65-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="f6d65-121">構成セクションの宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6d65-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="f6d65-122">configsections の **\<sectionGroup >** >  **\<** </span><span class="sxs-lookup"><span data-stu-id="f6d65-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="f6d65-123">構成セクションの名前空間を定義します。</span><span class="sxs-lookup"><span data-stu-id="f6d65-123">Defines a namespace for configuration sections.</span></span> |
