---
title: アプリ設定スキーマ
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a67689bd9757f7586881fd910ef6103b1dffeab8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550450"
---
# <a name="app-settings-schema"></a><span data-ttu-id="73c97-102">アプリ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="73c97-102">App Settings schema</span></span>

<span data-ttu-id="73c97-103">ファイル パス、XML Web サービス URL、またはアプリケーションのその他のカスタム構成情報など、カスタム アプリケーションの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73c97-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="73c97-104">要素</span><span class="sxs-lookup"><span data-stu-id="73c97-104">Element</span></span> | <span data-ttu-id="73c97-105">説明</span><span class="sxs-lookup"><span data-stu-id="73c97-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="73c97-106">**\<add>** **\<clear>** **\<remove>** アプリケーション設定を制御するための、、およびのタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73c97-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="73c97-107">省略可能な **file** 属性があります。</span><span class="sxs-lookup"><span data-stu-id="73c97-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="73c97-108">設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="73c97-108">Defines a setting.</span></span> <span data-ttu-id="73c97-109">の子 **\<appSettings>** 。</span><span class="sxs-lookup"><span data-stu-id="73c97-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="73c97-110">**key** 属性と **value** 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="73c97-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="73c97-111">すべての設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="73c97-111">Clears all settings.</span></span> <span data-ttu-id="73c97-112">の子 **\<appSettings>** 。</span><span class="sxs-lookup"><span data-stu-id="73c97-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="73c97-113">属性はありません。</span><span class="sxs-lookup"><span data-stu-id="73c97-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="73c97-114">設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="73c97-114">Removes a setting.</span></span> <span data-ttu-id="73c97-115">の子 **\<appSettings>** 。</span><span class="sxs-lookup"><span data-stu-id="73c97-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="73c97-116">**key** 属性が必要です。</span><span class="sxs-lookup"><span data-stu-id="73c97-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="73c97-117">\<appSettings> 要素</span><span class="sxs-lookup"><span data-stu-id="73c97-117">\<appSettings> element</span></span>

<span data-ttu-id="73c97-118">この要素に **\<add>** は、 **\<clear>** **\<remove>** アプリケーションの設定を制御するための、、およびのタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73c97-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="73c97-119">**file** の省略可能な属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="73c97-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="73c97-120">\<add> 要素</span><span class="sxs-lookup"><span data-stu-id="73c97-120">\<add> element</span></span>

<span data-ttu-id="73c97-121">カスタム アプリケーション設定を名前/値のペアとしてアプリケーション設定コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="73c97-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="73c97-122">**key** および **value** の属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="73c97-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="73c97-123">\<clear> 要素</span><span class="sxs-lookup"><span data-stu-id="73c97-123">\<clear> element</span></span>

<span data-ttu-id="73c97-124">継承されたカスタムアプリケーション設定へのすべての参照を削除し、要素の後にある要素によって追加された参照だけを許可し **\<add>** **\<clear>** ます。</span><span class="sxs-lookup"><span data-stu-id="73c97-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="73c97-125">属性は定義されません。</span><span class="sxs-lookup"><span data-stu-id="73c97-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="73c97-126">\<remove> 要素</span><span class="sxs-lookup"><span data-stu-id="73c97-126">\<remove> element</span></span>

<span data-ttu-id="73c97-127">アプリケーション設定コレクションから継承したカスタム アプリケーション設定への参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="73c97-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="73c97-128">**key** の属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="73c97-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="73c97-129">例</span><span class="sxs-lookup"><span data-stu-id="73c97-129">Example</span></span>

<span data-ttu-id="73c97-130">次の例は、カスタム アプリケーション設定を定義する外部アプリケーション設定ファイル (*custom.config*) を示しています。</span><span class="sxs-lookup"><span data-stu-id="73c97-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="73c97-131">次の例は、外部設定ファイルで設定を使用して、独自のアプリケーション設定を設定するアプリケーション構成ファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="73c97-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="73c97-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="73c97-132">See also</span></span>

- [<span data-ttu-id="73c97-133">アプリケーション設定の概要</span><span class="sxs-lookup"><span data-stu-id="73c97-133">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="73c97-134">アプリケーション設定アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="73c97-134">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
