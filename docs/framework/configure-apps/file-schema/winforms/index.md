---
title: Windows フォームの構成セクション
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e76e11ef8bb39d72cb16655c948354bc326e75bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913082"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="efeab-102">Windows フォームの構成セクション</span><span class="sxs-lookup"><span data-stu-id="efeab-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="efeab-103">Windows フォームの構成設定により、カスタマイズされたアプリケーション設定に関する情報 (マルチ モニターや高 DPI のサポート、その他の定義済みの構成設定など) を Windows フォームのアプリで格納したり、取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="efeab-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="efeab-104">Windows フォームのアプリケーション構成設定は、アプリケーション構成ファイルの `System.Windows.Forms.ApplicationConfigurationSection` 要素に格納されます。</span><span class="sxs-lookup"><span data-stu-id="efeab-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="efeab-105">構文</span><span class="sxs-lookup"><span data-stu-id="efeab-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="efeab-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="efeab-106">Attributes and elements</span></span>

<span data-ttu-id="efeab-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="efeab-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="efeab-108">属性</span><span class="sxs-lookup"><span data-stu-id="efeab-108">Attributes</span></span>

<span data-ttu-id="efeab-109">なし。</span><span class="sxs-lookup"><span data-stu-id="efeab-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="efeab-110">子要素</span><span class="sxs-lookup"><span data-stu-id="efeab-110">Child elements</span></span>

<span data-ttu-id="efeab-111">要素</span><span class="sxs-lookup"><span data-stu-id="efeab-111">Element</span></span>  |<span data-ttu-id="efeab-112">説明</span><span class="sxs-lookup"><span data-stu-id="efeab-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="efeab-113">指定した値を持つ構成設定キーを追加します</span><span class="sxs-lookup"><span data-stu-id="efeab-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="efeab-114">親要素</span><span class="sxs-lookup"><span data-stu-id="efeab-114">Parent elements</span></span>

<span data-ttu-id="efeab-115">要素</span><span class="sxs-lookup"><span data-stu-id="efeab-115">Element</span></span>  |<span data-ttu-id="efeab-116">説明</span><span class="sxs-lookup"><span data-stu-id="efeab-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="efeab-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="efeab-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="efeab-118">共通言語ランタイムと Windows フォームのアプリケーションで使用されるすべての構成ファイルのルート要素です</span><span class="sxs-lookup"><span data-stu-id="efeab-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="efeab-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="efeab-119">Remarks</span></span>

<span data-ttu-id="efeab-120">.NET Framework 4.7 を使用すれば、.NET Framework の最近のリリースで追加された機能が利用できる Windows フォームのアプリケーションを、`<System.Windows.Forms.ApplicationConfigurationSection>` 要素で構成できます。</span><span class="sxs-lookup"><span data-stu-id="efeab-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="efeab-121">`<System.Windows.Forms.ApplicationConfigurationSection>` 要素には 1 つまたは複数の子の [`<add>`](windows-forms-add-configuration-element.md) 要素を含めることができ、各要素には特定の構成設定が定義されます。</span><span class="sxs-lookup"><span data-stu-id="efeab-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="efeab-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="efeab-122">See also</span></span>

- [<span data-ttu-id="efeab-123">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="efeab-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="efeab-124">Windows フォームの高 DPI サポート</span><span class="sxs-lookup"><span data-stu-id="efeab-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
